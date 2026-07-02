---
description: Here you'll find how to make your own values menu from scratch.
---

# Values Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

The title of this menu supports custom placeholders: {0} - the name of the island's owner; {1} - the worth of the island; {2} - the worth of the island, formatted with `K` for thousands, `M` for millions, etc.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Block Value Items

The values menu displays the worth and level values of specific blocks on the island. In order to achieve that, the menu must be configured with special type of buttons that will make this work.

These special-type buttons follow the format of regular items, with one additional field that should be given to them:

| Field Name | Field Type | Description                                                                                                                        |
| ---------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `block`    | String     | The block to track. Can be a material name (for example `IRON_BLOCK`) or a spawner with an entity (for example `MOB_SPAWNER:BLAZE`). |

#### Custom Placeholders

The block value items support custom placeholders!\
&#x20;       {0} - The amount of the blocks on the island.\
&#x20;       {1} - The total worth of the blocks.\
&#x20;       {2} - The total level of the blocks.\
&#x20;       {3} - The total worth of the blocks, formatted with `K` for thousands, `M` for millions, etc.\
&#x20;       {4} - The total level of the blocks, formatted with `K` for thousands, `M` for millions, etc.

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is a shortened version of the default values menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '{0} &n${1}'
previous-menu: true

pattern:
  - '& & & & & & & & &'
  - '% $ A B C D E F %'
  - '% % G H I J K L %'
  - '% * M N O P Q R %'
  - '% % S T U V W X %'
  - '& & & & & & & & &'

items:
  '&':
    type: STAINED_GLASS_PANE
    data: 15
    name: '&f'
  '$':
    type: MOB_SPAWNER
    name: '&e&lSPAWNERS ->'
    flags:
      - HIDE_ATTRIBUTES
  '*':
    type: BOOK_AND_QUILL
    name: '&e&lITEMS ->'
  'A':
    block: MOB_SPAWNER:IRON_GOLEM
    type: SKULL_ITEM
    data: 3
    skull: 'eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvODkwOTFkNzllYTBmNTllZjdlZjk0ZDdiYmE2ZTVmMTdmMmY3ZDQ1NzJjNDRmOTBmNzZjNDgxOWE3MTQifX19'
    name: '&e&l[!] &7Iron Golem Spawner'
    lore:
      - '&6&l* &e&lQuantity &fx{0}'
      - '&6&l* &e&lWorth: &f${1}'
      - '&6&l* &e&lLevel: &f${2}'
  'M':
    block: HOPPER
    type: HOPPER
    name: '&e&l[!] &7Hopper'
    lore:
      - '&6&l* &e&lQuantity &fx{0}'
      - '&6&l* &e&lWorth: &f${1}'
      - '&6&l* &e&lLevel: &f${2}'
  'O':
    block: IRON_BLOCK
    type: IRON_BLOCK
    name: '&e&l[!] &7Iron Block'
    lore:
      - '&6&l* &e&lQuantity &fx{0}'
      - '&6&l* &e&lWorth: &f${1}'
      - '&6&l* &e&lLevel: &f${2}'
  # ... more block items follow the same format ...
```
