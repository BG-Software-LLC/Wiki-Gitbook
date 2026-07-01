# Regular Chests

The chest mode used to make the chest functional as a vanilla chest. It can later be expanded to do different tasks, such as selling its contents, craft them or have different pages for the chest.

All the different functionalities that chests can have are the followings:

## Sell Chest

The sell chests will automatically sell their contents and deposit the money to the player that placed them. The prices of the items are grabbed automatically from the supported shop plugins.

In order to set a chest as a sell chest, set the `sell-mode` section to true under the chest:

```yaml
chests:
  <chest-name>:
    chest-mode: CHEST
    sell-mode: true
    <other sections>
```

### Deposit Method

You can choose how the chest will deposit to money. It can deposit the money directly to the player's personal bank, or deposit to his island's bank (Supported only for SuperiorSkyblock). By default, the money will be deposited to his personal bank.

You can change this behavior by setting the `deposit-method` section for the chest to `"VAULT"` (Personal banks) or `"SUPERIORSKYBLOCK2"` (Island banks).

## Crafter Chest

The crafter chests will automatically use the contents in the chest to craft predefined recipes. You can configure a list of recipes that the chest will craft for the players. This list cannot be changed by the player, and you'll have to configure different chests that will have different recipes for this task.

You can configure the recipes list by adding a `crafter-chest` section that contains a list of recipes to craft:

```yaml
chests:
  <chest-name>:
    chest-mode: CHEST
    crafter-chest:
      - TNT
```

{% hint style="danger" %}
Avoid choosing two recipes that cause a cycle, as the results are undefined.\
For example, adding `"GOLD_INGOT"` and `"GOLD_BLOCK"` cause this cycle:\
Gold blocks can be crafted using gold ingots, and gold ingots can be crafted using gold blocks.
{% endhint %}

### Hopper Filter

You can configure it so hoppers will only take out items of the crafter chests if these items were crafted by the chest. It will make it so the ingredients for the recipes will not be taken out. You can enable this feature by setting the `hopper-filter` section to true under your chest.

## Auto Suction (Auto Collectors)

The auto suction chests (aka auto collectors) will pickup items in their range into the chest automatically. You can make a chest as an auto collector by adding the `auto-suction` section to it. The `auto-suction` section has two other sections to be configured:

_range_: The range in which items will be collected.

_chunk_: Whether the chest should collect items in the chunk instead of using the range.\
The range will still be used as an indicator to how many y levels to collect items from the chest.

```yaml
chests:
  <chest-name>:
    chest-mode: CHEST
    auto-suction:
      range: 5
      chunk: true
```

{% hint style="info" %}
The chest will pickup items in its chunk if the items are 5 blocks above or below it.
{% endhint %}

### Whitelist

You can configure a list of items that the chest can pickup. Items not in this list will not be picked up by the chest. You can enable it by adding `whitelist` to the chest with a list of items to collect:

```yaml
chests:
  <chest-name>:
    chest-mode: CHEST
    auto-suction:
      ...
    whitelist:
    - DIAMOND
    - IRON_INGOT
```

{% hint style="info" %}
The chest will pickup only diamond and iron ingots.
{% endhint %}

### Blacklist

You can configure a list of items that the chest will not pickup. Items in this list will not be picked up by the chest. You can enable it by adding `blacklist` to the chest with a list of items to filter out:

```yaml
chests:
  <chest-name>:
    chest-mode: CHEST
    auto-suction:
      ...
    blacklist:
    - DIRT
    - COBBLESTONE
```

{% hint style="info" %}
The chest will pickup any item besides dirt and cobblestone.
{% endhint %}

## Large Chest

You can configure more pages to chests and by that making them larger than usual. You can do that by adding a new section `pages` to your chest. The `pages` section should have sub-sections as indicators to the pages of the page. For example, to configure the second page, you'll add a section `'2'` under the `pages` section:

{% hint style="info" %}
The first page can be configured using default sections as mentioned [here](https://wiki.bg-software.com/wildchests/overview/configuring-chests#size).
{% endhint %}

```yaml
chests:
  <chest-name>:
    chest-mode: CHEST
    pages:
      '2':
        ...
      '3':
        ...
```

{% hint style="info" %}
The chest will have 3 pages in total.
{% endhint %}

Each section of page can have the following sections:

_title_: The title of the inventory of the chest in this page.\
This section is required and must be set to all pages.

_price_: The price for purchasing the page.\
This section is optional.

```yaml
chests:
  <chest-name>:
    chest-mode: CHEST
    pages:
      '2':
        price: 500000.0
        title: 'Chest #2'
      '3':
        price: 1000000.0
        title: 'Chest #3'
```

{% hint style="info" %}
The second page will cost $500,000 to upgrade and the third one will cost $1,000,000.
{% endhint %}

### How to Use

You can move between pages in the larger chests by right-clicking and left-clicking outside the inventory's window. Right click is to go to the next page and left clicking to the previous one.

In order to purchase a new page, simply go to your last page and right click as you'll open the next one. Instead of opening a new page, you'll get a message to confirm your purchase. You can either confirm or cancel the operation.
