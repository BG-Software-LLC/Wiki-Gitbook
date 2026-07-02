---
description: Here you'll find how to make your own warp categories menu from scratch.
---

# Warp Categories Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Paged-Type Menu Sections

The warp-categories menu is a paged-menu, which means it displays items from a list of available items - in this case, the warp categories of an island. Because the amount of categories can be greater than the amount of available slots, the menu supports multiple pages.

This type of menu requires 4 additional sections: \
`slots` - char of the category buttons.\
`previous-page` - char to set a custom button that will get players back to the previous page.\
`current-page` - char to set a custom button that will display the current page players look at.\
`next-page` - char to set a custom button that will get players to the next page.

{% hint style="info" %}
The category buttons themselves use the icons that were set for the categories in-game, and each category is placed in the slot that was chosen for it. The item configured for the `slots` char is used as a filler for the rest of the slots.
{% endhint %}

### Warp-Categories Related Sections

The warp-categories menu has an additional section that can be configured - `edit-lore`. This is a list of lore lines that will be appended to the category icons when the player viewing the menu is allowed to edit them. It is useful for explaining how to edit categories without having the extra lines displayed to regular visitors.

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

This is the default warp-categories menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lWarp Categories'
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

# This lore is added to category icons.
edit-lore:
  - '&f '
  - '&f '
  - '&7&o(( &f&oLeft-Click &7&oto see island warps. ))'
  - '&7&o(( &f&oRight-Click &7&oto edit the category. ))'

items:
  '@':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'
  '%':
    type: PAPER
    name: '&cPrevious Page'
  '*':
    type: DOUBLE_PLANT
    name: '&aCurrent Page'
    lore:
      - '&7Page 1'
  '^':
    type: PAPER
    name: '&cNext Page'
  '$':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'
```
