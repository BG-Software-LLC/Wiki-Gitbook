---
description: Here you'll find how to make your own top islands menu from scratch.
---

# Top Islands Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Paged-Type Menu Sections

The top-islands menu is a paged-menu, which means it displays items from a list of available items - in this case, the top islands of the server. Because the amount of islands can be greater than the amount of available slots, the menu supports multiple pages.

This type of menu requires 4 additional sections: \
`slots` - char of the island buttons.\
`previous-page` - char to set a custom button that will get players back to the previous page.\
`current-page` - char to set a custom button that will display the current page players look at.\
`next-page` - char to set a custom button that will get players to the next page.

### Top-Islands Related Sections

The top-islands menu has additional sections that can be configured:

| Field Name                | Field Type | Description                                                                             |
| ------------------------- | ---------- | ---------------------------------------------------------------------------------------- |
| `player-island`           | Char       | A custom button that displays the island of the player that is viewing the menu.       |
| `sort-glow-when-selected` | Boolean    | Whether the sorting buttons should glow when their sorting type is the selected one.    |

#### Sorting Buttons

You can create buttons that change the sorting type of the islands. These buttons follow the format of regular items, with one additional field that should be given to them:

| Field Name     | Field Type | Description                                                                       |
| -------------- | ---------- | ---------------------------------------------------------------------------------- |
| `sorting-type` | String     | The sorting type to switch to. Can be `WORTH`, `LEVEL`, `RATING` or `PLAYERS`.    |

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Island Items

The island buttons (`slots` and `player-island` chars) do not follow the format of regular items and have custom sections that should be given to them:

| Field Name  | Field Type   | Description                                                       |
| ----------- | ------------ | ------------------------------------------------------------------ |
| `island`    | Item-Section | The item that will be displayed when there is an island to show.  |
| `no-island` | Item-Section | The item that will be displayed when there is no island to show.  |

The `island` and `no-island` fields can be used in the sounds and commands sections as well, to achieve custom sounds/commands depending on whether an island exists in that slot.

#### Custom Placeholders

The `island` items support custom placeholders!\
&#x20;       {0} - The island's name (or its owner's name if no name is set).\
&#x20;       {1} - The island's place in the top islands.\
&#x20;       {2} - The island's level.\
&#x20;       {3} - The island's worth.\
&#x20;       {4} - Special placeholder for the members of the island (explained below).\
&#x20;       {5} - The island's level, formatted with `K` for thousands, `M` for millions, etc.\
&#x20;       {6} - The island's worth, formatted with `K` for thousands, `M` for millions, etc.\
&#x20;       {7} - The island's total rating, as a number.\
&#x20;       {8} - The island's rating, formatted as stars.\
&#x20;       {9} - The amount of ratings the island received.\
&#x20;       {10} - The amount of players that are currently on the island.\
The pagination items also support custom placeholders:\
`previous-page`, `next-page` -\
&#x20;       {0} - Green color (\&a) if can navigate to the previous/next page, red color (\&c) otherwise.\
`current-page` -\
&#x20;       {0} - The current's page number.

#### Members Placeholder

The {4} placeholder is used inside the lore to display the list of the island members. The format of the lore line should be `'{4}:<member-format>'` - the line will be repeated for every member of the island, and the `{}` placeholder inside the member format will be replaced with the member's name. You can also use {0} for the member's name, {1} for the member's online status and {2} for the member's role.

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default top-islands menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lTop Islands'
previous-menu: true

pattern:
  - '~ ~ ~ ~ ~ ~ ~ ~ ~'
  - '@ % @ @ @ # @ @ @'
  - '@ * @ @ # # # @ @'
  - '@ ^ @ # # # # # @'
  - '@ & @ @ @ $ @ @ @'
  - '~ ~ ! ~ - ~ + ~ ~'

slots: '#'
previous-page: '!'
current-page: '-'
next-page: '+'

player-island: '$'
sort-glow-when-selected: true

items:
  '#':
    island:
      type: SKULL_ITEM
      data: 3
      name: '&e&l[!] Island: &6&n{0}&7 (#{1})'
      lore:
        - '&7'
        - '&6&l* &e&lIsland Level &7{2}'
        - '&7'
        - '&6&l* &e&lPlace &7#{1}'
        - '&6&l* &e&lWorth &7${3}'
        - '&6&l* &e&lRating {8} &7({9})'
        - '&6&l* &e&lPlayers &7{10}'
        - '&7'
        - '&6&l* &e&lMembers:'
        - '{4}:&f  - &7{}'
        - '&7'
        - '&7&o(( &f&oLeft-Click &7&oto view their items. ))'
        - '&7&o(( &f&oRight-Click &7&oto teleport to island warp. ))'
    no-island:
      type: SKULL_ITEM
      data: 3
      name: '&cInvalid Island'
  '%':
    type: DIAMOND
    sorting-type: 'WORTH'
    name: '&6Sort by Worth'
  '*':
    type: GOLD_INGOT
    sorting-type: 'LEVEL'
    name: '&6Sort by Level'
  '^':
    type: EMERALD
    sorting-type: 'RATING'
    name: '&6Sort by Rating'
  '&':
    type: SKULL_ITEM
    data: 3
    sorting-type: 'PLAYERS'
    name: '&6Sort by Players'
  '!':
    type: PAPER
    name: '{0}Previous Page'
  '-':
    type: DOUBLE_PLANT
    name: '&aCurrent Page'
    lore:
      - '&7Page {0}'
  '+':
    type: PAPER
    name: '{0}Next Page'
  '~':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'

sounds:
  '@':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
```
