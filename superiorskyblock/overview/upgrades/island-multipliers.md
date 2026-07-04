---
description: >-
  The plugin gives you the ability to change different multipliers using the
  upgrades system.
---

# Island Multipliers

## Crop Growth

The crop-growth multiplier changes the rates of growth of crops in the island.&#x20;

In order to understand how the crop-growth work, you must understand first how it works in vanilla. To do that, you must under a few concepts beforehand:

#### Chunks

Chunks (16x16 areas of the world) are stored in the backend in sections - each for a 16x16x16 blocks.

#### Ticks

The server is running in intervals of ticks, which each tick last 50 milliseconds (so 20 ticks in a second).

#### Ticked Blocks

"ticking", "ticked blocks", etc; are all referred to blocks that can be grown as crops for this discussion.

Every tick the server is running, it iterates through all the loaded chunks in the world that can be ticked (in general, loaded chunks that players are close enough to them) and tries to tick blocks inside these chunks. For each of these chunks, the server iterates through each one of its sections and chooses a number of blocks to try and tick. How does the server choose this number? Game rules! The game rule `randomTickSpeed` determines exactly that. It randomly picks up blocks in each chunk section (according to the `randomTickSpeed` value) and checks if they can get ticked. If they do, it runs a tick for them. In game, you'll see the block grow.

Now that you have better understanding of the vanilla mechanism, that's the time to discuss how the plugin handles the multiplier. As you can guess, it's almost impossible to get an exact multiplier for crops due to the randomness of picking up blocks. However, the plugin can multiply the amount of blocks to tick, and that's exactly what it does. Instead of only ticking `randomTickSpeed` blocks, it actually tries to tick `randomTickSpeed * <crop-growth multiplier> * <crops-interval>` amount of blocks (The multiplication by the `crops-interval` is done because the plugin doesn't tick blocks every tick - configured)

## Spawner Rates

The spawner-rates multiplier changes the delay of spawners for running the next spawning waves.\
For this discussion, `spawner wave(s)` is referred to the action where the spawner spawn a group of entities. This action can be done across a few tick or get completed in one tick, depends on the game.

After a spawner wave is done, the plugin waits a few ticks (5 to be exact) and reduces the delay for the next wave. The delay in reducing the spawner-wave delay is to ensure the current spawner wave is completely done, and the new delay of the spawner was already set by the game. Because the wave can last for more than a tick, the plugin must ensure that the wave is completed before changing the delay.

The plugin changes the delay by simply taking the current delay and dividing it by the spawner-rates multiplier of the island. The plugin makes sure that the spawner-rate is above 1 before doing the action. Division (even in small values) can dramatically reduce the delay of spawners, and therefore it's advised to use small values (even decimals if possible) - spawning a lot of entities may cause server-lag. &#x20;

## Mob Drops

The mob-drops multiplier changes the amount of items that are dropped from mobs in the island.

{% hint style="info" %}
The multiplier changes the amount of items that were dropped; it doesn't increase the chances of other items to drop.
{% endhint %}

Once a mob dies, the plugin iterates through all the items that were dropped by the entity, and multiply their amount by the drops-multiplier. If the new amount exceeds the maximum stack-size of the item, the plugin will drop additional items.

The plugin makes sure to not multiply equipment (armor, hand items, chest contents, etc) of entities to prevent duplication glitches.
