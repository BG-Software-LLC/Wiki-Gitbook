---
description: The plugin provides a few commands that can be used by your players.
---

# Commands and Permissions

## Commands

{% hint style="info" %}
Parameters inside `<>` are required, unlike parameters in `[]` which are optional.
{% endhint %}

### /tools give \<player-name> \<tool-name> \[amount] \[uses]

Gives a tool to a specific player.

#### Parameters

_player-name_: The name of the player to give the tool to.

_tool-name_: The name of the tool to give.\
Must be identical to the names in the config file.

_amount_: The amount of tools to give to the player.

_uses_: A predefined amount of uses for the given tool.

#### Permission

The permission to use the command is `wildtools.give`.



### /tools info \<tool-name>

Checks information about a tool.

#### Parameters

tool-name: The name of the tool to get information about.\
Must be identical to the names in the config file.

#### Permission

The permission to use the command is `wildtools.info`.



### /tools list

Get a list of all the available tools.

#### Permission

The permission to use the command is `wildtools.list`.



### /tools reload

Reload the settings and the language files.

#### Permission

The permission to use the command is `wildtools.reload`.



### /tools settings

Open in-game editor for tools.

#### Permission

The permission to use the command is `wildtools.settings`.

## Permissions

### wildtools.\*

Gives access to all the commands.

{% hint style="danger" %}
This gives access to reload the plugin and save command!
{% endhint %}

### wildtools.use

Gives access to use the custom tools.

{% hint style="info" %}
Players will not be able to use any of the tools without this permission.
{% endhint %}

### wildtools.sellmode

Gives access to use harvester sell mode.

{% hint style="info" %}
This is only required for the harvester-hoe's sell mode, and not sell wand themselves.
{% endhint %}
