---
description: Here you'll find how to make your own border color menu from scratch.
---

# Border Color Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html). By default, this menu uses the `HOPPER` type, which has a single row with 5 slots.
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. Because this menu uses the `HOPPER` type by default, the pattern should contain a single line with 5 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Border-Color Related Sections

The border-color menu is used to change the color of the world border, and therefore it has special buttons that should be configured. Simply set them as a custom char from your pattern in order to make that item a custom button.

| Field Name    | Field Type | Description                                        |
| ------------- | ---------- | --------------------------------------------------- |
| `green-color` | Char       | The button that changes the border color to green. |
| `red-color`   | Char       | The button that changes the border color to red.   |
| `blue-color`  | Char       | The button that changes the border color to blue.  |

#### Border Toggle Item

Besides the color buttons, you can add a button that toggles the world border on and off for the player. This special-type button does not follow the format of regular items and has custom sections that should be given to it.

| Field Name       | Field Type   | Description                                                          |
| ---------------- | ------------ | --------------------------------------------------------------------- |
| `enable-border`  | Item-Section | The item that will be displayed when the player's border is disabled. |
| `disable-border` | Item-Section | The item that will be displayed when the player's border is enabled.  |

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default border-color menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&l        Border Color'
previous-menu: true
type: HOPPER

pattern:
  - '~ # @ ^ $'

green-color: '@'
red-color: '^'
blue-color: '$'

items:
  '~':
    enable-border:
      type: SKULL_ITEM
      data: 3
      skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvM2ZhZjRjMjlmMWU3NDA1ZjQ2ODBjNWMyYjAzZWY5Mzg0ZjFhZWNmZTI5ODZhZDUwMTM4YzYwNWZlZmZmMmYxNSJ9fX0='
      name: '&aEnable Border'
    disable-border:
      type: SKULL_ITEM
      data: 3
      skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvM2ZhZjRjMjlmMWU3NDA1ZjQ2ODBjNWMyYjAzZWY5Mzg0ZjFhZWNmZTI5ODZhZDUwMTM4YzYwNWZlZmZmMmYxNSJ9fX0='
      name: '&cDisable Border'
  '#':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'
  '@':
    type: SKULL_ITEM
    data: 3
    skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNzc0NzJkNjA4ODIxZjQ1YTg4MDUzNzZlYzBjNmZmY2I3ODExNzgyOWVhNWY5NjAwNDFjMmEwOWQxMGUwNGNiNCJ9fX0='
    name: '&aGreen Color'
  '^':
    type: SKULL_ITEM
    data: 3
    skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNjk1M2IxMmEwOTQ2YjYyOWI0YzA4ODlkNDFmZDI2ZWQyNmZiNzI5ZDRkNTE0YjU5NzI3MTI0YzM3YmI3MGQ4ZCJ9fX0='
    name: '&cRed Color'
  '$':
    type: SKULL_ITEM
    data: 3
    skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvMTYzZTY2NDZmMWMwZDQxZmQzYmY1NTg0YTFjZTA0NGY1YzQ2ZDU5ODI1OGRiNDYyMTYxMTc4NTlmNTdhZjE5NyJ9fX0='
    name: '&bBlue Color'

sounds:
  '~':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '@':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '^':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '$':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
```
