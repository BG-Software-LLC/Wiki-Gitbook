---
description: Here you'll find how to make your own coops menu from scratch.
---

# Coops Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

The title of this menu supports custom placeholders: {0} - the amount of coop players the island has; {1} - the coop limit of the island.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Paged-Type Menu Sections

The coops menu is a paged-menu, which means it displays items from a list of available items - in this case, coop players. Because the amount of coop players can be greater than the amount of available slots, the menu supports multiple pages.

This type of menu requires 4 additional sections: \
`slots` - char of the coop player buttons.\
`previous-page` - char to set a custom button that will get players back to the previous page.\
`current-page` - char to set a custom button that will display the current page players look at.\
`next-page` - char to set a custom button that will get players to the next page.

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Custom Placeholders

The items of the paged-menu (`slots`, `previous-page`, etc) support custom placeholders!\
`slots` - \
&#x20;       {0} - The coop player's name.\
&#x20;       {1} - The coop player's role.\
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

This is the default coops menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lIsland Coop Players ({0}/{1})'
previous-menu: true

pattern:
  - '@ @ @ @ @ @ @ @ @'
  - '@ @ @ @ @ @ @ @ @'
  - '@ @ @ @ @ @ @ @ @'
  - '@ @ @ @ @ @ @ @ @'
  - '$ $ $ $ $ $ $ $ $'
  - '# # % # * # ^ # #'

slots: '@'
previous-page: '%'
current-page: '*'
next-page: '^'

items:
  '@':
    type: SKULL_ITEM
    data: 3
    name: '&e{0}'
    lore:
      - '&7Click to uncoop the player.'
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
  '$':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'

sounds:
  '@':
    type: CHEST_OPEN
    volume: 0.8
    pitch: 1
```
