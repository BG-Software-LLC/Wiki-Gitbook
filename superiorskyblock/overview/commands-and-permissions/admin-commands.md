# Admin Commands

{% hint style="info" %}
Parameters inside `<>` are required, unlike parameters in `[]` which are optional.
{% endhint %}

### /island admin

List all available admin commands.

#### Permission

The permission to use the command is `superior.admin`

### /island admin add \<player-name / island-name> \<target-name>

Add a player to an island.

#### Parameters

_player-name_: The name of the player to add the target to his island.

_island-name_: The name of the island to add the target to.

_target-name_: The name of the target player to add.

#### Permission

The permission to use the command is `superior.admin.add`

### /island admin addbanklimit \<player-name / island-name / \*> \<limit>

Add a bank limit to an existing bank limit of an island.

#### Parameters

_player-name_: The name of the player to add bank limit to his island.

_island-name_: The name of the island to add bank limit to.

_\*_: Add bank limit to all islands on the server.

_limit_: The limit to add.

#### Permission

The permission to use the command is `superior.admin.addbanklimit`

### /island admin addblocklimit \<player-name / island-name / \*> \<material> \<limit>

Add a block limit to an existing block limit of an island.

#### Parameters

_player-name_: The name of the player to add block limit to his island.

_island-name_: The name of the island to add block limit to.

_\*_: Add block limits to all islands on the server.

_material_: The material to add block limit to.

_limit_: The limit to give to the block limit.

#### Permission

The permission to use the command is `superior.admin.addblocklimit`

### /island admin addbonus \<player-name / island-name / \*> \<worth/level> \<amount>

Add a bonus to an existing bonus of an island.

#### Parameters

_player-name_: The name of the player to add bonus to his island.

_island-name_: The name of the island to add bonus to.

_\*_: Add bonus to all islands on the server.

_worth_: Add bonus for the worth value of the island.

_level_: Add bonus for the level value of the island.

_amount_: The amount of bonus to add.

#### Permission

The permission to use the command is `superior.admin.addbonus`

### /island admin addcooplimit \<player-name / island-name / \*> \<limit>

Add a coop limit to an existing coop limit of an island.

#### Parameters

_player-name_: The name of the player to add coop limit to his island.

_island-name_: The name of the island to add coop limit to.

_\*_: Add coop limit to all islands on the server.

_limit_: The limit to add.

#### Permission

The permission to use the command is `superior.admin.addcooplimit`

### /island admin addcropgrowth \<player-name / island-name / \*> \<multiplier>

Add a crop-growth multiplier to an island.

#### Parameters

_player-name_: The name of the player to add crop growth to his island.

_island-name_: The name of the island to add crop growth to.

_\*_: Add crop growth to all islands on the server.

_multiplier_: The multiplier to add.

#### Permission

The permission to use the command is `superior.admin.addcropgrowth`

### /island admin adddisbands \<player-name> \<amount>

Add more disbands to a player.

#### Aliases

/island admin givedisbands \<player-name> \<amount>

#### Parameters

_player-name_: The name of the player to add disbands to.

_amount_: The amount of disbands to add.

#### Permission

The permission to use the command is `superior.admin.givedisbands`

### /island admin addentitylimit \<player-name / island-name / \*> \<entity> \<limit>

Add an entity limit to an existing entity limit of an island.

#### Parameters

_player-name_: The name of the player to add entity limit to his island.

_island-name_: The name of the island to add entity limit to.

_\*_: Add entity limit to all islands on the server.

_entity_: The name of the entity type to add limit to.

_limit_: The limit to add.

#### Permission

The permission to use the command is `superior.admin.addentitylimit`

### /island admin addeffect \<player-name / island-name / \*> \<effect> \<level>

Add an island effect to an existing effect level for an island.

#### Parameters

_player-name_: The name of the player to add island effect to his island.

_island-name_: The name of the island to add island effect to.

_\*_: Add island effect to all islands on the server.

_effect_: The effect to add.

_level_: The level of the effect to add.

#### Permission

The permission to use the command is `superior.admin.addeffect`

