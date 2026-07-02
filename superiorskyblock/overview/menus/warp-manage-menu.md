---
description: Here you'll find how to make your own warp manage menu from scratch.
---

# Warp Manage Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

The title of this menu supports a custom placeholder: {0} - the name of the warp that is being edited.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Warp-Manage Related Sections

The warp-manage menu is used to edit a single warp, and therefore it has special buttons that should be configured. Simply set them as a custom char from your pattern in order to make that item a custom button.

| Field Name              | Field Type | Description                                                                    |
| ----------------------- | ---------- | ------------------------------------------------------------------------------ |
| `warp-rename`           | Char       | The button that lets players rename the warp.                                 |
| `warp-icon`             | Char       | The button that opens the [warp icon edit menu](warp-icon-edit-menu.md).      |
| `warp-location`         | Char       | The button that updates the warp's location to the player's current location. |
| `warp-private`          | Char       | The button that toggles the privacy of the warp.                              |
| `success-update-sound`  | Sound      | A sound that will be played when the warp is successfully updated.            |

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default warp-manage menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lWarp: {0}'
previous-menu: true

pattern:
  - '@ @ @ @ @ @ @ @ @'
  - '@ @ ! @ % @ $ @ @'
  - '@ @ @ @ ~ @ @ @ @'
  - '@ @ @ @ @ @ @ @ @'

success-update-sound:
  type: ORB_PICKUP
  volume: 0.2
  pitch: 0.2

warp-rename: '!'
warp-icon: '~'
warp-location: '$'
warp-private: '%'

items:
  '!':
    type: BOOK
    name: '&6Rename Warp'
    lore:
      - '&f '
      - '&f '
      - '&7&o(( &f&oClick &7&oto rename the warp. ))'
  '~':
    type: STONE
    lore:
      - '&f '
      - '&f '
      - '&7&oYou can use the following placeholders:'
      - '&7&o{0} is used for the warp''s name.'
      - '&7&o{1} is used for the warp''s location.'
      - '&7&o{2} is used for the warp''s public status.'
      - '&7&o(( &f&oClick &7&oto edit the icon. ))'
  '$':
    type: ENDER_PEARL
    name: '&6Warp Location'
    lore:
      - '&f '
      - '&f '
      - '&7&o(( &f&oClick &7&oto update the warp location. ))'
  '%':
    type: FEATHER
    name: '&6Private Warp'
    lore:
      - '&f '
      - '&f '
      - '&7&o(( &f&oClick &7&oto toggle warp to the public. ))'
```
