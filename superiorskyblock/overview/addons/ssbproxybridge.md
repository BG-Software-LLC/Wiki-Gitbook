---
description: Adds support for multiple servers synchronization for SuperiorSkyblock2
---

# SSBProxyBridge

This is a module that adds support for proxy - such as Velocity or BungeeCord. This module is meant to be used by large networks that can’t hold all of their players on one server only.

## FAQ

**Is it free of charge?** \
Unfortunately not. The module is paid, monthly subscription, and costs 30$ per month. The reason for the price is the amount of work put into the module, the fact that it targets only large networks (that should have a strong income from their server), it’s not required to run SuperiorSkyblock2 and that premium support will be given to the customers (help with setting up everything, bug fixes, questions, etc.)

**Can the worlds be saved into a database?** \
Sadly not. Islands will not be serialized and saved into a database, as the module doesn’t change the way worlds are handled.

**Does the module run a server for each player?** \
The module will only forward players to already existing servers, and make sure to spread them as best as possible.

**Does the module support SlimeWorldManager, or any other custom worlds management?** \
Yes, the module will not break existing worlds management modules.

**Is it possible to add more servers as the time goes?** \
Yes, you’ll be able to add more servers and players will be forwarded to them. \
However, removing servers will cause islands to not be loaded and players will not be able to teleport to them.

**Are players able to visit and interact with islands on other servers?** \
Of course! One of the most important things of the module is to not hurt the experience from the players perspective.

**What will happen when a server is down?** \
When a server goes down, the players inside it will be forwarded to the spawn server, and they will not be able to teleport to their island. At first it may sound problematic, however it’s the same as a regular server goes down - you will not be able to play on it until it’s up. This situation should not occur, and the skyblock instances should be up as long as the entire proxy is up. The bright side is that data will still be fine - if the server was closed without unexpected crashes, it will be saved just fine.

## **Internals**