### /island admin addgenerator \<player-name / island-name / \*> \<material> \<value> \[world]

Add generator rates to an existing rates of an island.

#### Parameters

_player-name_: The name of the player to add generator rate to his island.

_island-name_: The name of the island to add generator rate to.

_\*_: Add generator rate to all islands on the server.

_material_: The block to add rates to.

_value_: The rate to add.

_world_: The world to add rates in.

#### Permission

The permission to use the command is `superior.admin.addgenerator`

### /island admin addmobdrops \<player-name / island-name / \*> \<multiplier>

Add a mob-drops multiplier to an island.

#### Parameters

_player-name_: The name of the player to add mob drops to his island.

_island-name_: The name of the island to add mob drops to.

_\*_: Add mob drops to all islands on the server.

_multiplier_: The multiplier to add.

#### Permission

The permission to use the command is `superior.admin.addmobdrops`

### /island admin addsize \<player-name / island-name> \<size>

Add a border size to an existing border size of an island.

#### Parameters

_player-name_: The name of the player to add border size to his island.

_island-name_: The name of the island to add border size to.

_size_: The size of border to add.

#### Permission

The permission to use the command is `superior.admin.addsize`

### /island admin addspawnerrates \<player-name / island-name / \*> \<multiplier>

Add a spawner-rate multiplier to an island.

#### Parameters

_player-name_: The name of the player to add spawner rates to his island.

_island-name_: The name of the island to add spawner rates to.

_\*_: Add spawner rates to all islands on the server.

_multiplier_: The multiplier to add.

#### Permission

The permission to use the command is `superior.admin.addspawnerrates`

### /island admin addteamlimit \<player-name / island-name / \*> \<limit>

Add a members limit to an existing members limit of an island.

#### Parameters

_player-name_: The name of the player to add members limit to his island.

_island-name_: The name of the island to add members limit to.

_\*_: Add members limit to all islands on the server.

_limit_: The limit to add.

#### Permission

The permission to use the command is `superior.admin.addteamlimit`

### /island admin addwarpslimit \<player-name / island-name / \*> \<limit>

Add a warps limit to an existing warps limit of an island.

#### Parameters

_player-name_: The name of the player to add warps limit to his island.

_island-name_: The name of the island to add warps limit to.

_\*_: Add warps limit to all islands on the server.

_limit_: The limit to add.

#### Permission

The permission to use the command is `superior.admin.addwarpslimit`

### /island admin bypass

Enable bypass mode.\
While in bypass mode, you can bypass all island protections.

#### Permission

The permission to use the command is `superior.admin.bypass`

### /island admin chest \<player-name / island-name>

Open an island chest of a specific island.

#### Parameters

_player-name_: The name of the player to open island chest of his island.

_island-name_: The name of an island to open island chest of.

#### Permission

The permission to use the command is `superior.admin.chest`

### /island admin cleargenerator \<player-name / island-name / \*> \[world]

Clear generator rates from an island.

#### Aliases

/island admin cg \<player-name / island-name / \*> \[world]

#### Parameters

_player-name_: The name of the player to clear generator rates from his island.

_island-name_: The name of the island to clear generator rates from.

_\*_: Clear generator rates from all islands on the server.

_world_: The world to clear rates in.

#### Permission

The permission to use the command is `superior.admin.cleargenerator`

### /island admin close \<player-name / island-name>

Close an island to the public.

#### Aliases

/island admin lock \<player-name / island-name>

#### Parameters

_player-name_: The name of the player to close his island.

_island-name_: The name of an island to close.

#### Permission

The permission to use the command is `superior.admin.close`

### /island admin cmdall \<player-name / island-name / \*> \<online-filter=true/false> \<command>

Execute a command on all the island members of an island.

#### Parameters

_player-name_: The name of the player to execute a command on his island's members.

_island-name_: The name of the island to execute a command on its members.

_online-filter_: Whether to execute the command only on online island members.

_command_: The command to execute\
You can use `{player-name}` as a placeholder for the island member's name.

#### Permission

The permission to use the command is `superior.admin.cmdall`

### /island admin count \<player-name / island-name> \[material]

Check block counts of an island.

