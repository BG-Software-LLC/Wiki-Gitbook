---
description: Here you'll find how to make your own permissions menu from scratch.
---

# Permissions Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Paged-Type Menu Sections

The permissions menu is a paged-menu, which means it displays items from a list of available items - in this case, the [island privileges](../island-privileges.md). Because the amount of privileges can be greater than the amount of available slots, the menu supports multiple pages.

This type of menu requires 4 additional sections: \
`slots` - char of the privilege buttons.\
`previous-page` - char to set a custom button that will get players back to the previous page.\
`current-page` - char to set a custom button that will display the current page players look at.\
`next-page` - char to set a custom button that will get players to the next page.

### Messages Section

The permissions menu can be opened for a specific player or for a role. When opened for a role, the `role-permission` items display which roles have the privilege using the `messages` section:

| Field Name              | Field Type | Description                                                                              |
| ----------------------- | ---------- | ------------------------------------------------------------------------------------------ |
| `no-role-permission`    | String     | The format of a role line when the role doesn't have the privilege. {} is the role name. |
| `exact-role-permission` | String     | The format of a role line when the role is the exact role with the privilege. {} is the role name. |
| `higher-role-permission`| String     | The format of a role line when the role inherits the privilege from a lower role. {} is the role name. |

```yaml
messages:
  no-role-permission: '&8 - &c{}'
  exact-role-permission: '&8 - &2{}'
  higher-role-permission: '&8 - &a{}'
```

### Permissions-Configuration Section

Besides the regular menu sections, the permissions menu has a `permissions` section, where all the privileges of the menu are configured. Each privilege has its own sub-section, with the name of the [island privilege](../island-privileges.md) as its key. Each privilege section can have the following fields:

| Field Name            | Field Type   | Description                                                                                    |
| --------------------- | ------------ | ------------------------------------------------------------------------------------------------ |
| `display-menu`        | Boolean      | Whether the privilege should be displayed in the menu.                                         |
| `permission-enabled`  | Item-Section | The item that will be displayed when the privilege is enabled for the player.                  |
| `permission-disabled` | Item-Section | The item that will be displayed when the privilege is disabled for the player.                 |
| `role-permission`     | Item-Section | The item that will be displayed when the menu is opened for a role instead of a player.        |
| `has-access`          | Section      | Contains a `sound` section (and optionally `commands`) used when the privilege is granted.     |
| `no-access`           | Section      | Contains a `sound` section (and optionally `commands`) used when the privilege can't be changed. |

The lore of the `role-permission` item supports two custom placeholders: {} - the name of the role that currently has the privilege; a lore line containing only {0} will be replaced with the list of the roles, formatted using the `messages` section.

```yaml
permissions:
  all:
    display-menu: true
    permission-enabled:
      type: BEDROCK
      name: '&6All'
      lore:
        - '&7Access to all the abilities of the island.'
        - '&7Currently &aENABLED&7.'
    permission-disabled:
      type: BEDROCK
      name: '&6All'
      lore:
        - '&7Access to all the abilities of the island.'
        - '&7Currently &cDISABLED&7.'
    role-permission:
      type: BEDROCK
      name: '&6All'
      lore:
        - '&7Access to all the abilities of the island.'
        - '&7Role: &e{}&7.'
        - ''
        - '{0}'
    has-access:
      sound:
        type: ORB_PICKUP
        volume: 0.2
        pitch: 0.2
    no-access:
      sound:
        type: ANVIL_LAND
        volume: 0.2
        pitch: 0.2
```

{% hint style="info" %}
If a privilege that exists in the plugin is missing from the `permissions` section, a warning will be printed to the console. You can hide a privilege from the menu without warnings by setting its `display-menu` field to `false`.
{% endhint %}

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Custom Placeholders

The pagination items of the paged-menu support custom placeholders!\
`previous-page`, `next-page` -\
&#x20;       {0} - Green color (\&a) if can navigate to the previous/next page, red color (\&c) otherwise.\
`current-page` -\
&#x20;       {0} - The current's page number.

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is a shortened version of the default permissions menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lPermissions Controller'
previous-menu: true

pattern:
  - '$ $ $ $ $ $ $ $ $'
  - '$ @ @ @ @ @ @ @ $'
  - '$ @ @ @ @ @ @ @ $'
  - '$ @ @ @ @ @ @ @ $'
  - '$ $ % $ * $ ^ $ $'

slots: '@'
previous-page: '%'
current-page: '*'
next-page: '^'

messages:
  no-role-permission: '&8 - &c{}'
  exact-role-permission: '&8 - &2{}'
  higher-role-permission: '&8 - &a{}'

items:
  '$':
    type: STAINED_GLASS_PANE
    data: 3
    name: '&f'
  '%':
    type: PAPER
    name: '{0}Previous Page'
  '*':
    type: DOUBLE_PLANT
    name: '&aCurrent Page'
    lore:
      - '&7Page {0}'
  '^':
    type: PAPER
    name: '{0}Next Page'

permissions:
  animal_breed:
    display-menu: true
    permission-enabled:
      type: WHEAT
      name: '&6Animal Breed'
      lore:
        - '&7Access to breed animals inside the island.'
        - '&7Currently &aENABLED&7.'
    permission-disabled:
      type: WHEAT
      name: '&6Animal Breed'
      lore:
        - '&7Access to breed animals inside the island.'
        - '&7Currently &cDISABLED&7.'
    role-permission:
      type: WHEAT
      name: '&6Animal Breed'
      lore:
        - '&7Access to breed animals inside the island.'
        - '&7Role: &e{}&7.'
        - ''
        - '{0}'
    has-access:
      sound:
        type: ORB_PICKUP
        volume: 0.2
        pitch: 0.2
    no-access:
      sound:
        type: ANVIL_LAND
        volume: 0.2
        pitch: 0.2
  # ... more privileges follow the same format ...
```
