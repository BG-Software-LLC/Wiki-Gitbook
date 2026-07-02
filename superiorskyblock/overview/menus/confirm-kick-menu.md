---
description: Here you'll find how to make your own confirm kick menu from scratch.
---

# Confirm Kick Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html). By default, this menu uses the `HOPPER` type, which has a single row with 5 slots.
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. Because this menu uses the `HOPPER` type by default, the pattern should contain a single line with 5 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Confirm-Kick Related Sections

The confirm-kick menu is used to confirm or cancel the kick of a player, and therefore it has special buttons that should be configured. Simply set them as a custom char from your pattern in order to make that item a custom button.

| Field Name | Field Type | Description                                     |
| ---------- | ---------- | ------------------------------------------------ |
| `confirm`  | Char       | The button that confirms and kicks the player.  |
| `cancel`   | Char       | The button that cancels the kick.               |

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default confirm-kick menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&l      Confirm Kick'
previous-menu: true
type: HOPPER

pattern:
  - '# @ # ^ #'

confirm: '@'
cancel: '^'

items:
  '#':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'
  '@':
    type: SKULL_ITEM
    data: 3
    skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNzc0NzJkNjA4ODIxZjQ1YTg4MDUzNzZlYzBjNmZmY2I3ODExNzgyOWVhNWY5NjAwNDFjMmEwOWQxMGUwNGNiNCJ9fX0='
    name: '&aConfirm'
    lore:
      - '&7Are you sure you want to kick that player?'
  '^':
    type: SKULL_ITEM
    data: 3
    skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNjk1M2IxMmEwOTQ2YjYyOWI0YzA4ODlkNDFmZDI2ZWQyNmZiNzI5ZDRkNTE0YjU5NzI3MTI0YzM3YmI3MGQ4ZCJ9fX0='
    name: '&4Cancel'

sounds:
  '@':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '^':
    type: ANVIL_LAND
    volume: 0.2
    pitch: 0.2
```