#### Parameters

_player-name_: The name of the player to check block counts of his island.

_island-name_: The name of the island to check block counts of.

_material_: Check a specific count of a block.

#### Permission

The permission to use the command is `superior.admin.count`

### /island admin data \<get/set/remove> \<player/island> \<player-name / island-name> \[path] \[value]

Interact with persistent data of players or islands.

#### Parameters

_get/set/remove_: Whether to read, write or delete persistent data.

_player/island_: Whether to interact with data of a player or an island.

_player-name_: The name of the player to interact with his data.

_island-name_: The name of the island to interact with its data.

_path_: The path of the data. Optional for `get` and `remove`, required for `set`.

_value_: The value to set. Required for `set`.

#### Permission

The permission to use the command is `superior.admin.data`

### /island admin debug \[filter]

Toggle debug outputs.

#### Parameters

_filter_: Show only debug outputs of a specific debug type.

#### Permission

The permission to use the command is `superior.admin.debug`

### /island admin delwarp \<player-name / island-name> \<warp-name>

Delete a warp for an island.

#### Parameters

_player-name_: The name of the player to delete a warp for his island.

_island-name_: The name of the island to delete a warp for.

_warp-name_: The name of the warp to delete.

#### Permission

The permission to use the command is `superior.admin.delwarp`

### /island admin demote \<player-name>

Demote a player in his island.

#### Parameters

_player-name_: The name of the player to demote.

#### Permission

The permission to use the command is `superior.admin.demote`

### /island admin deposit \<player-name / island-name / \*> \<amount>

Deposit money to the island bank of an island.

#### Parameters

_player-name_: The name of the player to deposit money to his island.

_island-name_: The name of the island to deposit money to.

_\*_: Deposit money to all islands.

_amount_: The amount of money to deposit.

#### Permission

The permission to use the command is `superior.admin.deposit`

### /island admin disband \<player-name / island-name>

Disband an island.

#### Parameters

_player-name_: The name of the player to disband his island.

_island-name_: The name of the island to disband.

#### Permission

The permission to use the command is `superior.admin.disband`

### /island admin fly \<player-name> \[true/false]

Toggle island fly for a player.

#### Parameters

_player-name_: The name of the player to toggle island fly for.

_true/false_: Whether to enable or disable island fly. When omitted, the mode is toggled.

#### Permission

The permission to use the command is `superior.admin.fly`

### /island admin ignore \<player-name / island-name>

Ignore an island from being displayed in the top islands.

#### Parameters

_player-name_: The name of the player to ignore his island.

_island-name_: The name of the island to ignore.

#### Permission

The permission to use the command is `superior.admin.ignore`

### /island admin join \<player-name / island-name>

Join to an island without an invitation.

#### Parameters

_player-name_: The name of the player to join his island.

_island-name_: The name of the island to join.

#### Permission

The permission to use the command is `superior.admin.join`

### /island admin kick \<player-name>

Kick a player from his island.

#### Parameters

_player-name_: The name of the player to kick from his island.

#### Permission

The permission to use the command is `superior.admin.kick`

### /island admin mission \<player-name> \<complete/reset> \<mission-name>

Complete or reset a mission for a player.

#### Parameters

_player-name_: The name of the player to manage the mission to.

_complete_: Complete the mission for the player.

_reset_: Reset the mission for the player.

_mission-name_: The name of the mission to manage.

#### Permission

The permission to use the command is `superior.admin.mission`

### /island admin modules \[module-name] \[load/unload]

Manage the installed modules.

#### Parameters

_module-name_: The name of the module to manager.

_load_: Load a module from the folder.

_unload_: Unload a module from the server.

#### Permission

The permission to use the command is `superior.admin.modules`

### /island admin msg \<player-name> \<message>

Send a message to a player without prefixes.

#### Parameters

_player-name_: The name of the player to send a message.

_message_: The message to send to the player.

#### Permission

The permission to use the command is `superior.admin.msg`

### /island admin msgall \<player-name / island-name / \*> \<message>

Send a message to all island members of an island without prefixes.

#### Parameters

_player-name_: The name of the player to send a message to his island's members.

