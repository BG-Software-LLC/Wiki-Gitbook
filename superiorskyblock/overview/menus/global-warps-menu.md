---
description: Here you'll find how to make your own global warps menu from scratch.
---

# Global Warps Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Paged-Type Menu Sections

The global-warps menu is a paged-menu, which means it displays items from a list of available items - in this case, all the islands with public warps on the server. Because the amount of islands can be greater than the amount of available slots, the menu supports multiple pages.

This type of menu requires 4 additional sections: \
`warps` - char of the island buttons (`slots` is supported as well).\
`previous-page` - char to set a custom button that will get players back to the previous page.\
`current-page` - char to set a custom button that will display the current page players look at.\
`next-page` - char to set a custom button that will get players to the next page.

### Global-Warps Related Sections

The global-warps menu has an additional section that can be configured - `visitor-warps`. When enabled, instead of showing islands with warps, the visitor warp locations of islands will be shown. To show the description of the visitor warp, use the {1} placeholder.

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Custom Placeholders

The items of the paged-menu (`warps`, `previous-page`, etc) support custom placeholders!\
`warps` - \
&#x20;       {0} - The name of the island's owner.\
&#x20;       {1} - The description of the visitor warp (when `visitor-warps` is enabled).\
&#x20;       {2} - The amount of warps the island has.\
&#x20;       {3} - The island's name.\
&#x20;       {4} - The island's level.\
&#x20;       {5} - The island's level, formatted with `K` for thousands, `M` for millions, etc.\
&#x20;       {6} - The island's worth.\
&#x20;       {7} - The island's worth, formatted with `K` for thousands, `M` for millions, etc.\
&#x20;       {8} - The island's total rating, as a number.\
&#x20;       {9} - The island's rating, formatted as stars.\
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

This is the default global-warps menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lIsland Warps'
previous-menu: true

pattern:
  - '@ @ @ @ @ @ @ @ @'
  - '@ @ @ @ @ @ @ @ @'
  - '@ @ @ @ @ @ @ @ @'
  - '@ @ @ @ @ @ @ @ @'
  - '$ $ $ $ $ $ $ $ $'
  - '# # % # * # ^ # #'

warps: '@'
previous-page: '%'
current-page: '*'
next-page: '^'

# When enabled, instead of showing warps, the visitor warp locations will be shown.
# To show the description, use the {1} placeholder.
visitor-warps: false

items:
  '@':
    type: SKULL_ITEM
    data: 3
    name: '&e{0}''s Island'
    lore:
      - '&7Click to see all warps of this island.'
      - '&8>> &7This island has {2} warps.'
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
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
```
