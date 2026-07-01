# API

SuperiorSkyblock provides a powerful API, so you can make your own custom modules to the plugin, change behavior of the plugin, register custom commands and more!\
You can find the javadocs of the API [here](https://bg-software.com/superiorskyblock/api/).

## Basic Usage

All of the API methods can be accessed via the [SuperiorSkyblockAPI](https://github.com/BG-Software-LLC/SuperiorSkyblock2/blob/master/API/src/main/java/com/bgsoftware/superiorskyblock/api/SuperiorSkyblockAPI.java) class.\
The API contains lots of objects that are used as method parameters, and here I'll cover some of them:

[SuperiorPlayer](https://github.com/BG-Software-LLC/SuperiorSkyblock2/blob/master/API/src/main/java/com/bgsoftware/superiorskyblock/api/wrappers/SuperiorPlayer.java)\
This object is used as a warpper to the known player objects of the Bukkit's API. It contains data about the player, states of modes (fly mode etc) and more.\
You can retrieve the object using `SuperiorSkyblockAPI.getPlayer(<UUID>)`.\
\
[Island](https://github.com/BG-Software-LLC/SuperiorSkyblock2/blob/master/API/src/main/java/com/bgsoftware/superiorskyblock/api/island/Island.java)\
This object is used to cache data about the islands on your server. Members, banned list, multipliers, upgrades and all of the other data is stored in this object.\
You can get the Island of a player by using `SuperiorPlayer#getIsland()`.\
If you want to get an Island in a specific location, you can use `SuperiorSkyblockAPI.getGrid().getIslandAt(<Location>)`.\
\
[GridManager](https://github.com/BG-Software-LLC/SuperiorSkyblock2/blob/master/API/src/main/java/com/bgsoftware/superiorskyblock/api/handlers/GridManager.java)\
The grid manager object handles all the islands on your server. If you want to interact with islands, get them from the top list or anything related to that, you should use this object.

{% hint style="info" %}
Do not use methods that the Island object has (for example, the deleteIsland method), as it should only be used by the Island object itself.
{% endhint %}