_island-name_: The name of the island to send a message to its members.

_\*_: Send a message to all players on the server.

_message_: The message to send to the player.

#### Permission

The permission to use the command is `superior.admin.msgall`

### /island admin name \<player-name / island-name> \<name>

Set a name to an island.

#### Aliases

/island admin setname \<player-name / island-name> \<name>

/island admin rename \<player-name / island-name> \<name>

#### Parameters

_player-name_: The name of the player to rename his island.

_island-name_: The name of the island to rename.

_name_: The name to set to the island.

#### Permission

The permission to use the command is `superior.admin.name`

### /island admin open \<player-name / island-name>

Open an island to the public.

#### Aliases

/island admin unlock \<player-name / island-name>

#### Parameters

_player-name_: The name of the player to open his island.

_island-name_: The name of the island to open.

#### Permission

The permission to use the command is `superior.admin.open`

### /island admin openmenu \<player-name> \<menu>

Open a menu for a player.

Aliases

/island admin menu \<player-name> \<menu>

#### Parameters

_player-name_: The name of the player to open a menu for.

_menu_: The name of the menu to open.

#### Permission

The permission to use the command is `superior.admin.openmenu`

### /island admin promote \<player-name>

Promote a player on his island.

#### Parameters

_player-name_: The name of the player to promote.

#### Permission

The permission to use the command is `superior.admin.promote`

### /island admin purge \<cancel/time>

Purge all inactive islands on the server.

#### Parameters

cancel: Cancel the next purge.

time: The time of inactivity of islands to purge, in seconds.

#### Permission

The permission to use the command is `superior.admin.purge`

### /island admin rankup \<player-name / island-name / \*> \<upgrade-name>

Rankup an upgrade for an island.

#### Parameters

_player-name_: The name of the player to rankup an upgrade for his island.

_island-name_: The name of the island to rankup an upgrade for.

_\*_: Rankup an upgrade for all islands on the server.

_upgrade-name_: The name of the upgrade to rankup.

#### Permission

The permission to use the command is `superior.admin.rankup`

### /island admin recalc \[player-name / island-name]

Recalculate worth and level values for an island.

#### Aliases

/island admin recalculate \[player-name / island-name]

/island admin level \[player-name / island-name]

#### Parameters

_player-name_: The name of the player to recalculate his island.

_island-name_: The name of the island to recalculate.

#### Permission

The permission to use the command is `superior.admin.recalc`

### /island admin reload

Reload all config files and language files.

#### Permission

The permission to use the command is `superior.admin.reload`

### /island admin removeblocklimit \<player-name / island-name / \*> \<material>

Remove a block limit of a block for an island.

#### Aliases

/island admin remblocklimit \<player-name / island-name / \*> \<material>

#### Parameters

_player-name_: The name of the player to remove block limit from his island.

_island-name_: The name of the island to remove block limit from.

_\*_: Remove block limit from all islands.

_material_: The block to remove limit to.

#### Permission

The permission to use the command is `superior.admin.removeblocklimit`

### /island admin removeentitylimit \<player-name / island-name / \*> \<entity>

Remove an entity limit of an entity for an island.

#### Aliases

/island admin rementitylimit \<player-name / island-name / \*> \<entity>

#### Parameters

_player-name_: The name of the player to remove entity limit from his island.

_island-name_: The name of the island to remove entity limit from.

_\*_: Remove entity limit from all islands.

_entity_: The entity to remove limit of.

#### Permission

The permission to use the command is `superior.admin.removeentitylimit`

### /island admin removeratings \<player-name / island-name / \*>

Remove all ratings for an island, or remove ratings of a player from all islands.

#### Aliases

/island admin rratings \<player-name / island-name / \*>

/island admin rr \<player-name / island-name / \*>

#### Parameters

_player-name_: The name of the player to remove his ratings from all islands.

_island-name_: The name of the island to remove all ratings from.

_\*_: Remove ratings from all islands.

#### Permission

The permission to use the command is `superior.admin.removeratings`

### /island admin resetpermissions \<player-name / island-name / \*>

Reset all island permissions for an island.

#### Parameters

