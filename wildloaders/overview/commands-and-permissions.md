---
description: The plugin provides a few commands that can be used by your players.
---

# Commands and Permissions

## Commands

{% hint style="info" %}
Parameters inside `<>` are required, unlike parameters in `[]` which are optional.
{% endhint %}

### /loader give \<player-name> \<loader-name> \[amount] \[time]

Gives a chunk loader to a specific player.

#### Parameters

_player-name_: The name of the player to give the loader to.

_loader-name_: The name of the loader to give.\
Must be identical to the names from the config file.

_amount_: The amount of loaders to give to the player.

_time_: The time left for the loader to work\
This arugment takes time in seconds. However, you can set one of the following chars after the amount to change it to other time units:\
`m` or `M` for minutes; `h` or `H` for hours; `d` or `D` for days.

{% hint style="info" %}
The argument `1d20h50m60` will give the loader a total time of 1 day, 20 hours, 50 minutes and 60 seconds.
{% endhint %}

#### Permission

The permission to use the command is `wildloaders.give`

### /loader list

Show all the available chunk loaders on the server.

#### Permission

The permission to use the command is `wildloaders.list`

## Permissions

### wildloaders.\*

Gives access to all the command.

### wildloaders.use

Gives access to place chunk-loaders.

{% hint style="info" %}
Without this permission, players will not be able to use chunk loaders.
{% endhint %}
