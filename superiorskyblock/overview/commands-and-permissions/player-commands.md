# Player Commands

{% hint style="info" %}
Parameters inside `<>` are required, unlike parameters in `[]` which are optional.
{% endhint %}

### /island accept \[player-name / island-name]

Accept an invitation to an island from a player.

#### Aliases

/island join \[player-name / island-name]

#### Parameters

_player-name_: The name of the player to accept invite from.

_island-name_: The name of the island to accept invite from.

#### Permission

The permission to use the command is `superior.island.accept`

### /island balance \[player-name / island-name]

Check the balance of an island.

#### Aliases

/island bal \[player-name / island-name]

/island money \[player-name / island-name]

#### Parameters

player-name: The name of the player to get balance of his island.

island-name: The name of the island to get balance of.

#### Permission

The permission to use the command is `superior.island.balance`

### /island ban \<player-name>

Ban a player from your island.

#### Parameters:

player-name: The name of the player to ban from the island.

#### Permission

The permission to use the command is `superior.island.ban`

### /island bank \[logs]

Open the island's bank.

#### Parameters

_logs_: Open the bank transaction logs menu.

#### Permission

The permission to use the command is `superior.island.bank`

### /island bans

Open the banned players menu.

#### Aliases

/island banlist

#### Permission

The permission to use the command is `superior.island.bans`

### /island biome

Change the biome of the island.

#### Aliases

/island setbiome

#### Permission

The permission to use the command is `superior.island.biome`

### /island border \[border-color]

Change the border color of islands.

#### Parameters

_border-color_: The color to set to the border. When omitted, the border color menu is opened.

#### Permission

The permission to use the command is `superior.island.border`

### /island chest \[page]

Open the island's chest.

#### Aliases

/is vault \[page]

#### Parameters

_page_: The page to open.

#### Permission

The permission to use the command is `superior.island.chest`

### /island close

Close the island to the public.

#### Aliases

/is lock

#### Permission

The permission to use the command is `superior.island.close`

### /island coop \<player-name>

Add a player as a co-op to your island.

#### Aliases

/island trust \<player-name>

#### Parameters

_player-name_: The name of the player to add as co-op to your island.

#### Permission

The permission to use the command is `superior.island.coop`

### /island coops

Open the coops menu.

#### Permission

The permission to use the command is `superior.island.coops`

### /island counts \[player-name / island-name]

See block counts in an island.

#### Aliases

/island blocks \[player-name / island-name]

#### Parameters

_player-name_: The name of the player to check block counts in this island.

_island-name_: The name of the island to check block counts for.

#### Permission

The permission to use the command is `superior.island.counts`

### /island create \[island-name]

Create a new island. The schematic is chosen through the island creation menu.

#### Parameters

_island-name_: The name to give to the new island. Required only when `island-names.required-for-creation` is enabled in the config.

#### Permission

The permission to use the command is `superior.island.create`

### /island delwarp \<warp-name...>

Delete an island warp.

#### Parameters

_warp-name_: The name of the warp to delete.

#### Permission

The permission to use the command is `superior.island.delwarp`

### /island demote \<player-name>

Demote a member in your island.

#### Parameters

_player-name_: The name of the player to demote.

#### Permission

The permission to use the command is `superior.island.demote`

### /island deposit \<amount>

Deposit money into the island's bank.

#### Parameters

_amount_: The amount of money to deposit.

#### Permission

The permission to use the command is `superior.island.deposit`

### /island disband

Disband your island permanently.

#### Aliases

/island reset

/island delete

#### Permission

The permission to use the command is `superior.island.disband`

### /island expel \<player-name>

Kick a visitor from your island.

#### Parameters

_player-name_: The name of the player to expel.

#### Permission

The permission to use the command is `superior.island.expel`

### /island fly

Toggle island fly.

#### Permission

The permission to use the command is `superior.island.fly`

The permission is also checked when players join the server or switch worlds - island fly is automatically disabled for players without it.

### /island help \[page]

List of all available commands.

#### Parameters

_page_: The page of commands to show.

#### Permission

The permission to use the command is `superior.island.help`

### /island invite \<player-name>

Invite a player to your island.