_player-name_: The name of the player to reset island permissions for his island.

_island-name_: The name of the island to reset island permissions for.

_\*_: Reset island permissions for all islands.

#### Permission

The permission to use the command is `superior.admin.resetpermissions`

### /island admin resetsettings \<player-name / island-name / \*>

Reset all island settings for an island.

#### Parameters

_player-name_: The name of the player to reset island settings for his island.

_island-name_: The name of the island to reset island settings for.

_\*_: Reset island settings for all islands.

#### Permission

The permission to use the command is `superior.admin.resetsettings`

### /island admin resetworld \<player-name / island-name / \*> \<world>

Reset a world for an island.

#### Aliases

/island admin rworld \<player-name / island-name / \*> \<world>

#### Parameters

_player-name_: The name of the player to reset a world for his island.

_island-name_: The name of the island to reset a world for.

_\*_: Reset a world for all islands.

_world_: The world to reset.\
Should be `normal`, `nether` or `the_end`. The world cannot be the default world.

#### Permission

The permission to use the command is `superior.admin.resetworld`

### /island admin schematic \[schematic-name] \[save-air]

Toggle schematic mode.\
While in schematic mode, you can create new schematics.

#### Aliases

/island admin schem \[schematic-name] \[save-air]

#### Parameters

_schematic-name_: Save a schematic with the given name.

_save-air_: Whether to save air blocks in the schematic (`true`/`false`).

#### Permission

The permission to use the command is `superior.admin.schematic`

### /island admin setbanklimit \<player-name / island-name / \*> \<limit>

Set a bank limit for an island.

#### Parameters

_player-name_: The name of the player to set bank limit to his island.

_island-name_: The name of the island to set bank limit to.

_\*_: Set bank limit to all islands.

_limit_: The limit to set.

#### Permission

The permission to use the command is `superior.admin.setbanklimit`

### /island admin setbiome \<player-name / island-name / \*> \<biome>

Set a biome for an island.

#### Aliases

/island admin biome \<player-name / island-name / \*> \<biome>

#### Parameters

_player-name_: The name of the player to set biome to his island.

_island-name_: The name of the island to set biome to.

_\*_: Set biome to all islands.

_biome_: The biome to set.

#### Permission

The permission to use the command is `superior.admin.setbiome`

### /island admin setblockamount \<world> \<x> \<y> \<z> \<amount>

Set an amount for a stacked block.

#### Aliases

/island admin setblocksize \<world> \<x> \<y> \<z> \<amount>

#### Parameters

_world_: The world of the stacked block.

_x_: The x-coords of the stacked block.

_y_: The y-coords of the stacked block.

_z_: The z-coords of the stacked block.

_amount_: The amount to set to the stacked block.

#### Permission

The permission to use the command is `superior.admin.setblockamount`

### /island admin setblocklimit \<player-name / island-name / \*> \<material> \<limit>

Set a block limit of a block for an island.

#### Parameters

_player-name_: The name of the player to set block limit to his island.

_island-name_: The name of the island to set block limit to.

_\*_: Set block limit to all islands.

_material_: The block to set the limit to.

_limit_: The limit to set.

#### Permission

The permission to use the command is `superior.admin.setblocklimit`

### /island admin setbonus \<player-name / island-name / \*> \<worth/level> \<bonus>

Set a bonus for an island.

#### Aliases

/island admin bonus \<player-name / island-name / \*> \<worth/level> \<bonus>

#### Parameters

_player-name_: The name of the player to set bonus to his island.

_island-name_: The name of the island to set bonus to.

_\*_: Set bonus to all islands.

_worth_: Set the bonus to the worth value of the island.

_level_: Set the bonus to the level value of the island.

_bonus_: The bonus to set.

#### Permission

The permission to use the command is `superior.admin.bonus`

### /island admin setchestrow \<player-name / island-name / \*> \<page> \<rows>

Set number of rows to a chest page for an island.

#### Parameters

_player-name_: The name of the player to set chest rows to his island.

_island-name_: The name of the island to set chest rows to.

_\*_: Set chest rows to all islands.

_page_: The page to set rows to.

