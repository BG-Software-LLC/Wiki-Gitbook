---
description: The plugin provides a few commands that can be used by your players.
---

# Commands and Permissions

## Commands

{% hint style="info" %}
Parameters inside `<>` are required, unlike parameters in `[]` which are optional.
{% endhint %}

### /buster cancel \[\<player-name> / \<chunk> ]

Cancel yours or others active chunk busters.

#### Parameters

_player-name:_ The name of the player to cancel a buster for.\
The buster that will be cancelled is the buster that the player gets notification about.

_chunk:_ The chunk to cancel from being busted.\
The format for the chunk is `<world-name>,<x>,<z>`.&#x20;

#### Permission

The permission to use the command is `wildbuster.cancel` for letting players to cancel their own chunk busters. In order to cancel others' busters, use `wildbuster.cancel.other`.



### /buster give \<player-name> \<buster-name> \[amount]

Give a chunk buster to a player.

#### Parameters

_player-name:_ The name of the player to give the chunk buster to.

_buster-name:_ The name of the buster to give.\
The name must be identical to the one from the config file.

_amount:_ The amount of chunk busters to give to the player.

#### Permission

The permission to use the command is `wildbuster.give` for letting players give themselves chunk busters. In order to give to other players, use `wildbuster.give.other`.



### /buster reload&#x20;

Reload the configuration files.

#### Permission

The permission to use the command is `wildbuster.reload`.



### /buster save

Save all active chunk busters to disk.

Permission

The permission to use the command is `wildbuster.save`

## Permissions

### wildbuster.\*

Gives access to all commands and actions of the plugin.

{% hint style="danger" %}
This gives access to reload the plugin and save commands!
{% endhint %}

### wildbuster.use

Gives access for players to use chunk busters.

{% hint style="warning" %}
Without this permission, players will not be able to place chunk busters.
{% endhint %}