#### Aliases

/island add \<player-name>

#### Parameters

_player-name_: The name of the player to invite.

#### Permission

The permission to use the command is `superior.island.invite`

### /island kick \<player-name>

Kick a player from your island.

#### Aliases

/island remove \<player-name>

#### Parameters

_player-name_: The player to kick from the island.

#### Permission

The permission to use the command is `superior.island.kick`

### /island lang

Change your personal language.

#### Aliases

/island language

#### Permission

The permission to use the command is `superior.island.lang`

### /island leave

Leave your island.

#### Permission

The permission to use the command is `superior.island.leave`

### /island members

Open the members menu.

#### Permission

The permission to use the command is `superior.island.members`

### /island mission complete \<mission-name>

Complete a mission.

#### Aliases

/island challenge complete \<mission-name>

#### Parameters

_mission-name_: The name of the mission to complete.

#### Permission

The permission to use the command is `superior.island.mission`

### /island missions \[mission-category]

Open the missions menu.

#### Aliases

/island challenges \[mission-category]

#### Parameters

_mission-category_: The name of the missions category to open directly.

#### Permission

The permission to use the command is `superior.island.missions`

### /island name \<island-name>

Change the name of your island.

#### Aliases

/island setname \<island-name>

/island rename \<island-name>

#### Parameters

island-name: The new name of the island to set.

#### Permission

The permission to use the command is `superior.island.name`

### /island open

Open the island to the public.

#### Aliases

/island unlock

#### Permission

The permission to use the command is `superior.island.open`

### /island panel \[members/visitors] \[toggle]

Open island panel.

#### Aliases

/island manager \[members/visitors] \[toggle]

/island cp \[members/visitors] \[toggle]

#### Parameters

_members/visitors_: Whether to open the `members` menu or the `visitors` menu.

_toggle_: Whether to make `/is` open the panel menu.

#### Permission

The permission to use the command is `superior.island.panel`

Opening the `members` menu also requires `superior.island.members`, and the `visitors` menu also requires `superior.island.visitors`.

### /island pardon \<player-name>

Unban a player from your island.

#### Aliases

/island unban \<player-name>

#### Parameters

_player-name_: The name of the player to unban from the island.

#### Permission

The permission to use the command is `superior.island.pardon`

### /island permissions \[player-name] \[reset]

Get all permissions for an island role or a player.

#### Aliases

/island perms \[player-name] \[reset]

/island setpermission \[player-name] \[reset]

/island setperm \[player-name] \[reset]

#### Parameters

_player-name_: The name of the player to change permissions.

_reset_: Whether to reset permissions for the island-role or player.

#### Permission

The permission to use the command is `superior.island.permissions`

### /island promote \<player-name>

Promote a member in your island.

#### Parameters

_player-name_: The name of the player to promote.

#### Permission

The permission to use the command is `superior.island.promote`

### /island rankup \<upgrade-name>

Level up an upgrade.

#### Parameters

_upgrade-name_: The name of the upgrade to rankup.

#### Permission

The permission to use the command is `superior.island.rankup`

### /island rate \[player-name / island-name]

Rate an island.

#### Parameters

_player-name_: The name of the player to rate his island.

_island-name_: The name of the island to rate.

#### Permission

The permission to use the command is `superior.island.rate`

### /island ratings

Show all island ratings.

#### Permission

The permission to use the command is `superior.island.ratings`

### /island recalc

Re-calculates the island worth.

#### Aliases

/island recalculate

/island level

#### Permission

The permission to use the command is `superior.island.recalc`

### /island setdiscord \<discord-tag>

Set the discord of the island.

#### Parameters

_discord-tag_: The discord tag of the island.

#### Permission

The permission to use the command is `superior.island.setdiscord`

### /island setpaypal \<email>

Set the paypal email of the island.

#### Parameters

_email_: The paypal email of the island.

#### Permission

The permission to use the command is `superior.island.setpaypal`

### /island setrole \<player-name> \<island-role>

Change the role of a player in your island.

#### Parameters

_player-name_: The name of the player to change the role to.

_island-role_: The island role to give to the player.

#### Permission