_rows_: The amount of rows to set.

#### Permission

The permission to use the command is `superior.admin.setchestrow`

### /island admin setcooplimit \<player-name / island-name / \*> \<limit>

Set a coop limit for an island.

#### Parameters

_player-name_: The name of the player to set coop limit to his island.

_island-name_: The name of the island to set coop limit to.

_\*_: Set coop limit to all islands.

_limit_: The limit set.

#### Permission

The permission to use the command is `superior.admin.setcooplimit`

### /island admin setcropgrowth \<player-name / island-name / \*> \<multiplier>

Set a crop-growth multiplier to an island.

#### Parameters

_player-name_: The name of the player to set crop growth to his island.

_island-name_: The name of the island to set crop growth to.

_\*_: Set crop growth to all islands on the server.

_multiplier_: The multiplier to set.

#### Permission

The permission to use the command is `superior.admin.setcropgrowth`

### /island admin setdisbands \<player-name / \*> \<amount>

Set the amount of disbands for a player.

#### Parameters

_player-name_: The name of the player to set disbands to.

_\*_: Set disbands to all players.

_amount_: The amount of disbands to set.

#### Permission

The permission to use the command is `superior.admin.setdisbands`

### /island admin seteffect \<player-name / island-name / \*> \<effect> \<level>

Set an island effect to an existing effect level for an island.

#### Parameters

_player-name_: The name of the player to set island effect to his island.

_island-name_: The name of the island to set island effect to.

_\*_: Set island effect to all islands on the server.

_effect_: The effect to set.

_level_: The level of the effect to set.

#### Permission

The permission to use the command is `superior.admin.seteffect`

### /island admin setentitylimit \<player-name / island-name / \*> \<entity> \<limit>

Set an entity limit of an entity to an island.

#### Parameters

_player-name_: The name of the player to set entity limit to his island.

_island-name_: The name of the island to set entity limit to.

_\*_: Set entity limit to all islands.

_entity_: The entity to set limit to.

_limit_: The limit set.

#### Permission

The permission to use the command is `superior.admin.setentitylimit`

### /island admin setgenerator \<player-name / island-name / \*> \<material> \<value> \[world]

Set generator rates to an island.

#### Parameters

_player-name_: The name of the player to set generator rate to his island.

_island-name_: The name of the island to set generator rate to.

_\*_: Set generator rate to all islands on the server.

_material_: The block to set rates to.

_value_: The rate to set.

_world_: The world to set rates in.

#### Permission

The permission to use the command is `superior.admin.setgenerator`

### /island admin setislandpreview \<schematic-name>

Set the preview location for an island schematic.

#### Aliases

/island admin setschematicpreview \<schematic-name>

#### Parameters

_schematic-name_: The name of the schematic to set the preview location for.

#### Permission

The permission to use the command is `superior.admin.setislandpreview`

### /island admin setleader \<leader> \<new-leader>

Change leadership of an island.

#### Parameters

_leader_: The name of the current island leader.

_new-leader_: The name of the new leader to set.

#### Permission

The permission to use the command is `superior.admin.setleader`

### /island admin setmobdrops \<player-name / island-name / \*> \<multiplier>

Set a mob-drops multiplier to an island.

#### Parameters

_player-name_: The name of the player to set mob drops to his island.

_island-name_: The name of the island to set mob drops to.

_\*_: Set mob drops to all islands on the server.

_multiplier_: The multiplier to set.

#### Permission

The permission to use the command is `superior.admin.setmobdrops`

### /island admin setpermission \<player-name / island-name / \*> \<permission> \<island-role>

Change permission for an island-role for an island.

#### Aliases

/island admin setperm \<player-name / island-name / \*> \<permission> \<island-role>

#### Parameters

_player-name_: The name of the player to change permission to his island.

_island-name_: The name of the island to change permission to.

_\*_: Change permission to all islands.

_permission_: The permission to change.

_island-role_: The new island role that will have the permission.

#### Permission

The permission to use the command is `superior.admin.setpermission`

### /island admin setrate \<player-name / island-name> \<target> \<rating>

Change rating of a player to an island.

