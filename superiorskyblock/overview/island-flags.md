---
description: >-
  Every island has settings (flags) that their island owners can modify. They
  are used to control different things on the island: fluid flow, lava, spawning
  and more!
---

# Island Flags

## Built-in Flags

**Always Day**\
Toggles time to always be day inside the island.\
This settings cannot work with other settings that change time.

**Always Middle Day**\
Toggles time to always be the middle of the day inside the island.\
This settings cannot work with other settings that change time.

**Always Night**\
Toggles time to always be night inside the island.\
This settings cannot work with other settings that change time.

**Always Middle Night**\
Toggles time to always be the middle of the night inside the island.\
This settings cannot work with other settings that change time.

**Always Rain**\
Toggles weather to always be rainy inside the island.\
This settings cannot work with other settings that change weather.

**Always Shiny**\
Toggles weather to always be shiny inside the island.\
This settings cannot work with other settings that change weather.

**Creeper Explosion**\
Toggles creeper explosions harming blocks inside the island.

**Crops Growth**\
Toggles growth of crops inside the island.

**Egg Lay**\
Toggles chickens laying eggs inside the island.

**Enderman Grief**\
Toggles endermans picking up blocks inside the island.

**Fire Spread**\
Toggles fire spread to other blocks inside the island.

**Ghast Fireball**\
Toggles fireballs harming blocks inside the island.

**Lava Flow**\
Toggles lava flowing inside the island.

**Natural Animals Spawn**\
Toggles natural spawning of animals inside the island.

**Natural Monster Spawn**\
Toggles natural spawning of monsters inside the island.

**PvP**\
Toggles pvp between players inside the island.\
When enabling the settings, all visitors will be teleported to spawn to prevent traps.

**Spawner Animals Spawn**\
Toggles spawner spawning animals inside the island.

**Spawner Monster Spawn**\
Toggles spawner spawning monsters inside the island.

**TNT Explosion**\
Toggles tnt explosions harming blocks inside the island.

**Tree Growth**\
Toggles growth of trees inside the island.

**Water Flow**\
Toggles water flowing inside the island.

**Wither Explosion**\
Toggles wither explosions harming blocks inside the island.

## Create your own island flag

&#x20;In order to create your own setting, you must have knowledge in Java and the Spigot API.\
&#x20;Alongside of these, you'll also need the SuperiorSkyblock's API, which can be found [here](https://github.com/OmerBenGera/SuperiorSkyblockAPI).

Island settings are represented as a class called "IslandFlag", and it's really easy to register custom ones! In this tutorial, I will make a custom setting for swimming. First, I register the custom setting by listening to the PluginInitializeEvent, and there I am calling the IslandFlag.register() method.

```java
public final class SwimmingFlag implements Listener {

    private static IslandFlag SWIMMING;

    @EventHandler
    public void onPluginInit(PluginInitializeEvent e){
        IslandFlag.register("SWIMMING");
        SWIMMING = IslandFlag.getByName("SWIMMING");
    }

}
```

{% hint style="info" %}
PluginInitializeEvent is called in the onEnable() method of SuperiorSkyblock. Therefore, you must have your plugin enabling before SuperiorSkyblock, which can be done by adding "SuperiorSkyblock2" as a depend/softdepend plugin.
{% endhint %}

After registering the custom flag, we can simply implement the restriction for swimming!

```java
public final class SwimmingFlag implements Listener {

    private static IslandFlag SWIMMING;

    @EventHandler
    public void onPluginInit(PluginInitializeEvent e){
        IslandFlag.register("SWIMMING");
        SWIMMING = IslandFlag.getByName("SWIMMING");
    }
    
    @EventHandler(ignoreCancelled = true)
    public void onPlayerMove(PlayerMoveEvent e){
        // First I check for movement between blocks
        if(e.getFrom().getBlockX() == e.getTo().getBlockX() && e.getFrom().getBlockY() == e.getTo().getBlockY() && 
                e.getFrom().getBlockZ() == e.getTo().getBlockZ())
            return;

        Island island = SuperiorSkyblockAPI.getIslandAt(e.getTo());
        
        // We make sure that swimming is disabled
        if(island == null || island.hasSettingsEnabled(SWIMMING))
            return;

        Block toBlock = e.getTo().getBlock();
        Block belowBlock = toBlock.getRelative(BlockFace.DOWN);
        
        // We check if the target block is water, or the block below it is water.
        if(toBlock.getType() == Material.WATER || (!toBlock.getType().isSolid() && belowBlock.getType() == Material.WATER)){
            e.setCancelled(true);
            e.getPlayer().sendMessage("" + ChatColor.RED + ChatColor.BOLD + "Error | " + ChatColor.GRAY + "This island has swimming disabled.");
        }
        
    }

}
```

That's it! Now players cannot enter water if the setting is disabled. You can simply add the new setting to the settings menu, and edit it's display icon there, the same as the regular settings.
