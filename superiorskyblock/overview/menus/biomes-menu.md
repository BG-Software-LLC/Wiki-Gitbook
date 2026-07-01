---
description: Here you'll find how to make your own biomes from scratch.
---

# Biomes Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Biomes Related Sections

The biomes menu have an additional section that can be configured - `current-biome-glow`, whether the current biome should be glowing or not.

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Biome Items

The biomes menu gives players the ability to change their island's biome to another. In order to achieve that, the menu must be configured with special type of buttons that will make this work.

These speical-type buttons do not follow the format of regular items and have custom sections that should be given to them.

| Field Name  | Field Type   | Description                                                                                |
| ----------- | ------------ | ------------------------------------------------------------------------------------------ |
| `biome`     | String       | The biome to change. List of biomes can be found [here](biomes-menu.md#general-sections).  |
| `access`    | Item-Section | The item that will be displayed when players have permission to change to the biome.       |
| `no-access` | Item-Section | The item that will be displayed when players don't have permission to change to the biome. |

{% hint style="info" %}
The `access` and `no-access` fields can be used in sounds and commands sections as well to achieve custom sounds/commands when having/not having permission to change to the biome.
{% endhint %}

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is an example of a biomes menu, which includes most of the technics and features stated in this tutorial.

{% embed url="https://gist.github.com/OmerBenGera/be693782389bfee0749fd6207e17bb66" %}
