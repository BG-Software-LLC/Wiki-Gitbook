---
description: Here you'll find how to make your own bank logs from scratch.
---

# Bank Logs Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Paged-Type Menu Sections

The bank-logs menu is a paged-menu, which means it displays items from a list of available items - in this case, bank-transactions. Because the amount of bank-transactions can be greater than the amount of available slots, the menu supports multiple pages.

This type of menu requires 4 additional sections: \
`slots` - char of the bank-transaction buttons.\
`previous-page` - char to set a custom button that will get players back to the previous page.\
`current-page` - char to set a custom button that will display the current page players look at.\
`next-page` - char to set a custom button that will get players to the next page.

### Bank-Logs Related Sections

The bank-logs menu have two additional sections that can be configured. The first one is `time-sort`, which you can configure a custom button that will sort the bank-transactions by their creation time. Similar to that, there is `money-sort`, which is a button to sort bank-transactions by the money in the transaction. Simply set them as a custom char from your pattern in order to make that item a custom button.

{% hint style="info" %}
If you don't want one of the custom buttons, simply remove their section from the file.
{% endhint %}

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Custom Placeholders

The items of the paged-menu (`slots`, `previous-page`, etc) support custom placeholders!\
`slots` - \
&#x20;       {0} - The transaction's id\
&#x20;       {1} - The name of the player that made the transaction.\
&#x20;       {2} - The transaction's action (widthraw / deposit)\
&#x20;       {3} - The time the transaction was made.\
&#x20;       {4} - The amount that was transferred in the transaction.\
&#x20;       {5} - The amount that was transferred, formatted with commas.\
&#x20;       {6} - The amount that was transferred, formatted with `K` for thousands, `M` for millions, \
&#x20;               `B` for billions, `T` for trillions and `Q` for quadrillions.\
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

This is an example of a bank-logs menu, which includes most of the technics and features stated in this tutorial.

{% embed url="https://gist.github.com/OmerBenGera/a5278989c3b2bf03ade12c2fafee2b2f" %}
