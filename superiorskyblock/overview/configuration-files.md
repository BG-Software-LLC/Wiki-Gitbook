# Configuration Files

The plugin contains a few configuration files where you can edit the behavior of the plugin.

## Directories Tree

* block-values
  * levels.yml\
    In the levels file you can configure custom level points for your blocks. The level points you configured then will be added to the islands when blocks are placed, and can be seen in `/is show`. The format for adding them is `<BLOCK>: <LEVEL>`, where `<BLOCK>` is your block (if your block contains `:` , add '' to the block) and `<LEVEL>` is a number.
  * worth.yml\
    In the levels file you can configure custom worth values for your blocks. The worth values you configured then will be added to the islands when blocks are placed, and can be seen in `/is show`. The format for adding them is `<BLOCK>: <LEVEL>`, where `<BLOCK>` is your block (if your block contains `:` , add '' to the block) and `<LEVEL>` is a number.\
    The difference between this file and the levels.yml file is not major - the plugin gives you two ways of valuating islands. The main idea of worth values to be synced with your shop prices while the levels have custom values that are different.
* commands\
  The plugin gives the ability to create custom commands using the API. The plugin provides another way of registering them not through an external module or a different plugin - you can drag and drop jars that represents custom commands into this folder and the plugin will load them automatically on startup.
* datastore\
  This directory contains all the data files of the plugin. The plugin tracks a lot of data - islands, players, statistics and more. While you can configure islands and players data to be stored in a remote sql server, there is other data that is not stored in this database - for example, missions tracking data, or other external modules data. This data is stored under the folder, in addition to the database file (if you use a local database, such as SQLite)
* lang\
  The lang directory contains files, each representing a different translation for messages of the plugin. Players have the ability to change their preferred language using the `/is lang` command. The names of the files must follow the Locale format (Can be seen [here](https://www.oracle.com/technetwork/java/javase/java8locales-2095355.html).)
* menus\
  The plugin contains a lot of different menus players can interact with. All the menus are 100% configurable, and their configuration files can be found under this directory. For more information about configuring menus, check out [this tutorial](menus/).&#x20;
  * custom\
    Besides the built-in menus, the plugin provides you with the ability to create your own, custom menus, that can be opened using a command of your choice. The configuration files of the custom menus are under this directory - for more information, there is a dedicated tutorial for custom menus [here](https://wiki.bg-software.com/superiorskyblock/overview/menus#creating-custom-menus).
* modules\
  Similar to plugins, the plugin can have different "plugins" (called "modules) that are loaded by the plugin and change the gameplay behavior - an example for such module is [OneBlock](https://wiki.bg-software.com/superiorskyblock/overview/addons#oneblock-addon).\
  The external modules must be put in this directory, which is similar to your plugins directory - each module will have its own directory created where it can put all of its files.
  * bank\
    The bank module is a built-in module that gives the ability to use `/is bank` and all of the functionalities of the island bank. The configuration options for this module are inside the config file under this directory.
  * generators\
    The generators module is a built-in module that brings custom generators to islands.
  * missions\
    The missions module is a built-in module that gives the ability to get rewarded for completing different tasks in game. For further information, there is a dedicated tutorial for missions [here](missions/).
  * upgrades\
    The upgrades module is a built-in module that gives the ability to reward players by making them purchase custom upgrades to their islands. For further information, there is a dedicated tutorial for upgrades [here](upgrades/).
* schematics\
  The schematics directory contains a number of different schematics that can be used to create new islands. Schematic is a file that tells the plugin what blocks to place when a new island is created. For further information, there is a dedicated tutorial for schematics [here](schematics.md).
* world-generator\
  The plugin gives the ability to change the default generation behavior of the islands worlds. Developers can create their own custom world generator and place it inside the world-generator folder, which the plugin will later load and use that generator for the worlds. An example for such behavior is [AcidIslands](https://wiki.bg-software.com/superiorskyblock/overview/addons#acidislands-addon), which changes the void world to be filled with water.

## Configuration Files

* config.yml\
  The configuration file contains a lot of different options that can be toggled and changed of the plugin. If you don't like a feature and want it to be disabled, that's the first place to look for it. The plugin is almost entirely configurable, and everything is done through this file.
* entity-categories.yml\
  The entity categories file contains categories of entities, and lets you configure which [island privileges](island-privileges.md) and [island flags](island-flags.md) control the actions done to the entities of each category. Each category has an `entities` list and an `actions` section with the following actions:

  * `SPAWN` - The privilege required to spawn the entities using spawn eggs.
  * `DAMAGE` - The privilege required to damage the entities.
  * `INTERACT` - The privilege required to interact with the entities.
  * `SPAWNER_SPAWN` - The island flag required so the entities can spawn from spawners.
  * `NATURAL_SPAWN` - The island flag required so the entities can spawn naturally.

  ```yaml
  VILLAGERS:
    entities:
      - VILLAGER
    actions:
      INTERACT: VILLAGER_TRADING
  ```

  You can create as many custom categories as you want, and using privilege or flag names that don't exist in the plugin will register them as new custom privileges/flags. The `ANIMAL`, `MONSTER`, `TAMEABLE` and `VEHICLE` categories are built-in groups - they do not have an `entities` list, and their entities are added automatically depending on your Minecraft version.
* heads.yml\
  The heads file contains a list of custom skins for different mobs that can be seen in `/is values` and inside other menus. The skins are base64 and can be taken from services online (such as [https://minecraft-heads.com/](https://minecraft-heads.com/))
* interactables.yml\
  The interactables file contains lists of blocks that players can interact with, grouped by the [island privilege](island-privileges.md) that is required to interact with them:

  ```yaml
  <PRIVILEGE>:
    - BLOCK_TYPE
    - ...
  ```

  You can create as many custom privileges as you want - using a privilege name that doesn't exist in the plugin will register it as a new custom privilege. Each block should only be listed under one privilege.\
  Blocks that are not listed in this file will not get checked when interacted, letting all players interact with them on other islands. This means that if, for example, `CHEST` is not listed under this file, all the players will be able to interact with chests on islands.\
  The old format of the file - a single `interactables` list of blocks - is still supported: the plugin automatically converts it on startup by assigning a privilege to each block based on its type (chests to `CHEST_ACCESS`, containers to `USE`, signs to `SIGN_INTERACT`, spawners to `SPAWNER_BREAK`, farmland and crops to `FARM_TRAMPING`, turtle eggs to `TURTLE_EGG_TRAMPING`, lecterns to `PICKUP_LECTERN_BOOK`, and everything else to `INTERACT`).
* safe\_blocks.yml\
  This safe blocks file contains a list of blocks that player can teleport to safely. The plugin blocks teleportation of players to blocks that are considered "unsafe" to prevent players dying when they are teleported to islands.
