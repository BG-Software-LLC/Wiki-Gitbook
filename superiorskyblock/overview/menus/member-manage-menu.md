---
description: Here you'll find how to make your own member manage menu from scratch.
---

# Member Manage Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

The title of this menu supports a custom placeholder: {} - the name of the member that is being managed.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Member-Manage Related Sections

The member-manage menu is used to manage a single island member, and therefore it has special buttons that should be configured. Simply set them as a custom char from your pattern in order to make that item a custom button.

| Field Name | Field Type | Description                                                                |
| ---------- | ---------- | -------------------------------------------------------------------------- |
| `roles`    | Char       | The button that opens the [member role menu](member-role-menu.md).        |
| `ban`      | Char       | The button that bans the member from the island.                          |
| `kick`     | Char       | The button that kicks the member from the island.                         |

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default member-manage menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&8&l{}'
previous-menu: true

pattern:
  - '$ $ $ $ $ $ $ $ $'
  - '$ # # # # # # # $'
  - '$ # @ # % # ^ # $'
  - '$ # # # # # # # $'
  - '$ $ $ $ $ $ $ $ $'

roles: '@'
ban: '%'
kick: '^'

items:
  '$':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'
  '@':
    type: DIAMOND_CHESTPLATE
    name: '&ePlayer Role'
    lore:
      - '&7Click to edit player''s role.'
    flags:
      - HIDE_ATTRIBUTES
  '%':
    type: BARRIER
    name: '&eBan Player'
    lore:
      - '&7Click to ban the player from the island.'
  '^':
    type: SKULL_ITEM
    name: '&eKick Player'
    lore:
      - '&7Click to kick the player from the island.'

sounds:
  '@':
    type: CHEST_OPEN
    volume: 0.8
    pitch: 1
  '%':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '^':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
```