Before we start with the internals of the module itself, it’s important to first understand how SuperiorSkyblock2 saves its data. Every object that can be saved into a database (islands, players, etc) has a class that handles interactions with the database for that specific object, and it may be unique for each object. This class is a bridge between the object and the database, and it is referenced as “[DatabaseBridge](https://github.com/BG-Software-LLC/SuperiorSkyblock2/blob/master/API/src/main/java/com/bgsoftware/superiorskyblock/api/data/DatabaseBridge.java)”.

When a player makes a change that requires interaction with the database, the object he was interacting with calls one of the methods of its database bridge, which then interacts with the database asynchronously. This makes it so the high-level of the plugin does not care about the database implementation, and this what gives the plugin the ability to interact with all the database types in the world - sql, mongodb and anything else that can implement the methods required by the database bridge.

Why is it even important you may ask yourself? Well, this is where the magic starts. The new module will handle the database bridges of the objects of the plugin - therefore, insteading of saving the data into the database, it will send them to somewhere else, to handle all of it. Because the process is done fully asynchronously, it will not impact performance at all.

Now that I explained how it’s possible to achieve the goal of the module, we need to understand and go through the issues we need to deal with:

* Load balancing; we want a way to spread the islands between multiple servers, so not all the islands end up being on one server.&#x20;
* Support other modules; such as slime world manager worlds, etc. We want to still support other modules (besides ones that change database bridges as well).&#x20;
* Synchronization of data between different servers; we want invites, messages, etc to work across servers.&#x20;
* Support multiple proxies; nowadays one proxy can’t hold enough players, and networks have multiple proxies that players connect to.&#x20;
* Performance; one of the most important aspects is to keep performance as good as possible. Otherwise, what’s the point of the module?

I will go through each one of the issues in the following pages and explain how we can deal with each one of them.

### Load balancing

In order to keep the performance of your servers in its highest, the module will spread the players across the servers. In order to achieve it, it will act as a load-balancer for players, and will forward them upon islands creation to the most optimal server.

When a player first joins the server, he will be forwarded to the spawn server (which can be a server that also has islands as well). However, once the player chooses to create an island, instead of creating the island in the server he is playing on, the module will look for the most optimal server to create the island at.

The module will also have another aspect besides a regular module on your skyblock instance - it will be a proxy plugin as well, that can process lookups for servers. The proxy aspect will track islands for each server, and will track how active they are. In general, servers with more active islands probably have more potential to have lag. Therefore, when an island is created, it will look for the server with the least amount of active islands, and will communicate with the module on that server to create the island for it. Once the island is successfully created, the player will be teleported to that server, right into his island.

### Support other modules

As explained before, the module only changes the database layer of the plugin, and forwards calls that originally meant to the database onto another remote service. This gives the ability to have other modules that change other things to not be affected by this module. As long as you keep all skyblock instances synced with their configuration files and modules, everything will work as intended.

### Synchronization of data

The main feature of the module is its ability to synchronize data between multiple servers. In order to achieve that, the servers must communicate with each other at first, and sync the data between them all. The question is "how can it be achieved", and in this chapter it will be explained.

Before we dive into details, we first need to take some considerations:

* &#x20;Islands can be modified by any server, therefore changes should be synchronized (island being changed from multiple islands should consist all changes)&#x20;
* We need one component that will let the skyblock instances to communicate with each other (message queue/broker)&#x20;
* We need one component that will handle data saving (database)

#### **Message Queue/Broker**

Message queue/broker is a design pattern to handle communication between services that can be asynchronous. When one service wants to tell another one about an event that happened, for example, instead of directly communicating with that service, it sends a message to a 3rd party component, then the other service can read messages from this component. This design breaks the hard-connection between the services, and allows multiple services to communicate with each other - this component is called Message Broker. The message broker stores the messages it receives as a queue of messages (the first message that it received will be the first message to be read), and services can subscribe to it and read the messages it receives. Because there is no direct connection between the services, services can read messages from the broker only when they can, and this is helpful for performance.

In our case, skyblock instances will let other instances about certain events - island creations, data manipulation of islands, etc. Then, other skyblock instances can listen to the messages and update data and do certain actions when needed. An example for such an action is an island creation

#### Database&#x20;

In order to keep the data between restarts, we need to somehow store it in a database. With the regular plugin, this database is a SQL database that can be either local or remote. However, in the case of the module, the database must be a remote one - so all the skyblock instances will be able to interact with it. There are no restrictions or requirements to the database besides the obvious that it needs to be remotely. The most ideal database to be used is Redis, as it can act as a database and a message broker (described in more detailed above), however it doesn't really matter and it's up to you.

### Multiple Proxies

Nowadays large networks cannot depend on one proxy (whether its Velocity or BungeeCord) to hold all their players, and therefore they have multiple proxies connected to their servers where players can connect through. This brings another challenge we need to face - how can we synchronize everything between multiple proxies?

At first it may sound horrible, but when you better understand how multiple proxies are set up it turns to be pretty easy. The proxies at the end are connected to the same servers, therefore players that were connected from proxy A can play together with players connected from proxy B. This setup is completely invisible to the players, and they will not notice a different - therefore, the only issue left is to understand how the module interacts with the proxy and how we can get it working. The module needs to communicate with the proxy in order to make two simple actions - the first is to move players between servers, and the second one is to know in which server the players should have their new islands.

#### **Manager**

In a multiple proxies setup, we will need a 3rd-party service that will be able to manage all the islands from all the proxies. The manager will wait for the skyblock instances to communicate with it and will wait organize everything for them. It will track which island is in which server, which islands are active and which aren’t so it will know which server is the best for the next island creation.

When a player creates an island, instead of straight away creating the island on the server, instead the module will send a request to the manager and ask for the most optimal server to create the island on. Then, it will check if the server is itself - if it is, then the normal process of island creation will proceed. Otherwise, the server will tell the server that was received that it needs to create a new island, and once this process is done, it will teleport the player to his new island, on the other server.

The manager can handle the following requests:

* Register a new server&#x20;
* Unregister a server (when server is down)&#x20;
* Find the most optimal server to create an island at&#x20;
  * This process should check for the server with the least amount of active islands.&#x20;
* Get the server of an island.

## Installation Guide

#### First Step: Downloading the zip file.

When downloading the module, you'll receive a zip file containing multiple files:

* SSBProxyBridge-X.Y.Z.jar - This is the module jar itself. It should be installed on each of your spigot instances.
* SSBProxyBridge-Manager-X.Y.Z\_standalone.jar - This is a standalone manager jar. You need to run it as a separate server.

#### Second Step: Run for the first time

Launch all your spigot instances as well as the manager for the first time. This action will generate all the config files for the modules and the manager.

#### Third Step: Configuration

**Manager Configuration**

You can configure the port and the IP the manager listens to, the keep-alive interval as well as a list of excluded servers that islands will not be generated at. You don't need to add to this list servers that do not have the module installed.

**Module Configuration**

The configuration file of the module is more complicated than the manager's one. It contains two main sections that needs to be configured: the `messaging-service` and the `manager`. These sections are for configuring the way the module will communicate with other servers and the manager. It's important to configure it correctly before running your servers.

{% hint style="warning" %}
When configuring the `server`field, make sure it's identical to the name you configure to your server in your proxy (Velocity or BungeeCord)&#x20;
{% endhint %}

