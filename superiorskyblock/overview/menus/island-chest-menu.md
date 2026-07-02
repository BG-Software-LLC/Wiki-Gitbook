---
description: Here you'll find how to make your own island chest menu from scratch.
---

# Island Chest Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Paged-Type Menu Sections

The island-chest menu is a paged-menu, which means it displays items from a list of available items - in this case, the pages of the island chest. Because the amount of chest pages can be greater than the amount of available slots, the menu supports multiple pages.

This type of menu requires 4 additional sections: \
`slots` - char of the chest page buttons.\
`previous-page` - char to set a custom button that will get players back to the previous page.\
`current-page` - char to set a custom button that will display the current page players look at.\
`next-page` - char to set a custom button that will get players to the next page.

{% hint style="info" %}
The island-chest menu supports the `skip-one-item` option - when enabled and the island has only one chest page, the chest will be opened directly instead of this menu.
{% endhint %}

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Chest Page Items

The chest page buttons (`slots` char) do not follow the format of regular items and have custom sections that should be given to them:

| Field Name     | Field Type   | Description                                                            |
| -------------- | ------------ | ------------------------------------------------------------------------ |
| `valid-page`   | Item-Section | The item that will be displayed when the chest page is available.       |
| `invalid-page` | Item-Section | The item that will be displayed when the chest page is not available.   |

#### Custom Placeholders

The `valid-page` items support custom placeholders!\
&#x20;       {0} - The page's number.\
&#x20;       {1} - The amount of slots in the page.\
The pagination items also support custom placeholders:\
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

This is the default island-chest menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lIsland Chest'
previous-menu: true

pattern:
  - '# # # # # # # # #'
  - '# $ @ @ @ @ @ $ #'
  - '# $ @ @ @ @ @ $ #'
  - '# $ @ @ @ @ @ $ #'
  - '# $ @ @ @ @ @ $ #'
  - '# # % # * # ^ # #'

slots: '@'
previous-page: '%'
current-page: '*'
next-page: '^'

items:
  '@':
    valid-page:
      type: STORAGE_MINECART
      name: '&ePage #{0}'
      lore:
        - '&eSize: &7{1}'
    invalid-page:
      type: MINECART
      name: '&f '
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
  '#':
    type: RAILS
    name: '&f '

sounds:
  '@':
    type: CHEST_OPEN
    volume: 0.8
    pitch: 1
```
