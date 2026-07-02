---
description: Here you'll find how to make your own island bank menu from scratch.
---

# Island Bank Menu

### General Sections

First, give your menu a custom name by adding a `title (string)` section. After that, you may configure other general options of your menu: `previous-menu (boolean)` to enable opening of previous menu when closing the menu; `type (string)` to set the inventory-type of the menu; `open-sound (sound)` for setting a custom sound when opening the menu.

{% hint style="info" %}
You may find a list of valid inventory-types [on this link](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html).
{% endhint %}

### Pattern Section

Let's work on the pattern section. The pattern section is the area where you can configure the layout of your menu. It is a list of strings that each char in them represents a different item that will be displayed in your menu. The pattern list should contain a list of 1 to 6 lines that each will have 9 chars - spaces are not counted as chars. If you have two same chars in different slots, then the items in these slots will be identical. Configuring how items will look like is not done here, but in the `items` section.

### Island-Bank Related Sections

The island-bank menu has additional sections that can be configured. Simply set them as a custom char from your pattern in order to make that item a custom button.

| Field Name | Field Type | Description                                                          |
| ---------- | ---------- | --------------------------------------------------------------------- |
| `balance`  | Char       | A custom button that displays the balance of the island's bank.      |
| `logs`     | Char       | The button that opens the [bank logs menu](bank-logs-menu.md).       |

### Items Section

That's the place where you configure your items. You can find a tutorial on how to properly configure an item [here](https://wiki.bg-software.com/superiorskyblock/menus#editing-items-in-the-menu).

#### Bank Action Items

In order to create deposit and withdraw buttons, the items should be configured with a special `bank-action` section. This section should contain either a `deposit` field or a `withdraw` field.

The value of the field can be a percentage (double): `100.0` will deposit/withdraw all the money, `50.0` will deposit/withdraw half of it, and `0.0` will ask the player to enter a custom amount in the chat.

```yaml
'!':
  type: STAINED_GLASS_PANE
  data: 5
  name: '&aDeposit Half Money'
  bank-action:
    deposit: 50.0
```

Instead of a percentage, the value can also be a list of commands that will be executed by the console when the transaction succeeds. The placeholder {0} will be replaced with the name of the player, and {1} will be replaced with the amount of the transaction.

#### Custom Placeholders

The `balance` item supports custom placeholders!\
&#x20;       {0} - The bank's balance.\
&#x20;       {1} - The bank's balance, formatted with commas.\
&#x20;       {2} - The bank's balance, formatted with `K` for thousands, `M` for millions, etc.\
&#x20;       {3} - The bank's limit.\
&#x20;       {4} - The bank's limit, formatted with commas.\
&#x20;       {5} - The bank's limit, formatted with `K` for thousands, `M` for millions, etc.\
&#x20;       {6} - The last time interest was given.\
&#x20;       {7} - The next time interest will be given.

### Sounds Section

In this section you can configure custom sounds that will be played when players click the items in the menu. You can find a tutorial on how to properly configure sounds [here](https://wiki.bg-software.com/superiorskyblock/menus#giving-sounds-to-items).

Bank action items support two special sound sections instead of a regular sound: `success-sound`, which is played when the transaction succeeds, and `fail-sound`, which is played when the transaction fails.

```yaml
sounds:
  '!':
    success-sound:
      type: ORB_PICKUP
      volume: 0.2
      pitch: 0.2
    fail-sound:
      type: ANVIL_LAND
      volume: 0.2
      pitch: 0.2
```

### Commands Section

In this section you can configure custom commands that will be executed when players click the items in the menu. You can find a tutorial on how to properly configure commands [here](https://wiki.bg-software.com/superiorskyblock/menus#running-custom-commands).

### Permissions Section

In this section you can configure required-permissions for your items that players must have before they can click an item. You can find a tutorial on how to properly configure permissions [here](https://wiki.bg-software.com/superiorskyblock/menus#permissions-section).

### Menu Example

This is the default island-bank menu, which includes most of the technics and features stated in this tutorial.

```yaml
title: '&lIsland Bank'
previous-menu: true

pattern:
  - '= - @ @ @ @ @ - ='
  - '- @ ! @ @ @ % @ -'
  - '@ # @ @ * @ @ ^ @'
  - '- @ $ @ @ @ & @ -'
  - '= - @ @ ~ @ @ - ='

balance: '*'
logs: '~'

items:
  '!':
    type: STAINED_GLASS_PANE
    data: 5
    name: '&aDeposit Half Money'
    lore:
      - '&7Deposit half of your money into the bank.'
    bank-action:
      deposit: 50.0
  '#':
    type: STAINED_GLASS_PANE
    data: 5
    name: '&aDeposit Money'
    lore:
      - '&7Deposit money into the bank.'
    bank-action:
      deposit: 0.0
  '$':
    type: STAINED_GLASS_PANE
    data: 5
    name: '&aDeposit All Money'
    lore:
      - '&7Deposit all of your money into the bank.'
    bank-action:
      deposit: 100.0
  '%':
    type: STAINED_GLASS_PANE
    data: 14
    name: '&aWithdraw Half Money'
    lore:
      - '&7Withdraw half of the money from the bank.'
    bank-action:
      withdraw: 50.0
  '^':
    type: STAINED_GLASS_PANE
    data: 14
    name: '&aWithdraw Money'
    lore:
      - '&7Withdraw money from the bank.'
    bank-action:
      withdraw: 0.0
  '&':
    type: STAINED_GLASS_PANE
    data: 14
    name: '&aWithdraw All Money'
    lore:
      - '&7Withdraw all of the money from the bank.'
    bank-action:
      withdraw: 100.0
  '*':
    type: PAPER
    name: '&6Balance'
    lore:
      - '&7Your bank currently has ${2}'
      - '&7Next interest on {7}'
  '=':
    type: EMERALD_BLOCK
    name: '&f '
  '-':
    type: EMERALD
    name: '&f '
  '~':
    type: EXP_BOTTLE
    name: '&6Transaction Logs'

sounds:
  '!':
    success-sound:
      type: ORB_PICKUP
      volume: 0.2
      pitch: 0.2
    fail-sound:
      type: ANVIL_LAND
      volume: 0.2
      pitch: 0.2
  '~':
    type: ORB_PICKUP
    volume: 0.2
    pitch: 0.2
```
