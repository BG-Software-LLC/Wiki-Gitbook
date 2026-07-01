---
description: >-
  WildStacker is suitable for servers with a lot of entities and drops which
  want to reduce the server-lag that they cause without changing the game
  experience.
---

# Overview

{% embed url="https://www.youtube.com/watch?v=Txh3rim3s-I" %}
Diamondxr showcasing the plugin
{% endembed %}

The plugin can stack entities, items, spawners, blocks, buckets and stews - all in one plugin. It uses asynchronous tasks to ensure the best experience with least amount of lag possible. The plugin has algorithms for stacking entities that no other plugin has to prevent lag from entities.

## Table of Contents

* [Overview](https://wiki.bg-software.com/wildstacker/overview)
  * [Supported Plugins](https://wiki.bg-software.com/wildstacker/overview#supported-plugins)
    * [Custom Entities](https://wiki.bg-software.com/wildstacker/overview#custom-entities)
    * [Custom Spawners](https://wiki.bg-software.com/wildstacker/overview#custom-spawners)
    * [Additional Plugins](https://wiki.bg-software.com/wildstacker/overview#additional-plugins)
* [Commands and Permissions](https://wiki.bg-software.com/wildstacker/overview/commands-and-permissions)
  * [Commands](https://wiki.bg-software.com/wildstacker/overview/commands-and-permissions#commands)
  * [Permissions](https://wiki.bg-software.com/wildstacker/overview/commands-and-permissions#permissions)
* [Items Stacker](https://wiki.bg-software.com/wildstacker/overview/items-stacker)
  * [Stacking Algorithm](https://wiki.bg-software.com/wildstacker/overview/items-stacker#stacking-algorithm)
  * [Stacking Triggers](https://wiki.bg-software.com/wildstacker/overview/items-stacker#stacking-triggers)
* [Entities Stacker](https://wiki.bg-software.com/wildstacker/overview/entities-stacker)
  * [Stacking Algorithm](https://wiki.bg-software.com/wildstacker/overview/entities-stacker#stacking-algorithm)
  * [Stacking Triggers](https://wiki.bg-software.com/wildstacker/overview/entities-stacker#stacking-triggers)
  * [Stacking Checks](https://wiki.bg-software.com/wildstacker/overview/entities-stacker#stacking-checks)
  * [Loot Tables](https://wiki.bg-software.com/wildstacker/overview/entities-stacker/loot-tables)
    * [Loot Tables](https://wiki.bg-software.com/wildstacker/overview/entities-stacker/loot-tables#loot-tables)
    * [Loot Pairs](https://wiki.bg-software.com/wildstacker/overview/entities-stacker/loot-tables#loot-pairs)
    * [Loot Items](https://wiki.bg-software.com/wildstacker/overview/entities-stacker/loot-tables#loot-items)
    * [Loot Commands](https://wiki.bg-software.com/wildstacker/overview/entities-stacker/loot-tables#loot-commands)
  * [Linked Entities](https://wiki.bg-software.com/wildstacker/overview/entities-stacker/linked-entities)
    * [Stacking Algorithm](https://wiki.bg-software.com/wildstacker/overview/entities-stacker/linked-entities#linked-entities-stacking-algorithm)
* [Spawners Stacker](https://wiki.bg-software.com/wildstacker/overview/spawners-stacker)
  * [Spawners Override](https://wiki.bg-software.com/wildstacker/overview/spawners-stacker/spawners-override)
    * [Optimizations](https://wiki.bg-software.com/wildstacker/overview/spawners-stacker/spawners-override#optimizations)
    * [Spawn Conditions](https://wiki.bg-software.com/wildstacker/overview/spawners-stacker/spawners-override/spawn-conditions)
  * [Spawner Upgrades](https://wiki.bg-software.com/wildstacker/overview/spawners-stacker/spawner-upgrades)
    * [Spawner Settings](https://wiki.bg-software.com/wildstacker/overview/spawners-stacker/spawner-upgrades#spawner-settings)
    * [Upgrade Ladders](https://wiki.bg-software.com/wildstacker/overview/spawners-stacker/spawner-upgrades#upgrade-ladders)
    * [Custom Drops](https://wiki.bg-software.com/wildstacker/overview/spawners-stacker/spawner-upgrades#custom-drops)
* [Blocks Stacker](https://wiki.bg-software.com/wildstacker/overview/blocks-stacker)

## Supported Plugins

The plugin has support for many plugins to distinguish custom mobs from vanilla ones. The following plugins are supported:

### Custom Entities

* [Boss](https://www.mc-market.org/resources/21619/)
* [Citizens](https://www.spigotmc.org/resources/13811/)
* [EchoPet](https://dev.bukkit.org/projects/echopet)
* [EliteBosses](https://www.spigotmc.org/resources/89093/)
* [JetsMinions](https://www.spigotmc.org/resources/59972/)
* [LevelledMobs](https://www.spigotmc.org/resources/74304/)
* [MiniaturePets](https://www.spigotmc.org/resources/23991/)
* [MoreBosses](https://www.spigotmc.org/resources/69355/)
* [MyPet](https://www.spigotmc.org/resources/12725/)
* [MythicMobs](https://www.spigotmc.org/resources/5702/)
* [PinataParty](https://www.spigotmc.org/resources/59318/)

### Custom Spawners

* [MineableSpawners](https://www.spigotmc.org/resources/59921/)
* [SilkSpawners](https://www.spigotmc.org/resources/7811/)
* [EpicSpawners](https://songoda.com/marketplace/product/13)

### Additional Plugins

* [CoreProtect](https://www.spigotmc.org/resources/8631/)
* [Clearlagg](https://www.spigotmc.org/resources/68271/)
* [Jobs](https://www.spigotmc.org/resources/4216/)
* [mcMMO](https://www.spigotmc.org/resources/64348/)
* [CrazyEnchantments](https://www.spigotmc.org/resources/16470/)
* [Slimefun](https://github.com/Slimefun/Slimefun4)
