---
description: >-
  Using missions, you can give your players tasks to do on your server. In this
  documentation, you will understand how to edit them to your own style!
---

# Missions

## How do missions work?

First of all, it's important to understand how missions work. Missions are instructions that given to external jars (similar to plugins). The jars handle the events and actions that player do, and by following the instructions that are given to them, they know how to reward the players or islands. SuperiorSkyblock provides default jars that know how to handle a large range of actions, such as block breaking, island actions, enchanting, collection of items and crafting of items.

## Default mission jars

Here you can find information about every default mission jar.

#### BlocksMissions

The BlocksMissions jar handles tracking of placement and breaking of blocks in islands. Using this jar, you can give players missions that they need to break certain blocks or place them.\
You can read more about it [here](blocksmissions.md).

#### **BrewingMissions**

The BrewingMissions jar handles tracking of brewing potions in islands. Using this jar, you can give players missions that they need to brew certain potions.\
You can read more about it [here](brewingmissions.md).

#### **CraftingMissions**

The CraftingMissions jar handles tracking of crafting items in islands. Using this jar, you can give players missions that they need to craft items in a crafting table.\
You can read more about it [here](craftingmissions.md).

#### **EnchantingMissions**

The EnchantingMissions jar handles tracking of enchanting items in islands. Using this jar, you can give players missions that they need to enchant certain items.\
You can read more about it [here](enchantingmissions.md).

#### **FarmingMissions**

The FarmingMissions jar handles tracking of growth of crops in islands. Using this jar, you can give players missions that they need to plant crops. \
You can read more about it [here](farmingmissions.md).

#### **FishingMissions**

The FishingMissions jar handles tracking of fishing in islands. Using this jar, you can give players missions that they need to fish.\
You can read more about it [here](fishingmissions.md).

#### **IslandMissions**

The IslandMissions jar handles tracking island events. Using this jar, you can give players missions that can be completed once an event is fired.\
You can read more about it [here](islandmissions.md).

#### **ItemsMissions**

The ItemsMissions jar handles tracking of items in inventories. Using this jar, you can give players missions that they need to hold an item for completion.\
You can read more about it [here](itemsmissions.md).

#### **KillsMissions**

The KillsMissions jar handles tracking of mobs killing in islands. Using this jar, you can give players missions that they need to kill mobs.\
You can read more about it [here](killsmissions.md).

#### **StatisticsMissions**

The StatisticsMissions jar handles tracking of statistics. Using this jar, you can give players missions that they need to get certain statistics.\
You can read more about it [here](statisticsmissions.md).

## Missions files-structure

The root folder for missions is the "categories" folder, located in `modules/missions/categories`. This folder should contain only folders, each represents a different missions-category. Each category folder can contain unlimited amount of files, each represents a different mission inside that category. The name of the missions will be the same as the name of the file representing your mission.

## Create your first mission

Here you'll understand how to create your own mission. All the missions have the follow the same concept, but in this tutorial I chose to customize my own lumberjack mission!

I first start with setting basic information (name & mission type):

```yaml
mission-file: BlocksMissions    # I am using the BlocksMissions jar as it knows how to handle block breaking.
```

After that, I start giving it some more advanced settings. I want my players to only gain progress from natural blocks spawning, I want the mission to be reset upon disbanding of an island, and I want them to be able to use the mission if they are above island level of 250.

```yaml
mission-file: BlocksMissions

only-natural-blocks: true             # Make sure only natural blocks are counted.
disband-reset: true                   # Resetting the mission upon island disband.
required-checks:                      # Handles custom checks, such as minimum level requirement.
  - '%superior_island_level% > 250'
```

Now, I will configure three important things:

1. The blocks that will be tracked (I am using 1.16 blocks).
2. Rewards for the mission
3. The icon of the mission that will be displayed in /is missions.

