---
description: >-
  The plugin has a feature to override spawners behavior. When enabled, the
  plugin will override the spawning mechanism of spawners and will add
  optimizations to the spawning mechanism of the game.
---

# Spawners Override

## Optimizations

The plugin aims to solve as many lag issues as possible from spawners, and by enabling the spawners-override feature, it can run more optimizations than usual on spawners by overriding the vanilla mechanism of spawning entities.

#### Vanilla Mechanism

The spawning mechanism of the vanilla is as follows:

1. The spawner creates an entity without spawning it to the world.
2. The spawner chooses a random location in its spawning range.\
   If it cannot spawn the entity in this location, it goes back to step 1.
3. The spawner checks for other spawning conditions, such as difficulty of the server, lights in the location and custom conditions for each entity.\
   If any of the conditions fails, it goes back to step 1.
4. The spawner looks for the amount of nearby entities and makes sure it's below the maximum allowed.
5. The spawner adds the entity to the world.

As you can see, some of the tasks can be skipped if we consider entity-stacking and linked-entity stacking. With that being said, WildStacker solves the problem:

#### WildStacker Mechanism

1. The spawner creates a entity without spawning it to the world.
2. The spawners checks for nearby entities in the spawning range.\
   WildStacker checks in this list if there's an entity that can get stacked. This check works as follows:\
   \- First, checking if the linked entity is valid. If it does, we have a match.\
   \- Secondly, checking if one of the nearby entities can be stacked.
3. WildStacker picks a random number between the spawner's stack size and the spawn count times the spawner's size. This number will be the amount of mobs to spawn and will always be:\
   \`\<spawner-stack-size> <= Random Number <= (\<spawner-stack-size> \* \<spawn-count>)\`\
   WildStacker uses an algorithm to pick a random number that will most likely be the middle between the edges, and have less chance to be close to the edges.
4. WildStacker will try to add the number that was picked to the target entity. If the new stack size of the target entity doesn't exceed the limit, then the task of spawning ends.
5. WildStacker will take the amount of entities left to spawn, and will try to spawn only one stacked entity instead of a few different ones - following vanilla's mechanism.

WildStacker's mechanism tries to predict the amount of entities to spawn before calculating locations for them, and tries to "add" them to the world by only changing other entities' stack sizes instead of actually spawning the entities. Both of these tasks make the spawning algorithm much more optimized and results can be seen in game.



## Custom Spawning Conditions

As described above, WildStacker overrides the spawning mechanism of entities. This means it can also ignore the vanilla spawning conditions of entities, and instead run its own conditions. The plugin lets you configure these conditions, and more about them can be read [here](https://app.gitbook.com/s/-MjGaELpevur-9lym3B_/~/changes/P6YYaP2zDN4S0zR7EzeD/wildstacker/description/spawners-stacker/spawners-override/spawn-conditions).&#x20;
