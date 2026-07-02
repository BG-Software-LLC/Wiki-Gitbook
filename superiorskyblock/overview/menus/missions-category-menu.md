---
description: Here you'll find how to make your own missions category menu from scratch.
---

# Missions Category Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

The title of this menu supports a custom placeholder: {0} - the name of the category.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Paged-Type Menu Sections

The missions-category menu is a paged-menu, which means it displays items from a list of available items - in this case, the missions of the category. Because the amount of missions can be greater than the amount of available slots, the menu supports multiple pages.

This type of menu requires 4 additional sections: \
`slots` - char of the mission buttons.\
`previous-page` - char to set a custom button that will get players back to the previous page.\
`current-page` - char to set a custom button that will display the current page players look at.\
`next-page` - char to set a custom button that will get players to the next page.

{% hint style="info" %}
The icons of the missions themselves are not configured in this menu - each mission has its own icon configured in its mission file, under the `icons` section.
{% endhint %}

### Missions-Category Related Sections

The missions-category menu has additional sections that can be configured:

| Field Name           | Field Type | Description                                                                                                    |
| -------------------- | ---------- | --------------------------------------------------------------------------------------------------------------- |
| `sort-by-completion` | Boolean    | Whether missions should be sorted by their completion status: Not completed -> Can complete -> Completed. |
| `remove-completed`   | Boolean    | Whether completed missions should not be displayed in the menu.                                                |

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

The mission buttons (`slots` char) support four special sound sections instead of a regular sound, depending on the status of the mission for the player:

| Field Name      | Description                                                             |
| --------------- | ------------------------------------------------------------------------ |
| `locked`        | Played when the mission is locked for the player.                       |
| `completed`     | Played when the mission was already completed.                          |
| `not-completed` | Played when the mission is not completed and cannot be completed yet.   |
| `can-complete`  | Played when the mission can be completed.                               |

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default missions-category menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&l{0} Missions'
previous-menu: true

pattern:
  - '# # # # # # # # #'
  - '# # @ @ @ @ @ # #'
  - '# # # # # # # # #'

slots: '@'
previous-page: '*'
current-page: '*'
next-page: '*'

# Should missions be sorted by their completion status?
# Not completed -> Can complete -> Completed
sort-by-completion: false

# Should completed missions not be displayed in the menu?
remove-completed: false

items:
  '#':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'

sounds:
  '@':
    locked:
      type: ANVIL_LAND
      volume: 0.2
      pitch: 0.2
    completed:
      type: ANVIL_LAND
      volume: 0.2
      pitch: 0.2
    not-completed:
      type: ANVIL_LAND
      volume: 0.2
      pitch: 0.2
    can-complete:
      type: ORB_PICKUP
      volume: 0.2
      pitch: 0.2
```
