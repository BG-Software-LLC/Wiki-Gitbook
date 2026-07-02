---
description: Here you'll find how to make your own player language menu from scratch.
---

# Player Language Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Language Items

The player-language menu gives players the ability to change the language of the plugin's messages for themselves. In order to achieve that, the menu must be configured with special type of buttons that will make this work.

These special-type buttons follow the format of regular items, with one additional field that should be given to them:

| Field Name | Field Type | Description                                                                                                  |
| ---------- | ---------- | -------------------------------------------------------------------------------------------------------------- |
| `language` | String     | The language to switch to when clicking the item (for example `en-US`). The language must be a valid locale that is enabled in the config. |

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is a shortened version of the default player-language menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lSelect Language...'
previous-menu: true

pattern:
  - '@ @ @ @ @ @ @ @ @'
  - '@ # % * + ^ ~ 1 @'
  - '@ @ - = ! 2 3 @ @'
  - '@ @ @ @ @ @ @ @ @'

items:
  '@':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'
  '#':
    language: 'en-US'
    type: SKULL_ITEM
    data: 3
    skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNGNhYzk3NzRkYTEyMTcyNDg1MzJjZTE0N2Y3ODMxZjY3YTEyZmRjY2ExY2YwY2I0YjM4NDhkZTZiYzk0YjQifX19'
    name: '&eEnglish'
    lore:
      - '&7Change language to English.'
  '-':
    language: 'fr-FR'
    type: SKULL_ITEM
    data: 3
    skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNTEyNjlhMDY3ZWUzN2U2MzYzNWNhMWU3MjNiNjc2ZjEzOWRjMmRiZGRmZjk2YmJmZWY5OWQ4YjM1Yzk5NmJjIn19fQ=='
    name: '&eFrench'
    lore:
      - '&7Change language to French.'
  '=':
    language: 'es-ES'
    type: SKULL_ITEM
    data: 3
    skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvMzJiZDQ1MjE5ODMzMDllMGFkNzZjMWVlMjk4NzQyODc5NTdlYzNkOTZmOGQ4ODkzMjRkYThjODg3ZTQ4NWVhOCJ9fX0='
    name: '&eSpanish'
    lore:
      - '&7Change language to Spanish.'
  # ... more language items follow the same format ...

sounds:
  '#':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
```
