---
description: Here you'll find how to make your own missions menu from scratch.
---

# Missions Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Category Buttons

The missions menu displays the mission categories of the server. The slot of each category button is not set in this menu - it is determined by the `slot` field of the category in the `config.yml` file, under the `missions-categories` section. Clicking a category button opens the [missions category menu](missions-category-menu.md) for that category.

The items you configure in this menu are used as the visuals for the slots - place an item in the same slot as a category to give that category a custom look.

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default missions menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lMissions'
previous-menu: true

pattern:
  - '$ $ $ $ $ $ $ $ $'
  - '$ * * * * * * * $'
  - '$ * # @ % ^ & * $'
  - '$ * * * * * * * $'
  - '$ $ $ $ $ $ $ $ $'

items:
  '$':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'
  '#':
    type: DIAMOND_PICKAXE
    name: '&eMiner Missions'
    lore:
      - '&7Click to start your adventure as a Miner.'
    flags:
      - HIDE_ATTRIBUTES
  '@':
    type: SKULL_ITEM
    data: 2
    name: '&eSlayer Missions'
    lore:
      - '&7Click to start your adventure as a Slayer.'
  '%':
    type: WHEAT
    name: '&eFarmer Missions'
    lore:
      - '&7Click to start your adventure as a Farmer.'
  '^':
    type: FISHING_ROD
    name: '&eFisherman Missions'
    lore:
      - '&7Click to start your adventure as a Fisherman.'
  '&':
    type: MAP
    name: '&eExplorer Missions'
    lore:
      - '&7Click to start your adventure as an Explorer.'

sounds:
  '#':
    type: CHEST_OPEN
    volume: 0.8
    pitch: 1
  '@':
    type: CHEST_OPEN
    volume: 0.8
    pitch: 1
  '%':
    type: CHEST_OPEN
    volume: 0.8
    pitch: 1
  '^':
    type: CHEST_OPEN
    volume: 0.8
    pitch: 1
  '&':
    type: CHEST_OPEN
    volume: 0.8
    pitch: 1
```
