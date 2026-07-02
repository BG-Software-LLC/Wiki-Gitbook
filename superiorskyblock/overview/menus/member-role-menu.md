---
description: Here you'll find how to make your own member role menu from scratch.
---

# Member Role Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

The title of this menu supports a custom placeholder: {} - the name of the member that its role is being changed.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Role Items

The member-role menu gives players the ability to set the role of a member. In order to achieve that, the menu must be configured with special type of buttons that will make this work.

These special-type buttons follow the format of regular items, with one additional field that should be given to them:

| Field Name | Field Type       | Description                                                                                              |
| ---------- | ---------------- | -------------------------------------------------------------------------------------------------------- |
| `role`     | String / Integer | The role to set when clicking the item. Can be either the role's name or the role's id from config.yml. |

{% hint style="info" %}
Clicking a role item with the leader role will transfer the leadership of the island to the member.
{% endhint %}

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default member-role menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&8&l{}'
previous-menu: true

pattern:
  - '$ $ $ $ $ $ $ $ $'
  - '$ # # # # # # # $'
  - '$ @ # % # & # * $'
  - '$ # # # # # # # $'
  - '$ $ $ $ $ $ $ $ $'

items:
  '$':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'
  '@':
    role: Member
    type: LEATHER_CHESTPLATE
    name: '&eMember'
    lore:
      - '&7Click to set player''s role to member.'
    flags:
      - HIDE_ATTRIBUTES
  '%':
    role: Moderator
    type: GOLD_CHESTPLATE
    name: '&eModerator'
    lore:
      - '&7Click to set player''s role to moderator.'
    flags:
      - HIDE_ATTRIBUTES
  '&':
    role: Admin
    type: IRON_CHESTPLATE
    name: '&eAdmin'
    lore:
      - '&7Click to set player''s role to admin.'
    flags:
      - HIDE_ATTRIBUTES
  '*':
    role: Leader
    type: DIAMOND_CHESTPLATE
    name: '&eLeader'
    lore:
      - '&7Click to transfer leadership to player.'
    flags:
      - HIDE_ATTRIBUTES

sounds:
  '@':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
  '%':
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
```