#### Parameters

_player-name_: The name of the player to change rating to his island.

_island-name_: The name of the island to change rating to.

_target_: The name of the player to change his rating.

_rating_: The new rating to set.

#### Permission

The permission to use the command is `superior.admin.setrate`

### /island admin setrolelimit \<player-name / island-name / \*> \<island-role> \<limit>

Set a role limit to an island.

#### Parameters

_player-name_: The name of the player to set role limit to his island.

_island-name_: The name of the island to set role limit to.

_\*_: Set role limit to all islands.

_island-role_: The role to set limit to.

_limit_: The limit to set.

#### Permission

The permission to use the command is `superior.admin.setrolelimit`

### /island admin setsettings \<player-name / island-name / \*> \<island-flag> \<true/false>

Change island-flag for an island.

#### Parameters

_player-name_: The name of the player to change island flag to his island.

_island-name_: The name of the island to change island flag to.

_\*_: Change island flags to all islands.

_island-flag_: The island-flag to change.

_true_: Enable the island flag on the island.

_false_: Disable the island flag on the island.

#### Permission

The permission to use the command is `superior.admin.setsettings`

### /island admin setsize \<player-name / island-name / \*> \<size>

Set the border size of an island.

#### Aliases

/island admin setislandsize \<player-name / island-name / \*> \<size>

/island admin setbordersize \<player-name / island-name / \*> \<size>

#### Parameters

_player-name_: The name of the player to set border size to his island.

_island-name_: The name of the island to set border size to.

_\*_: Set border size to all islands.

_size_: The size of border to set.

#### Permission

The permission to use the command is `superior.admin.setsize`

### /island admin setspawn

Change the spawn location of the plugin.

#### Permission

The permission to use the command is `superior.admin.setspawn`

### /island admin setspawnerrates \<player-name / island-name / \*> \<multiplier>

Set a spawner-rate multiplier to an island.

#### Parameters

_player-name_: The name of the player to set spawner rates to his island.

_island-name_: The name of the island to set spawner rates to.

_\*_: Set spawner rates to all islands on the server.

_multiplier_: The multiplier to set.

#### Permission

The permission to use the command is `superior.admin.setspawnerrates`

### /island admin setteamlimit \<player-name / island-name / \*> \<limit>

Set the members limit of an island.

#### Parameters

_player-name_: The name of the player to set members limit to his island.

_island-name_: The name of the island to set members limit to.

_\*_: Set members limit to all islands.

_limit_: The limit to set.

#### Permission

The permission to use the command is `superior.admin.setteamlimit`

### /island admin settings

Open an in-game config editor.

#### Permission

The permission to use the command is `superior.admin.settings`

### /island admin setupgrade \<player-name / island-name> \<upgrade-name> \<level>

Set level of an upgrade for an island.

#### Parameters

_player-name_: The name of the player to set upgrade level to his island.

_island-name_: The name of the island to set upgrade level to.

_upgrade_: The name of the upgrade to set its level.

_level_: The level to set.

#### Permission

The permission to use the command is `superior.admin.setupgrade`

### /island admin setwarpslimit \<player-name / island-name / \*> \<limit>

Set the warps limit of an island.

#### Parameters

_player-name_: The name of the player to set warps limit to his island.

_island-name_: The name of the island to set warps limit to.

_\*_: Set warps limit to all islands.

_limit_: The limit to set.

#### Permission

The permission to use the command is `superior.admin.setwarpslimit`

### /island admin show \<player-name / island-name>

Show information about an island.

#### Parameters

_player-name_: The name of the player to show information about his island.

_island-name_: The name of the island to show information about.

#### Permission

The permission to use the command is `superior.admin.show`

### /island admin spawn \[player-name]

Teleport to spawn.

#### Parameters

_player-name_: The name of the player to teleport.

#### Permission

The permission to use the command is `superior.admin.spawn`

### /island admin syncbonus \<player-name / island-name / \*> \<worth/level>

Sync the bonus of an island with the generated worlds.

#### Parameters

_player-name_: The name of the player to sync bonus for his island.

_island-name_: The name of the island to sync bonus for.

