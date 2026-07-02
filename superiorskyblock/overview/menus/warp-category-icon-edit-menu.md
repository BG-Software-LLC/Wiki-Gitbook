---
description: Here you'll find how to make your own warp category icon edit menu from scratch.
---

# Warp Category Icon Edit Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

The title of this menu supports a custom placeholder: {0} - the name of the category that its icon is being edited.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Warp-Category-Icon-Edit Related Sections

The warp-category-icon-edit menu is used to edit the icon of a warp category, and therefore it has special buttons that should be configured. Simply set them as a custom char from your pattern in order to make that item a custom button.

| Field Name     | Field Type | Description                                                        |
| -------------- | ---------- | ------------------------------------------------------------------ |
| `icon-type`    | Char       | The button that lets players change the material of the icon.     |
| `icon-rename`  | Char       | The button that lets players change the name of the icon.         |
| `icon-relore`  | Char       | The button that lets players change the lore of the icon.         |
| `icon-confirm` | Char       | The button that confirms the changes made to the icon.            |
| `icon-slots`   | Char       | The slot where the currently edited icon is displayed as preview. |

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default warp-category-icon-edit menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lCategory: {0}'
previous-menu: true

pattern:
  - '@ @ @ @ @ @ @ @ @'
  - '@ ! @ @ @ @ @ ~ @'
  - '@ @ @ @ ^ @ @ @ @'
  - '@ $ @ @ @ @ @ % @'
  - '@ @ @ @ @ @ @ @ @'

icon-type: '!'
icon-rename: '~'
icon-relore: '$'
icon-confirm: '%'
icon-slots: '^'

items:
  '!':
    type: DIAMOND
    name: '&6Set Type'
    lore:
      - '&f '
      - '&f '
      - '&7&o(( &f&oClick &7&oto edit the item type. ))'
  '~':
    type: ANVIL
    name: '&6Set Name'
    lore:
      - '&f '
      - '&f '
      - '&7&o(( &f&oClick &7&oto edit the item name. ))'
  '$':
    type: PAPER
    name: '&6Set Lore'
    lore:
      - '&f '
      - '&f '
      - '&7&o(( &f&oClick &7&oto edit the item lore. ))'
  '%':
    type: EMERALD
    name: '&6Confirm Changes'
    lore:
      - '&f '
      - '&f '
      - '&7&o(( &f&oClick &7&oto confirm all changes. ))'
  '^':
    type: STONE

sounds:
  '%':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
```
