---
description: The plugin provides a few commands that can be used by your players.
---

# Commands and Permissions

## Commands

{% hint style="info" %}
Parameters inside `<>` are required, unlike parameters in `[]` which are optional.
{% endhint %}

### /chests give \<player-name> \<chest-name> \[amount]

Give a custom chest to a player.

#### Parameters

_player-name_: The name of the player to give the chest to.

_chest-name_: The name of the chest to give.\
Must be identical to the names from the config file.

_amount_: The amount of the chest to give.

#### Permission

The permission to use the command is `wildchests.give`

### /chests info \<chest-name>

Shows information about a chest.

#### Parameters

_chest-name_: The name of the chest to get info about.\
Must be identical to the names from the config file.

#### Permission

The permission to use the command is `wildchests.info`

### /chests link

Links a linked chest into another chest.

#### Permission

The permission to use the command is `wildchests.link`

{% hint style="info" %}
Without this permission, players will not be able to link chests.
{% endhint %}

### /chests reload

Reload the settings and the language files.

#### Permission

The permission to use the command is `wildchests.reload`

### /chests save

Save all cached data into disk.

#### Permission

The permission to use the command is `wildchests.save`

### /chests settings

Open an in-game editor for chests.

#### Permission

The permission to use the command is `wildchests.settings`

## Permissions

### wildchests.\*

Gives access to all the commands.

{% hint style="danger" %}
This gives access to reload the plugin and save command!
{% endhint %}
