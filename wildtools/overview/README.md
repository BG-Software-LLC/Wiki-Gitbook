---
description: >-
  WildTools brings the ability to create custom wands and tools that can be used
  by players. You can create Sell-Wands, Harvester Hoes, Trench Pickaxes and
  more!
---

# Overview

{% embed url="https://www.youtube.com/watch?v=703E9BzrZF4" %}
Diamondxr showcasing the plugin
{% endembed %}

The plugin brings custom tools to your server with many different actions they can perform - breaking multiple blocks, placing blocks, sell contents in containers and more!

## Table of Contents

* [Overview](https://wiki.bg-software.com/wildtools/overview)
  * [Supported Plugins](https://wiki.bg-software.com/wildtools/overview#supported-plugins)
    * [Adding support for plugins](https://wiki.bg-software.com/wildtools/overview#adding-support-for-plugins)
    * [Built-in support](https://wiki.bg-software.com/wildtools/overview#built-in-support)
* [Commands and Permissions](https://wiki.bg-software.com/wildtools/overview/commands-and-permissions)
  * [Commands](https://wiki.bg-software.com/wildtools/overview/commands-and-permissions#commands)
  * [Permissions](https://wiki.bg-software.com/wildtools/overview/commands-and-permissions#permissions)
* [Configuring Tools](https://wiki.bg-software.com/wildtools/overview/configuring-tools)
  * [Tool Sections](https://wiki.bg-software.com/wildtools/overview/configuring-tools#tool-sections)
* [Builder Tool](https://wiki.bg-software.com/wildtools/overview/builder-tool)
  * [Required Sections](https://wiki.bg-software.com/wildtools/overview/builder-tool#required-sections)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/builder-tool#how-to-use)
* [Cannon Tool](https://wiki.bg-software.com/wildtools/overview/cannon-tool)
  * [Required Sections](https://wiki.bg-software.com/wildtools/overview/cannon-tool#required-sections)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/cannon-tool#how-to-use)
* [Crafting Tool](https://wiki.bg-software.com/wildtools/overview/crafting-tool)
  * [Required Sections](https://wiki.bg-software.com/wildtools/overview/crafting-tool#required-sections)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/crafting-tool#how-to-use)
* [Crowbar Tool](https://wiki.bg-software.com/wildtools/overview/crowbar-tool)
  * [Optional Sections](https://wiki.bg-software.com/wildtools/overview/crowbar-tool#optional-sections)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/crowbar-tool#how-to-use)
* [Cuboid Tool](https://wiki.bg-software.com/wildtools/overview/cuboid-tool)
  * [Required Sections](./#custom-containers)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/cuboid-tool#how-to-use)
* [Drain Tool](https://wiki.bg-software.com/wildtools/overview/drain-tool)
  * [Required Sections](https://wiki.bg-software.com/wildtools/overview/drain-tool#required-sections)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/drain-tool#how-to-use)
* [Harvester Tool](https://wiki.bg-software.com/wildtools/overview/harvester-tool)
  * [Required Sections](https://wiki.bg-software.com/wildtools/overview/harvester-tool#required-sections)
  * [Optional Sections](https://wiki.bg-software.com/wildtools/overview/harvester-tool#optional-sections)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/harvester-tool#how-to-use)
    * [Sell Mode](https://wiki.bg-software.com/wildtools/overview/harvester-tool#sell-mode-enable-disable)
* [Ice Tool](https://wiki.bg-software.com/wildtools/overview/ice-tool)
  * [Required Sections](https://wiki.bg-software.com/wildtools/overview/ice-tool#required-sections)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/ice-tool#how-to-use)
* [Lightning Tool](https://wiki.bg-software.com/wildtools/overview/lightning-tool)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/lightning-tool#how-to-use)
* [Magnet Tool](https://wiki.bg-software.com/wildtools/overview/magnet-tool)
  * [Required Sections](https://wiki.bg-software.com/wildtools/overview/magnet-tool#required-sections)
  * [How to Use](./#adding-support-for-plugins)
* [Pillar Tool](https://wiki.bg-software.com/wildtools/overview/pillar-tool)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/pillar-tool#how-to-use)
* [Sell Tool](https://wiki.bg-software.com/wildtools/overview/sell-tool)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/sell-tool#how-to-use)
* [Sort Tool](https://wiki.bg-software.com/wildtools/overview/sort-tool)
  * [How to Use](https://wiki.bg-software.com/wildtools/overview/sort-tool#how-to-use)

## Supported Plugins

The plugin handles the interactions of the tools and how they behave, and this may cause conflicts with other plugins. However, the plugin is packed with a smart system that supports every plugin in the world.

### Adding support for plugins

There are two different supports you can add - one, is for claiming plugins. If you have a plugin that prevents blocks from being broken by other plugins, WildTools should know it and respect their restrictions. If you have a plugin like that, simply add it to the `claiming-plugins` list in your config, and WildTools will do the job.

The second type of plugins is plugins that do something when a block is broken or placed. For example, giving rewards for breaking blocks. These plugins should know about the blocks that were broken or placed, and by adding them to the `other-plugins` list in your config, WildTools will make sure they are notified about these changes.

By filterring which plugins should be notified about actions made by WildTools, you can reduce the amount of lag caused by the amount of actions there are. Many plugins know how to handle breaking of one block at a time, however using tools of WildTools you can break multiple at once, which can drop performance due to other plugins.

### Built-in support

The plugin has a few plugins that are supported by default. Here's a list of them:

#### Custom Containers

* [WildChests](https://bg-software.com/wildchests/)

#### Custom Drops

* [MergedSpawner](https://polymart.org/resource/189)
* [RoseStacker](https://www.spigotmc.org/resources/82729/)
* [SilkSpawners](https://www.spigotmc.org/resources/7811/)
* [WildStacker](https://bg-software.com/wildstacker/)
* [mcMMO](https://www.spigotmc.org/resources/64348/)

#### Custom Prices

* [CMI](https://www.spigotmc.org/resources/3742/)
* [EconomyShopGUI](https://www.spigotmc.org/resources/69927/)
* [Essentials](https://www.spigotmc.org/resources/9089/)
* [GUIShop](https://www.spigotmc.org/resources/2451/)
* NewtShop
* [QuantumShop](https://www.spigotmc.org/resources/50696/)
* [ShopGUIPlus](https://www.spigotmc.org/resources/6515/)

#### Custom Claims

* [FactionsUUID](https://www.spigotmc.org/resources/1035/)
* [GriefPrevention](https://www.spigotmc.org/resources/1884/)
* [Lands](https://www.spigotmc.org/resources/53313/)
* [MassiveCore Factions](https://www.spigotmc.org/resources/1900/)
* [Residence](https://www.spigotmc.org/resources/11480/)
* [Towny](https://www.spigotmc.org/resources/72694/)
* [Villages](https://www.spigotmc.org/resources/88265/)