```yaml
mission-file: BlocksMissions

only-natural-blocks: true
disband-reset: true
required-checks:
 - '%superior_island_level% > 250'

# The blocks that will be tracked.
required-blocks:
 # A section of blocks. All the blocks in a section will be counted together.
 '1':
   # All the blocks of this section.
   types:
     - 'OAK_LOG'
     - 'SPRUCE_LOG'
     - 'BIRCH_LOG'
     - 'JUNGLE_LOG'
     - 'ACACIA_LOG'
     - 'DARK_OAK_LOG'
   # The total amount of all the blocks of the section (5 stacks).
   amount: 320

# The rewards of the mission.
rewards:
 items:
   '1':                  # Random section name, doesn't really matter.
     type: OAK_SAPLING   # The item's type
     amount: 16          # The item's amount.
 commands:               # Commands that will be executed upon completion.
   - 'is admin msg %player% &e&lMission | &7Successfully finished the mission Lumberjack!'

# Settings related to the icon in the missions menu.
icons:
 # The icon that will be displayed when the player cannot complete the mission for any reason.
 not-completed:
   type: PAPER
   name: '&aLumberjack'
   lore:
     - '&7Cut 320 logs.'
     - ''
     - '&6Required Materials:'
     - '&8 - &7x320 Logs'
     - ''
     - '&6Rewards:'
     - '&8 - &7x16 Oak Saplings'
     - ''
     - '&6Cut Logs: &7{1}/320'
     - '&6Progress: &7{0}%'
     - '&c&l ✘ &7Not Completed'
 # The icon that will be displayed when the player can complete the mission.
 can-complete:
   type: PAPER
   name: '&aLumberjack'
   lore:
     - '&7Cut 320 logs.'
     - ''
     - '&6Required Materials:'
     - '&8 - &7x320 Logs'
     - ''
     - '&6Rewards:'
     - '&8 - &7x16 Oak Saplings'
     - ''
     - '&6Cut Logs: &7320/320'
     - '&6Progress: &7100%'
     - '&a&l ✔ &7Click to redeem your reward.'
   enchants:
     DURABILITY: 1
   flags:
     - HIDE_ENCHANTS
 # The icon that will be displayed when the player has already completed the mission.
 completed:
   type: MAP
   name: '&aLumberjack'
   lore:
     - '&7Cut 320 logs.'
     - ''
     - '&6Cut Logs: &7320/320'
     - '&6Progress: &7100%'
     - '&a&l ✔ &7Already Claimed.'
```

As you might have noticed, I used some built-in placeholders, such as {0} and {1}. \
{0} - Used as a percentage placeholder. \
{1} - Used as a placeholder for the amount of tracked blocks. \
{value\_\<block>} - Used as a placeholder for the amount of a specific tracked block.\
{percentage\_\<block>} - Used as a percentage placeholder for a specific block.

That's it! The mission is now setup and ready to be used. There are more settings that can be applied to all the missions:\
`required-missions`: A list of missions that must be completed before completion of the mission. \
`required-checks`: A list of checks which depend on placeholders that needs to be checked before completion of the mission. \
`only-show-if-required-completed`: Whether or not the mission should only be shown in menus when the required missions & checks are completed. \
`island`: Whether or not the mission should be an islands mission (mission that is synced with all island members).                                                                                                                                                                                             `weight`: The order this mission will be displayed in the missions folder. Missions will be sorted by their weights, and if two missions have the same weight, they will be sorted by their names instead.\
`auto-reward`: Whether or not the plugin should reward the players without them doing it in the missions menu. \
`disband-reset`: Whether or not the mission should be reset when disbanding the island (used for player-missions).\
`leave-reset`: Whether or not the mission should be reset when leaving an island (used for player-missions).\
`reset-amount`: The amount of times a mission can be completed. \
`rewards.items`: A list of items that will be given to players when they complete the mission. `rewards.commands`: A list of commands that will be executed when players complete the mission. `icons.not-completed`: The item that will be shown in the menu when the mission is not completed. `icons.can-complete`: The item that will be shown in the menu when the mission can be completed. `icons.completed`: The item that will be shown in the menu when the mission is completed.&#x20;

## Create your own mission jar

&#x20;In order to create your own missions jar, you must have knowledge in Java and the Spigot API.\
&#x20;Mission jars are part of the SuperiorSkyblock's API, which can be found [here](https://github.com/OmerBenGera/SuperiorSkyblockAPI).\
\
&#x20;In this tutorial, I will make a chat-mission that counts the amount of times a player has written "Hello".\
&#x20;First, I create a ChatMission object that extends the Mission object, and override all the methods.

```java
public final class ChatMission extends Mission<Object> {

    @Override
    public void load(JavaPlugin plugin, ConfigurationSection section) throws MissionLoadException {

    }

    @Override
    public double getProgress(SuperiorPlayer superiorPlayer) {
        return 0;
    }

    @Override
    public void onComplete(SuperiorPlayer superiorPlayer) {

    }

    @Override
    public void onCompleteFail(SuperiorPlayer superiorPlayer) {

    }

}
```

As you can see, the Mission object needs an argument. This argument will be our data. The Mission object has a built-in system to organize all the data for us. In this tutorial, I can just use the Integer class. In more complicated missions, you might want to use your own custom object.

```java
public final class ChatMission extends Mission<Integer> {

    ...

}
```

