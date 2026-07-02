---
description: >-
  Permissions that can be assigned to members or roles, that give access to
  certain things in the island. You can remove permissions from being given by
  not having them inside the permissions menu.
---

# Island Privileges

## Built-in Privileges

{% hint style="info" %}
Some of the privileges below are not hardcoded in the plugin, but registered through the default configuration files: the [interactables.yml](configuration-files.md) file registers block-interaction privileges (`Interact`, `Use`, `Chest Access`, `Sign Interact`, `Farm Tramping`, `Turtle Egg Tramping`, `Pickup Lectern Book`), and the [entity-categories.yml](configuration-files.md) file registers entity-related privileges (`Animal Spawn`, `Animal Damage`, `Monster Spawn`, `Monster Damage`, `Allay Interact`, `Copper Golem Interact`, `Horse Interact`, `Nautilus Interact`, `Pickup Axolotl`, `Pickup Fish`, `Item Frame`, `Painting`, `Tamed Animal Damage`, `Minecart Place`, `Minecart Damage`). You can register your own custom privileges by adding new privilege names to these files, without writing any code.
{% endhint %}

**All**\
Gives access to all the permissions.\
Recommendation: Should only be given to island leaders.

**Allay Interact**\
Gives access to interact with allays inside the island

**Animal Breed**\
Gives access to breed animals inside the island.

**Animal Damage**\
Gives access to damage animals inside the island

**Animal Shear**\
Gives access to shear animals inside the island

**Animal Spawn**\
Gives access to spawn animals inside the island

**Ban Member**\
Gives access to ban members from the island

**Break**\
Gives access to break blocks inside the island

**Brush**\
Gives access to brush suspicious blocks inside the island (1.20+ servers only)

**Build**\
Gives access to build inside the island

**Change Name**\
Gives access to change the name of the island

**Chest Access**\
Gives access to access chests inside the island

**Chorus Fruit**\
Gives access to consume chorus fruits inside the island (1.9+ servers only)

**Close Bypass**\
Gives bypass to the lock island status

**Close Island**\
Gives access to close (lock) the island to the public

**Coop Member**\
Gives access to add a player as a coop-member to the island

**Copper Golem Interact**\
Gives access to interact with copper golems inside the island

**Delete Warp**\
Gives access to delete island warps

**Demote Members**\
Gives access to demote island members

**Deposit Money**\
Gives access to deposit money into the island's bank

**Disband Island**\
Gives access to disband the island

**Discord Show**\
Gives access to see the discord of the island

**Drop Items**\
Gives access to drop items inside the island

**Dye Sheep**\
Gives access to dye sheep inside the island

**Ender Pearl**\
Gives access to use ender pearls inside the island

**Entity Ride**\
Gives access to ride entities inside the island

**Expel Bypass**\
Gives bypass from being expelled from the island

**Expel Players**\
Gives the ability to expel players from the island

**Farm Tramping**\
Gives access to destroy farms (jump on them) inside the island

**Fertilize**\
Gives access to fertilize blocks around the island

**Fish**\
Gives access to fish inside the island

**Fly**\
Gives access to fly around the island

**Horse Interact**\
Gives access to interact with horses inside the island

**Ignite Creeper**\
Gives access to ignite creppers (using a flint and steal) inside the island

**Interact**\
Gives access to interact with blocks inside the island.\
The interactable blocks are configurable and can be found under the interactables.yml file.

**Invite Member**\
Gives access to invite new players into the island

**Island Chest**\
Gives access to the community chest of the island

**Item Frame**\
Gives access to break and interact with item frames inside the island

**Kick Member**\
Gives access to kick members from the island

**Leash**\
Gives access to leash mobs inside the island

**Minecart Damage**\
Gives access to damage vehicles inside the island

**Minecart Enter**\
Gives access to enter vehicles inside the island

**Minecart Open**\
Gives access to open vehicles inside the island

**Minecart Place**\
Gives access to place vehicles inside the island

**Monster Damage**\
Gives access to damage monsters inside the island

**Monster Spawn**\
Gives access to spawn monsters inside the island

**Name Entity**\
Gives access to nametag entities inside the island

**Nautilus Interact**\
Gives access to interact with nautiluses inside the island

**Open Island**\
Gives access to open (unlock) the island to the public

**Painting**\
Gives access to break paintings inside the island