The permission to use the command is `superior.island.setrole`

### /island setteleport

Change the teleport location of your island.

#### Aliases

/island settp

/island setgo

/island sethome

#### Permission

The permission to use the command is `superior.island.setteleport`

### /island settings \[reset]

Open the settings menu.

#### Parameters

_reset_: Reset all island settings to their defaults.

#### Permission

The permission to use the command is `superior.island.settings`

### /island setwarp \<warp-name> \[warp-category]

Create a new island warp.

#### Parameters

_warp-name_: The name of the warp to set.

_warp-category_: The name of the category of the warp.

#### Permission

The permission to use the command is `superior.island.setwarp`

### /island show \[player-name / island-name]

Get information about an island.

#### Aliases

/island info

#### Parameters

_player-name_: The name of the player to get information about his island.

_island-name_: The name of the island to get information about.

#### Permission

The permission to use the command is `superior.island.show`

### /island team \[player-name / island-name]

Get information about island members status.

#### Aliases

/island showteam \[player-name / island-name]

/island online \[player-name / island-name]

#### Parameters

_player-name_: The name of the player to check members status of his island.

_island-name_: The name of the island to check members.

#### Permission

The permission to use the command is `superior.island.team`

### /island teamchat \[message]

Toggle team chat mode.

#### Aliases

/island chat \[message]

/island tc \[message]

#### Parameters

_message_: The message to send in the island-chat.

#### Permission

The permission to use the command is `superior.island.teamchat`

### &#x20;/island teleport

Teleport to your island.

#### Aliases

/island tp

/island go

/island home

#### Permission

The permission to use the command is `superior.island.teleport`

### /island toggle \<border/blocks>

Toggle island borders and stacked blocks placements.

#### Parameters

_border_: Toggle the island borders visiblility.

_blocks_: Toggle stacking of blocks.

#### Permission

The permission to use the command is `superior.island.toggle`

The permission to use the border toggle command is `superior.island.toggle.border`

The permission to use the blocks toggle command is `superior.island.toggle.blocks`

### /island top

Open top islands panel.

#### Permission

The permission to use the command is `superior.island.top`

### /island transfer \<player-name>

Transfer your island's leadership.

#### Aliases

/island leader \<player-name>

/island leadership \<player-name>

#### Parameters

_player-name_: The name of the player to transfer the leadership to.

#### Permission

The permission to use the command is `superior.island.transfer`

### /island uncoop \<player-name>

Remove a player from being a co-op in your island.

#### Aliases

/island untrust \<player-name>

#### Parameters

_player-name_: The name of the player to remove from being a co-op.

#### Permission

The permission to use the command is `superior.island.uncoop`

### /island upgrade

Open upgrades panel.

#### Aliases

/island upgrades

#### Permission

The permission to use the command is `superior.island.upgrade`

### /island value \[material]

Get the worth value of a block in your hand.

#### Parameters

_material_: Get the worth value of a specific material.

#### Permission

The permission to use the command is `superior.island.value`

### /island values \[player-name / island-name]

Open the values menu.

#### Parameters

_player-name_: The name of player to check values of blocks of his island.

_island-name_: The name of the island to check values of.

#### Permission

The permission to use the command is `superior.island.values`

### /island visit \<player-name / island-name>

Teleport to the visitors location of an island.

#### Parameters

_player-name_: The name of the player to visit his island.

_island-name_: The name of the island to visit.

#### Permission

The permission to use the command is `superior.island.visit`

### /island visitors

Open the visitors menu.

#### Permission

The permission to use the command is `superior.island.visitors`

### /island warp \[player-name / island-name] \[warp-name]

Warp to an island warp.

#### Parameters

_player-name_: The name of the player to warp to his island.

_island-name_: The name of the island to warp to.

_warp-name_: The name of warp to teleport to.

#### Permission

The permission to use the command is `superior.island.warp`

### /island warps

Open the warps menu.

#### Permission

The permission to use the command is `superior.island.warps`

### /island withdraw \<amount>

Withdraw money from your island's bank.

#### Parameters

amount: The amount of money to withdraw from your island bank.

#### Permission

The permission to use the command is `superior.island.withdraw`