_\*_: Sync bonus for all islands.

_worth_: Sync the worth bonus of the island.

_level_: Sync the level bonus of the island.

#### Permission

The permission to use the command is `superior.admin.syncbonus`

### /island admin syncupgrades \<player-name / island-name / \*>

Sync the multipliers and limits of an island with the upgrades.\
It will remove any value that was set with a command from the island.

#### Parameters

_player-name_: The name of the player to sync upgrades for his island.

_island-name_: The name of the island to sync upgrades for.

_\*_: Sync upgrades or all islands.

#### Permission

The permission to use the command is `superior.admin.syncupgrades`

### /island admin spy

Toggle chat spy mode.\
While in spy mode, you can see messages of island-chats of other islands.

#### Permission

The permission to use the command is `superior.admin.spy`

### /island admin stats

Show statistics about the plugin.

#### Permission

The permission to use the command is `superior.admin.stats`

### /island admin teleport \<player-name / island-name> \[normal/nether/the\_end]

Teleport to an island.

#### Aliases

/island admin tp \<player-name / island-name> \[normal/nether/the\_end]

/island admin go \<player-name / island-name> \[normal/nether/the\_end]

/island admin visit \<player-name / island-name> \[normal/nether/the\_end]

#### Parameters

_player-name_: The name of the player to teleport to his island.

_island-name_: The name of the island to teleport to.

_normal_: Teleport to the overworld world of the island.

_nether_: Teleport to the nether world of the island.

_the\_end_: Teleport to the end world of the island.

#### Permission

The permission to use the command is `superior.admin.teleport`

### /island admin title \<player-name> \<fade-in> \<duration> \<fade-out> -title \[message] -subtitle \[message]

Send a title to a player.

#### Parameters

_player-name_: The name of the player to send the title to.

_fade-in_: The fade-in time of the title, in ticks.

_duration_: The duration time of the title, in ticks.

_fade-out_: The fade-out time of the title, in ticks.

_title_: The title contents to send.

_subtitle_: The subtitle contents to send.

#### Permission

The permission to use the command is `superior.admin.title`

### /island admin titleall \<player-name / island-name / \*> \<fade-in> \<duration> \<fade-out> -title \[message] -subtitle \[message]

Send a title to all island members of an island.

#### Parameters

_player-name_: The name of the player to send the title to his island's members.

_island-name_: The name of the island to send the title to its members.

_\*_: Send the title to all the players.

_fade-in_: The fade-in time of the title, in ticks.

_duration_: The duration time of the title, in ticks.

_fade-out_: The fade-out time of the title, in ticks.

_title_: The title contents to send.

_subtitle_: The subtitle contents to send.

#### Permission

The permission to use the command is `superior.admin.titleall`

### /island admin unignore \<player-name / island-name>

Remove an island from being ignored from the top islands.

#### Parameters

_player-name_: The name of the player to unignore his island.

_island-name_: The name of the island to unignore.

#### Permission

The permission to use the command is `superior.admin.unignore`

### /island admin unlockworld \<player-name / island-name / \*> \<normal/nether/the\_end> \<true/false>

Unlock a world for an island.

#### Aliases

/island admin world \<player-name / island-name / \*> \<normal/nether/the\_end> \<true/false>

/island admin uworld \<player-name / island-name / \*> \<normal/nether/the\_end> \<true/false>

#### Parameters

_player-name_: The name of the player to unlock a world for his island.

_island-name_: The name of the island to unlock a world for.

_\*_: Unlock a world to all islands.

_normal_: Unlock the overworld world for the island.

_nether_: Unlock the nether world for the island.

_the\_end_: Unlock the end world for the island.

_true_: Unlock the world for the island.

_false_: Lock the world for the island.

#### Permission

The permission to use the command is `superior.admin.world`

### /island admin withdraw \<player-name / island-name> \<amount>

Withdraw money from the island bank of an island.

#### Parameters

_player-name_: The name of the player to withdraw money from his island.

_island-name_: The name of the island to withdraw money from.

_amount_: The amount of money to withdraw.

#### Permission

The permission to use the command is `superior.admin.withdraw`