**Paypal Show**\
Gives access to see the paypal of the island

**Pickup Axolotl**\
Gives access to pick up axolotls using a water bucket inside the island

**Pickup Drops**\
Gives access to pick up drops inside the island

**Pickup Fish**\
Gives access to pick up fish using a water bucket inside the island

**Pickup Lectern Book**\
Gives access to pick up books out of lecterns inside the island

**Promote Members**\
Gives access to promote members inside the island

**Rankup**\
Gives access to rankup upgrade levels

**Ratings Show**\
Gives access to see the ratings that were given to the island

**Saddle Entity**\
Gives access to add saddles to entities inside the island

**Sculk Sensor**\
Gives access to trigger sculk sensors inside the island (1.17+ servers only)

**Set Biome**\
Gives access to change the biome of the island

**Set Discord**\
Gives access to set the discord of the island

**Set Home**\
Gives access to set the teleport location of the island

**Set Paypal**\
Gives access to set the paypal of the island

**Set Permission**\
Gives access to change the permissions of the island

**Set Role**\
Gives access to set roles to members of the island

**Set Settings**\
Gives access to change the settings of the island

**Set Warp**\
Gives access to set new warps inside the island

**Sign Interact**\
Gives access to interact with signs inside the island

**Spawner Break**\
Gives access to break spawners inside the island

**Tamed Animal Damage**\
Gives access to damage tamed animals inside the island

**Turtle Egg Tramping**\
Gives access to break turtle eggs when standing on them inside the island

**Uncoop Member**\
Gives access to remove members from being coop from the island

**Use**\
Gives access to use blocks inside the island

**Valuable Break**\
Gives access to break valuable blocks inside the island

**Villager Trading**\
Gives access to trade with villagers inside the island

**Wind Charge**\
Gives access to use wind charges inside the island (1.21+ servers only)

**Withdraw Money**\
Gives access to withdraw money from the island's bank

## Create your own island privilege

&#x20;In order to create your own permission, you must have knowledge in Java and the Spigot API.\
&#x20;Alongside of these, you'll also need the SuperiorSkyblock's API, which can be found [here](https://github.com/OmerBenGera/SuperiorSkyblockAPI).\
\
&#x20;Island permissions are represented as a class called "IslandPrivilege", and it's really easy to register custom ones! In this tutorial, I will make a custom permission for breaking beacons inside islands.\
First, I register the custom permission by listening to the PluginInitializeEvent, and there I am calling the IslandPrivilege.register() method.

```java
public final class BeaconPlacePermission implements Listener {

    private static IslandPrivilege BEACON_BREAK;

    @EventHandler
    public void onPluginInit(PluginInitializeEvent e){
        IslandPrivilege.register("BEACON_BREAK");
        BEACON_BREAK = IslandPrivilege.getByName("BEACON_BREAK");
    }

}
```

{% hint style="info" %}
PluginInitializeEvent is called in the onEnable() method of SuperiorSkyblock. Therefore, you must have your plugin enabling before SuperiorSkyblock, which can be done by adding "SuperiorSkyblock2" as a depend/softdepend plugin.
{% endhint %}

After registering the custom permission, we can simply implement the restriction for breaking beacons!

```java
public final class BeaconPlacePermission implements Listener {

    private static IslandPrivilege BEACON_BREAK;

    @EventHandler
    public void onPluginInit(PluginInitializeEvent e){
        IslandPrivilege.register("BEACON_BREAK");
        BEACON_BREAK = IslandPrivilege.getByName("BEACON_BREAK");
    }
    
    @EventHandler
    public void onBlockBreak(BlockBreakEvent e){
        //Checking for beacons only.
        if(e.getBlock().getType() != Material.BEACON)
            return;

        Island island = SuperiorSkyblockAPI.getIslandAt(e.getBlock().getLocation());
        
        // Making sure the block was broken inside an island.
        if(island == null)
            return;
        
        if(!island.hasPermission(e.getPlayer(), BEACON_BREAK)){
            e.setCancelled(true);
            e.getPlayer().sendMessage("" + ChatColor.RED + ChatColor.BOLD + "Error | " + ChatColor.GRAY + "This island is protected.");
        }
    }

}
```

That's it! Now players must have the BEACON\_BREAK permission in order to mine beacons. You can simply add the new permission to the permissions menu, and edit it's display icon there, the same as the regular permissions.
