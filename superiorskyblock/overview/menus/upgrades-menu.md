---
description: Here you'll find how to make your own upgrades menu from scratch.
---

# Upgrades Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Upgrades Section

Besides the regular menu sections, the upgrades menu has an `upgrades` section, where all the upgrade buttons are configured. Each upgrade has its own sub-section, with the name of the upgrade from `upgrades.yml` (the upgrades configuration file) as its key.

Each upgrade section should have an `item` field with the char of the upgrade button from the pattern. Besides that, it should have a sub-section for every level of the upgrade, with the level number as its key. Each level section should have the following fields:

| Field Name       | Field Type   | Description                                                                  |
| ---------------- | ------------ | ------------------------------------------------------------------------------ |
| `has-next-level` | Item-Section | The item that will be displayed when there is a next level to upgrade to.    |
| `no-next-level`  | Item-Section | The item that will be displayed when the level is the last one.              |

Both items can have their own `sound` section (played when clicking the button in that state) and `commands` list.

#### Custom Placeholders

The upgrade items support custom placeholders!\
&#x20;       {0} - The price of the next level.\
&#x20;       {1} - The price of the next level, formatted with commas.\
&#x20;       {2} - The price of the next level, formatted with `K` for thousands, `M` for millions, etc.

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is a shortened version of the default upgrades menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lIsland Upgrades'
previous-menu: true

pattern:
  - '$ $ $ $ $ $ $ $ $'
  - '# # @ # % # ^ # #'
  - '# # # ! # + # # #'
  - '# # * # ~ # & # #'
  - '$ $ $ $ $ $ $ $ $'

items:
  '$':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'

upgrades:
  hoppers-limit:
    item: '@'
    '1':
      has-next-level:
        type: HOPPER
        name: '&d&lHopper Increase &a(Available)'
        lore:
          - '&7'
          - '&dNext Level: &e2'
          - '&7'
          - '&7Purchasing the hopper upgrade'
          - '&7will increase your island''s'
          - '&7max hoppers limit.'
          - '&7'
          - '&dAmount: &f16x Hoppers'
          - '&dPrice: &f$1,000,000'
          - '&7'
          - '&aClick to purchase upgrade.'
        sound:
          type: ORB_PICKUP
          volume: 0.2
          pitch: 0.2
      no-next-level:
        type: HOPPER
        name: '&d&lHopper Increase &c(Unavailable)'
        lore:
          - '&7'
          - '&dNext Level: &e2'
          - '&7'
          - '&7Purchasing the hopper upgrade'
          - '&7will increase your island''s'
          - '&7max hoppers limit.'
          - '&7'
          - '&dAmount: &f16x Hoppers'
          - '&dPrice: &f$1,000,000'
          - '&7'
          - '&cYou cannot purchase this upgrade.'
    '2':
      has-next-level:
        # ... same format as level 1 ...
      no-next-level:
        # ... same format as level 1 ...
  # ... more upgrades (crop-growth, spawner-rates, mob-drops, members-limit,
  #     border-size, generator-rates, minecarts-limit) follow the same format ...
```
