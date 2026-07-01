---
description: The plugin provides a few commands that can be used by your players.
---

# Commands and Permissions

## Commands

{% hint style="info" %}
Parameters inside `<>` are required, unlike parameters in `[]` which are optional.
{% endhint %}

### /stacker give \<player-name> \<item> \<stack-type> \<stack-size>

Give a stacked spawner/spawn-egg/barrel to a player.

#### Parameters

_player-name_: The name of the player to give the item to.

_item_: The type of item to give to the player.\
Can be `spawner`, `egg` or `barrel`.

_stack-type_: The type of spawner, egg or a barrel to give to the player.\
If the item is `spawner` or `egg`, the `stack-type` should be an `entity-type`.\
If the item is a `barrel`, the `stack-type` should be a `block-type`.

_stack-size_: The stack-amount of the item.

#### Permission

The permission to use the command is `wildstacker.give`



### /stacker info

Shows information about a spawner you're looking at.

#### Permission

The permission to use the command is `wildstacker.info`



### /stacker inspect \<player-name> \[amount]

Give an inspect tool to a player.\
The inspect tool is used to get more information about a stacked entity or spawner.

#### Parameters

player-name: The name of the player to give the inspect tool.

amount: The amount of inspect tools to give to the player.

#### Permission

The permission to use the command is `wildstacker.inspect.give`



### /stacker kill \[radius=?] \[type=?] \[spawn=?] \[config\<true/false>]

Kill all the stacked mobs in the server.

#### Parameters

radius: The radius from player to kill entities.

type: The type of entities to kill.

spawn: The spawn-cause of the entities to kill.

config: Whether to respect kill limits from config or not.

{% hint style="warning" %}
Make sure you use the config parameter in caution.
{% endhint %}

#### Permission

The permission to use the command is `wildstacker.kill`



### /stacker reload

Reload the settings and the language files.

#### Permission

The permission to use the command is `wildstacker.reload`



/stacker save

Save cached data to disk.

#### Permission

The permission to use the command is `wildstacker.save`



### /stacker settings

Open the in-game config file editor.

#### Permission

The permission to use the command is `wildstacker.settings`



### /stacker simulate \<player-name> \[amount]

Give a simulate tool to a player.\
The simulate tool is used to check if two entities can stack together.

#### Parameters

player-name: The name of the player to give the simulate-tool to.

amount: The amount of simulate-tools to give to the player.

#### Permission

The permission to use the command is `wildstacker.simulate.give`



### /stacker stats

See all the cached data statistics of WildStacker.

#### Permission

The permission to use the command is `wildstacker.stats`



### /stacker test

Test the status of the stacking thread.\
If a stacking-thread is no longer active, this command will wake it up.

#### Permission

The permission to use the command is `wildstacker.test`

## Permissions

### wildstacker.\*

Gives access to all the commands of the plugin.

{% hint style="danger" %}
This gives access to reload the plugin and save command!
{% endhint %}

### wildstacker.silktouch

Gives access to mine spawners and get them dropped with silk-touch.

{% hint style="info" %}
Players must have this permission otherwise they will not get the dropped spawner after mining it with a silktouch pickaxe.
{% endhint %}

### wildstacker.nosilkdrop

Gives access to mine spawners and get them dropped without silk-touch.

{% hint style="info" %}
If you have drop-without-silk enabled in the config, players must have this permission otherwise they will not get the dropped spawner.
{% endhint %}

### wildstacker.place.\*

Gives access to place all spawner types.

{% hint style="info" %}
This permission will only work if you enabled placement-permission in the config.
{% endhint %}

### wildstacker.place.\<entity-type>

Gives access to place a specific spawner type.

{% hint style="info" %}
This permission will only work if you enabled placement-permission in the config.
{% endhint %}

### wildstacker.nextplace

Gives access to place spawners next to others.

{% hint style="info" %}
Players will only be able to place spawners next to each other if next-spawner-place is enabled in the config or they have this permission.
{% endhint %}

### wildstacker.charge.bypass

Gives the ability to bypass charging when placing or breaking spawners.
