---
description: >-
  The plugin can stack similar items together and reduce the amount of items in
  your world and the lag caused by those items.
---

# Items Stacker

## Stacking Algorithm

The plugin uses a simple but efficient way of stacking items together:

#### Stacking Trigger occurs

There are plenty of triggers that will cause the plugin to attempt and stack two items together. This is the first step in the stacking process, and more about the triggers can be found below.

#### Nearby Items Check

The plugin will look for nearby items, and proceed to the next step. Only nearby items that meet range criteria will be potential items to be stacked. The plugin will cache the results for 5 seconds so items lookups can be more optimized.

#### Item Similar Check

The plugin will attempt to stack two items together only if they are similar in their item types, metadata and the only difference between the items is their amount.

#### Stacking Items

The last and most important step. The plugin will stack the two items together: it will take the amount of the first stack and add it to the second. Then it will remove the first one from the world, and play a nice partical.

## Stacking Triggers

The plugin will attempt to stack items when one of the following events occur:

* Item spawns into the world.
* Every cycle of the stack-task of items.
* Two entities are naturally merging (vanilla's mechanism of merging items)
