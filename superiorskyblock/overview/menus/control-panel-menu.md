---
description: Here you'll find how to make your own control panel menu from scratch.
---

# Control Panel Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Control-Panel Related Sections

The control-panel menu is the main island panel, and it has special buttons that open other menus directly. Simply set them as a custom char from your pattern in order to make that item a custom button.

| Field Name | Field Type | Description                                              |
| ---------- | ---------- | --------------------------------------------------------- |
| `members`  | Char       | The button that opens the [members menu](members-menu.md). |
| `settings` | Char       | The button that opens the [settings menu](settings-menu.md). |
| `visitors` | Char       | The button that opens the [visitors menu](visitors-menu.md). |

{% hint style="info" %}
All the other buttons in the default menu are regular items that execute island commands using the commands section, so you can add as many custom buttons as you wish.
{% endhint %}

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default control-panel menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lIsland Panel'
previous-menu: true

pattern:
  - '2 2 2 2 2 2 2 2 2'
  - '# ! # @ # $ # % #'
  - '_ # ^ # & # * # 1'
  - '# ~ # = # - # + #'
  - '2 2 2 2 2 2 2 2 2'

members: '+'
settings: '@'
visitors: '-'

items:
  '!':
    type: SIGN
    name: '&eTeleport'
    lore:
      - '&7Teleport back to your island.'
  '@':
    type: DIODE
    name: '&eIsland Settings'
    lore:
      - '&7Manage settings regarding your island.'
  '$':
    type: ENDER_PEARL
    name: '&eIsland Permissions'
    lore:
      - '&7Manage permissions in your island.'
  '%':
    type: GRASS
    name: '&eIsland Biomes'
    lore:
      - '&7Change the biome of your island.'
  '_':
    type: EMERALD
    name: '&eIsland Bank'
    lore:
      - '&7Open the bank of your island.'
  '^':
    type: GOLD_INGOT
    name: '&eIsland Upgrades'
    lore:
      - '&7Upgrade your island statistics!'
  '&':
    type: BEACON
    name: '&eTop Islands'
    lore:
      - '&7Check which island is the best on the server!'
  '*':
    type: PAPER
    name: '&eIsland Missions'
    lore:
      - '&7Complete missions and get rewarded!'
  '1':
    type: SMOOTH_BRICK
    name: '&eIsland Counts'
    lore:
      - '&7See all the blocks on your island!'
  '~':
    type: BARRIER
    name: '&eIsland Disband'
    lore:
      - '&7Disband your island.'
      - '&cThis action cannot be restored!'
  '=':
    type: CHEST
    name: '&eIsland Chest'
    lore:
      - '&7Open the community chest of the island.'
  '-':
    type: SKULL_ITEM
    name: '&eIsland Visitors'
    lore:
      - '&7Check all the visitors of the island.'
  '+':
    type: SKULL_ITEM
    data: 3
    name: '&eIsland Members'
    lore:
      - '&7Manage the members of the island.'
  '2':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'

sounds:
  '!':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '@':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '$':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '%':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '_':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '^':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '&':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '*':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '1':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '~':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '-':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '=':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '+':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2

commands:
  '!':
    - '[player] is tp'
  '$':
    - '[player] is permissions'
  '%':
    - '[player] is biome'
  '_':
    - '[player] is bank'
  '^':
    - '[player] is upgrade'
  '&':
    - '[player] is top'
  '*':
    - '[player] is missions'
  '1':
    - '[player] is counts'
  '~':
    - '[player] is disband'
  '=':
    - '[player] is chest'
```
