---
description: >-
  You can add different tools to the plugin by adding them to the config file.
  In this tutorial you'll see how it's done, what fields can be added and which
  tools are available.
---

# Configuring Tools

First thing to do is to give your tool a unique name. This name will later be used to give the tools to players with the give command. The name must be unique to your tool, and two tools cannot share the same name. After choosing one, add it to your config under the tools section:

```
tools:
  <tool-name>:
    ...
```

Second step is to choose the type of tool you want to create. There are plenty of different tools you can create, and each of them have a different action it can do:

#### BUILDER

The builder tool will place blocks for you upon clicking on a block in the same direction as the block's face you clicked on. The placed blocks will be taken from the player's inventory.\
Read more about it [here](builder-tool.md).

#### CANNON

The cannon tool will fill every dispenser in a selected area with TNT from your inventory or your TNT bank (Factions).\
Read more about it [here](cannon-tool.md).

#### CRAFTING

The crafting tool will craft items in a container upon clicking on it. You can configure which crafting recipes it can craft, and upon clicking a container - it will craft these items with the ingredients found in the container.\
Read more about it [here](crafting-tool.md).

#### CROWBAR

The crowbar tool can break spawners and drop the spawner item on ground by right clicking on a spawner.\
Read more about it [here](crowbar-tool.md).

#### CUBOID

The cuboid tool can break a cuboid shaped area with a single block-break. It will break all blocks in a configured range.\
Read more about it [here](cuboid-tool.md).

#### DRAIN

The drain tool will remove any ice block in its range.\
Read more about it [here](drain-tool.md).

#### HARVESTER

The harvester tool will harvest crops in range, plant them and even sell them automatically for the players.\
Read more about it [here](harvester-tool.md).

#### ICE

The ice tool will remove any ice block in it's range and replace it with water source blocks.\
Read more about it [here](ice-tool.md).

#### LIGHTNING

The lightning wand will strike a lightning on creepers and will make them powered.\
Read more about it [here](lightning-tool.md).

#### MAGNET

The magnet tool will make nearby items fly towards the player so he can collect them easily.\
Read more about it [here](magnet-tool.md).

#### PILLAR

The pillar tool will break blocks in a pillar shape, starting from the highest block to the bottom. It will only break blocks similar to the clicked block.\
Read more about it [here](pillar-tool.md).

#### SELL

The sell tool will sell items in your containers.\
Read more about it [here](sell-tool.md).

#### SORT

The sort tool will sort items in containers by their ids (similar order as in creative menu).\
Read more about it [here](sort-tool.md).

Once you chose your tool, you can add it to the config under the `tool-mode` section:

```
tools:
  <tool-name>:
    tool-mode: <tool>
```

## Tool Sections

In order to properly have your tool registered, you must add the required sections for each tool (These can be found on each tool's page), alongside of a material type for the tool. The `type` section is used for this purpose, and you need to choose a valid material for the tool.

{% hint style="info" %}
You can find a list of materials for your minecraft version on this website:\
[https://bg-software.com/materials/](https://bg-software.com/materials/)
{% endhint %}

Each tool can have optional sections besides the required ones, which can change the behavior of your tools. Here is the list of sections you can use:

### cooldown

Give a cooldown to your tool. Players can not use the tool while they are in cooldown.

#### Section Type

Long (Number, maximum of 9,223,372,036,854,775,807)

### auto-collect

When set, drops from tools will be auto-collected to the inventories of the players. If the players don't have enough space for the items, they will be dropped naturally on ground.

#### Section Type

Boolean (true/false)

### instant-break

When set, tools will instantly break blocks. The minecraft's breaking time will be instantly - similar to how stone blocks are broken using Haste II beacon.

#### Section Type

Boolean (true/false)

### silk-touch

When set, tools will act similar as they have a silk touch enchantment. In other words, this is an invinsible silk touch enchantment.

#### Section Type

Boolean (true/false)

### only-same-type

When set, tools will only be able to break the same type of block in a single mining.

#### Section Type

Boolean (true/false)

### only-inside-claim

When set, players will only be able to use tools inside their claims.\
Only supported claiming plugins will work.

#### Section Type

Boolean (true/false)

### unbreakable

When set, tools will not lose durability or uses.

#### Section Type

Boolean (true/false)

### vanilla-damage

When set, tools will lose damage when other vanilla actions cause it to take damage.\
For example, hitting a mob with a pickaxe will make the pickaxe lose damage.

#### Section Type

Boolean (true/false)

### uses

When set, tools will have a specific amount of uses instead of using vanilla's tool durability.

#### Section Type

Integer (Number, maximum of  2,147,483,647)

### keep-inventory

When set, tools will not dropped upon player's death.

#### Section Type

Boolean (true/false)

### name

The name of the tool's item.

#### Section Type

String

### lore

The lore of the tool's item.

#### Section Type

List

### glow

When set, the tool's item will glow as it is enchanted without any enchantments applied to it.

#### Section Type

Boolean (true/false)

### spigot-unbreakable

When set, spigot's unbreakable tag will be set to the tool's item.

#### Section Type

Boolean (true/false)

### custom-model

Custom model for the tool's item.\
Only available in 1.14+

{% hint style="info" %}
This type of data is used for custom textures on client-side resource packs.
{% endhint %}

#### Section Type

Integer (Number, maximum of 2,147,483,647)

### enchants

List of enchantments to be added to the tool's item.\
Each line represents an enchantment and level, split by `:`

{% hint style="info" %}
You can find a list of enchantments [on this website](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/enchantments/Enchantment.html).
{% endhint %}

#### Section Type

List

### blacklisted-blocks

List of blocks that cannot be broken by the tool.

#### Section Type

List

### whitelisted-blocks

List of blocks that the tool can break.

#### Section Type

List

### blacklisted-drops

List of drops that cannot be dropped by the tool.

#### Section Type

List

### whitelisted-drops

List of drops that the tool may drop.

#### Section Type

List

### multiplier

Set a multiplier for the outcome earnings from harvester tools and sell tools.

#### Section Type

Double (Decimal)

### omni-tool

When set, tools will change their type according to the blocks players try to break.

#### Section Type

Boolean (true/false)

### private

When set, tools can only be used by one player. The first player to use the tool will claim it and no other player will be able to use it.

#### Section Type

Boolean (true/false)

### uses-progress

When set, tools will have the vanilla's durability bar decreasing as they use the tool.\
It will reflect their uses percentage with the vanilla's durability bar.

#### Section Type

Boolean (true/false)

### anvil-combine-exp

The amount of exp required to combine this tool with another.

#### Section Type

Integer (Number, maximum of 2,147,483,647)

### anvil-combine-limit

The maximum uses a tool can have when combined in an anvil.

#### Section Type

Integer (Number, maximum of 2,147,483,647)

### blacklisted-worlds

List of worlds that the tool can not work inside.

#### Section Type

List

### whitelisted-worlds

List of worlds that the tool can only work inside.

#### Section Type

List

### notified-plugins

List of plugins that will get notified when using the tool.\
Similar to the `other-plugins` section in the config, just a custom list for the tool.

#### Section Type

List
