---
description: Here you'll find how to make your own visitors menu from scratch.
---

# Visitors Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

The title of this menu supports a custom placeholder: {0} - the amount of visitors that are currently on the island.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Paged-Type Menu Sections

The visitors menu is a paged-menu, which means it displays items from a list of available items - in this case, the visitors that are currently on the island. Because the amount of visitors can be greater than the amount of available slots, the menu supports multiple pages.

This type of menu requires 4 additional sections: \
`slots` - char of the visitor buttons.\
`previous-page` - char to set a custom button that will get players back to the previous page.\
`current-page` - char to set a custom button that will display the current page players look at.\
`next-page` - char to set a custom button that will get players to the next page.

### Visitors Related Sections

The visitors menu has an additional section that can be configured - `unique-visitors`. This is a char of a custom button that opens the [unique visitors menu](unique-visitors-menu.md), which displays all-time visitors of the island.

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Custom Placeholders

The items of the paged-menu (`slots`, `previous-page`, etc) support custom placeholders!\
`slots` - \
&#x20;       {0} - The visitor's name.\
&#x20;       {1} - The name of the owner of the visitor's island.\
&#x20;       {2} - The name of the visitor's island.\
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

This is the default visitors menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lIsland Visitors ({0})'
previous-menu: true

pattern:
  - '@ @ @ @ @ @ @ @ @'
  - '@ @ @ @ @ @ @ @ @'
  - '@ @ @ @ @ @ @ @ @'
  - '@ @ @ @ @ @ @ @ @'
  - '$ $ $ $ ~ $ $ $ $'
  - '# # % # * # ^ # #'

slots: '@'
previous-page: '%'
current-page: '*'
next-page: '^'
unique-visitors: '~'

items:
  '@':
    type: SKULL_ITEM
    data: 3
    name: '&e{0}'
    lore:
      - '&7Island Owner: {1}'
      - ''
      - '&7Left-Click to expel the player.'
      - '&7Right-Click to invite the player.'
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
  '~':
    type: SKULL_ITEM
    name: '&eUnique Visitors'
    lore:
      - '&7Click to open all-time visitors menu.'
  '$':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'

sounds:
  '@':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
```
