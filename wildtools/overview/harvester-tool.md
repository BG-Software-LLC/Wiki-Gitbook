# Harvester Tool

The harvester tool will harvest crops in range and plant them automatically for players. The tool can also sell automatically the drops of the crops, and farm lands for planting.

## Required Sections

There are some required sections to be added to the config in order to have the tool working properly.

### radius

The radius in which to harvest crops.&#x20;

#### Section Type

Integer (Number, maximum of 2,147,483,647)

## Optional Sections

There are some optional sections that can be used with this tool.

### active-action

Set the activation action for the tool.

#### Section Type

String (`"RIGHT_CLICK"` or `"LEFT_CLICK"` only.)

### farmland-radius

The radius in which to turn dirt into farmlands.

#### Section Type

Integer (Number, maximum of 2,147,483,647)

### one-layer-only

When set, the radius for planting and turning dirt to farmlands will only work on the same y-level of the clicked block.

#### Section Type

Boolean (true/false)

## How to Use

* Hold the tool in your hand.
* Right click or left click on a block (depends on your configuration)\
  By default, right-click should be used

### Sell Mode (Enable/Disable)

{% hint style="info" %}
You must have wildtools.sellmode in order for this to work.
{% endhint %}

* Hold the tool in your hand.
* Sneak (shift-click)
* Right click in the air
