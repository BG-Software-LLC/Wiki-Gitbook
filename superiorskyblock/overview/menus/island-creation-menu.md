---
description: Here you'll find how to make your own island creation menu from scratch.
---

# Island Creation Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Schematic Items

The island-creation menu gives players the ability to choose the schematic of their new island. In order to achieve that, the menu must be configured with special type of buttons that will make this work.

These special-type buttons do not follow the format of regular items and have custom sections that should be given to them.

| Field Name     | Field Type   | Description                                                                                                    |
| -------------- | ------------ | ---------------------------------------------------------------------------------------------------------------- |
| `schematic`    | String       | The name of the schematic that will be used for the island. More info about schematics [here](../schematics.md). |
| `biome`        | String       | The biome the island will have when created.                                                                   |
| `spawn-offset` | String       | An offset for the spawn location of the island, in the format `'x, y, z'`.                                     |
| `bonus`        | Double       | A bonus worth that will be given to islands created with this schematic (`bonus-worth` is supported as well).  |
| `bonus-level`  | Double       | A bonus level that will be given to islands created with this schematic.                                       |
| `offset`       | Boolean      | When enabled, the values of the schematic's blocks will be used as an offset, making the island start with a value of 0. |
| `access`       | Item-Section | The item that will be displayed when players have permission to use the schematic.                             |
| `no-access`    | Item-Section | The item that will be displayed when players don't have permission to use the schematic.                       |

{% hint style="info" %}
The `access` and `no-access` fields can be used in the sounds and commands sections as well to achieve custom sounds/commands when having/not having permission to use the schematic. The permission for a schematic is `superior.island.schematic.<schematic-name>`.
{% endhint %}

{% hint style="info" %}
The island-creation menu supports the `skip-one-item` option - when enabled and only one schematic is available, the island will be created directly with that schematic instead of opening the menu.
{% endhint %}

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default island-creation menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lCreate a new island...'
previous-menu: true

pattern:
  - '~ ~ ~ ~ ~ ~ ~ ~ ~'
  - '# @ # # ^ # # $ #'
  - '~ ~ ~ ~ ~ ~ ~ ~ ~'

items:
  '@':
    schematic: 'normal'
    biome: PLAINS
    spawn-offset: '0, 0, 0'
    access:
      type: SKULL_ITEM
      data: 3
      skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYzk1ZDM3OTkzZTU5NDA4MjY3ODQ3MmJmOWQ4NjgyMzQxM2MyNTBkNDMzMmEyYzdkOGM1MmRlNDk3NmIzNjIifX19'
      name: '&eNormal Island &a(Available)'
      lore:
        - '&7Simple island with trees and a mining area!'
        - '&7 '
        - '&7&o(( &f&oRight-Click &7&oto preview the island. ))'
    no-access:
      type: SKULL_ITEM
      data: 3
      skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYzk1ZDM3OTkzZTU5NDA4MjY3ODQ3MmJmOWQ4NjgyMzQxM2MyNTBkNDMzMmEyYzdkOGM1MmRlNDk3NmIzNjIifX19'
      name: '&eNormal Island &c(Unavailable)'
      lore:
        - '&7Simple island with trees and a mining area!'
        - '&7 '
        - '&7&o(( &f&oRight-Click &7&oto preview the island. ))'
  '^':
    schematic: 'mycel'
    biome: MUSHROOM_ISLAND
    spawn-offset: '0, 0, 0'
    access:
      type: SKULL_ITEM
      data: 3
      skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvZWE0NWQxYjQxN2NiZGRjMjE3NjdiMDYwNDRlODk5YjI2NmJmNzhhNjZlMjE4NzZiZTNjMDUxNWFiNTVkNzEifX19'
      name: '&eMycelium Island &a(Available)'
      lore:
        - '&7Customized island with lots of mycelium!'
        - '&7 '
        - '&7&o(( &f&oRight-Click &7&oto preview the island. ))'
    no-access:
      type: SKULL_ITEM
      data: 3
      skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvZWE0NWQxYjQxN2NiZGRjMjE3NjdiMDYwNDRlODk5YjI2NmJmNzhhNjZlMjE4NzZiZTNjMDUxNWFiNTVkNzEifX19'
      name: '&eMycelium Island &c(Unavailable)'
      lore:
        - '&7Customized island with lots of mycelium!'
        - '&7 '
        - '&7&o(( &f&oRight-Click &7&oto preview the island. ))'
  '$':
    schematic: 'desert'
    biome: DESERT
    spawn-offset: '0, 0, 0'
    access:
      type: SKULL_ITEM
      data: 3
      skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvZjVkYjMxMjA2N2JlMWQ1YzRmMTQ3OGFmM2NhMmY2Y2Y4MTA0YWI0Y2NiZmY1NzkxN2M4NTc4ZGFhMTUwMDJjMiJ9fX0='
      name: '&eDesert Island &a(Available)'
      lore:
        - '&7Customized island with lots of sand!'
        - '&7 '
        - '&7&o(( &f&oRight-Click &7&oto preview the island. ))'
    no-access:
      type: SKULL_ITEM
      data: 3
      skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvZjVkYjMxMjA2N2JlMWQ1YzRmMTQ3OGFmM2NhMmY2Y2Y4MTA0YWI0Y2NiZmY1NzkxN2M4NTc4ZGFhMTUwMDJjMiJ9fX0='
      name: '&eDesert Island &c(Unavailable)'
      lore:
        - '&7Customized island with lots of sand!'
        - '&7 '
        - '&7&o(( &f&oRight-Click &7&oto preview the island. ))'
  '~':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'

sounds:
  '@':
    access:
      type: PORTAL_TRIGGER
      volume: 1
      pitch: 0.2
    no-access:
      type: ANVIL_LAND
      volume: 0.2
      pitch: 0.2
  '^':
    access:
      type: PORTAL_TRIGGER
      volume: 1
      pitch: 0.2
    no-access:
      type: ANVIL_LAND
      volume: 0.2
      pitch: 0.2
  '$':
    access:
      type: PORTAL_TRIGGER
      volume: 1
      pitch: 0.2
    no-access:
      type: ANVIL_LAND
      volume: 0.2
      pitch: 0.2
```