Now, we need to start implementing the default methods.\
`load()` - That's your "constructor" of the mission. It has two parameters: the plugin's instance, and the configurationsection of the mission. If something was not done correctly, and you want to cancel the loading of the mission - throw MissionLoadException with your error as a message. \
`getProgress()` - Calculates the progress of the player. Must return a number between 0 and 1. `onComplete()` - A callback method that will be ran when a player completes a mission. \
`onCompleteFail()` - A callback method that will be ran when a player fails to complete a mission.

```java
public final class ChatMission extends Mission<Integer> {

    private int AMOUNT_OF_TIMES = 0;
    private String CHAT_MESSAGE = "";

    @Override
    public void load(JavaPlugin plugin, ConfigurationSection section) throws MissionLoadException {
        if(!section.contains("times"))
            throw new MissionLoadException("Mission ChatMission must contain the \"times\" section!");

        if(!section.contains("message"))
            throw new MissionLoadException("Mission ChatMission must contain the \"message\" section!");

        AMOUNT_OF_TIMES = section.getInt("times");

        if(AMOUNT_OF_TIMES <= 0)
            throw new MissionLoadException("times must be a positive value.");

        CHAT_MESSAGE = section.getString("message").toLowerCase();
    }

    @Override
    public double getProgress(SuperiorPlayer superiorPlayer) {
        Integer count = get(superiorPlayer);
        return count == null ? 0D : (double) count / AMOUNT_OF_TIMES;
    }

    @Override
    public void onComplete(SuperiorPlayer superiorPlayer) {
        // There's nothing special to do here, so I will just clear data from the user.
        clearData(superiorPlayer);
    }

    @Override
    public void onCompleteFail(SuperiorPlayer superiorPlayer) {
        // Empty
    }

}
```

At this point, you can start listening to your events and alter the data when necessary. There's only one important thing to do, and it's to call the rewardMission() method. Furthermore, it's important to implement the saveProgress() and loadProgress() methods, so data will be saved on restarts.

The final product after adding a listener & registering it:

```java
public final class ChatMission extends Mission<Integer> implements Listener {

    private int AMOUNT_OF_TIMES = 0;
    private String CHAT_MESSAGE = "";

    @Override
    public void load(JavaPlugin plugin, ConfigurationSection section) throws MissionLoadException {
        if(!section.contains("times"))
            throw new MissionLoadException("Mission ChatMission must contain the \"times\" section!");

        if(!section.contains("message"))
            throw new MissionLoadException("Mission ChatMission must contain the \"message\" section!");

        AMOUNT_OF_TIMES = section.getInt("times");

        if(AMOUNT_OF_TIMES <= 0)
            throw new MissionLoadException("times must be a positive value.");

        CHAT_MESSAGE = section.getString("message").toLowerCase();

        Bukkit.getPluginManager().registerEvents(this, plugin);
    }

    @Override
    public double getProgress(SuperiorPlayer superiorPlayer) {
        Integer count = get(superiorPlayer);
        return count == null ? 0D : (double) count / AMOUNT_OF_TIMES;
    }

    @Override
    public void onComplete(SuperiorPlayer superiorPlayer) {
        // There's nothing special to do here, so I will just clear data from the user.
        clearData(superiorPlayer);
    }

    @Override
    public void onCompleteFail(SuperiorPlayer superiorPlayer) {
        // Empty
    }

    @EventHandler(priority = EventPriority.MONITOR, ignoreCancelled = true)
    public void onPlayerChat(AsyncPlayerChatEvent e){
        SuperiorPlayer superiorPlayer = SuperiorSkyblockAPI.getPlayer(e.getPlayer());;

        // Checking if the tracked message is in the player's message.
        if(!e.getMessage().toLowerCase().contains(CHAT_MESSAGE))
            return;

        // Making sure that the player can actually complete the mission, so we don't track data for no reason.
        if(!SuperiorSkyblockAPI.getMissions().canCompleteNoProgress(superiorPlayer, this))
            return;

        // Increasing the counter by 1.
        Integer currentCount = get(superiorPlayer);
        insertData(superiorPlayer, currentCount == null ? 1 : currentCount + 1);

        /* Calling the reward method with the following paramters:
            mission - this instance.
            superiorPlayer - our player.
            boolean - should the plugin check for auto reward or not.
         */
        SuperiorSkyblockAPI.getMissions().rewardMission(this, superiorPlayer, true);
    }

}
```

&#x20;More complicated missions will require more data to be tracked and more listeners.\
&#x20;Moreoever, I didn't implement the saveProgress() and loadProgress(), and didn't implement other useful methods that you might want to use.\
I recommend going through the Mission object before creating your own jar and see all the things it provides. If you want to see how the default mission jars are implemented, check out their [github repository](https://github.com/OmerBenGera/SuperiorSkyblock2-Missions/)!
