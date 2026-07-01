---
description: >-
  The plugin can stack similar entities together and reduce the amount of
  entities in your world and the lag caused by these entities.
---

# Entities Stacker

## Stacking Algorithm

The plugin uses a simple but efficient way of stacking entities together:

#### Stacking Trigger occurs

There are plenty of triggers that will cause the plugin to attempt and stack two entities together. This is the first step in the stacking process, and more about the triggers can be found below.

#### Nearby Entities Check

In many cases, the plugin will attempt to stack the entity to a possible nearby entity, unlike some times where the plugin knows to which target to try and stack the entity. The plugin will look for nearby entities, and proceed to the next step. Only nearby entities that meet range criteria will be potential entities to be stacked. The plugin will cache the results for 5 seconds so entity lookups can be more optimized.

#### Entity Similar Check

The plugin will attempt to stack two entities together only if they are similar. If two entities are similar, then they can get stacked. There are plenty of different checks that the plugin does - more about them can be found below.&#x20;

#### Stacking Entities

The last and most important step. The plugin will stack the two entities together: it will take the amount of the first stack and add it to the second. Then it will remove the first one from the world, and play a nice partical.

## Stacking Triggers

The plugin will attempt to stack entities when one of the following events occur:

* Player dyes a sheep.
* Sheep grows wool.
* Player name tags an entity.
* Entities are bread and stack-after-breed is enabled.
* Entity leaves a vehicle.
* Entity spawns into the world.
* Player shears a sheep and the SHEEP\_SHEAR stack-split is enabled.
* Every cycle of the stack-task.
* Zombie villager is created after villager dies.
* Entity transfroms into another type of entity.
* When minimum-required-entities is enabled and an entity is stacked to another and they don't meet the minimum limit, if there are nearby entities and their total sum exceeds the minimum limit, they will all get stacked together.

## Stacking Checks

{% hint style="info" %}
&#x20;Most of the stack checks listed in this section can be disabled in the config file.

Stack checks with red color cannot be disabled.
{% endhint %}

The plugin will make sure two entities are similar before stacking them together. The following checks are done to ensure it:

* <mark style="color:red;">Entities stacking feature is enabled.</mark>
* <mark style="color:red;">Entities are in the whitelist if it's not empty.</mark>
* <mark style="color:red;">Entities are not in the blacklist.</mark>
* <mark style="color:red;">Entities are not in a disabled world.</mark>
* <mark style="color:red;">The amount of the two entities doesn't exceed the limit.</mark>
* <mark style="color:red;">The names of the entities are not blacklisted.</mark>
* <mark style="color:red;">Entities are alive.</mark>
* <mark style="color:red;">Entities don't have the "bypass-stacking" flag.</mark>
* Entities don't have a nametag.
* <mark style="color:red;">Entities are not corpses.</mark>
* Entities have the same upgrade level.
* Entities have the same nerfed status.
* Entities have the same spawn reason.
* Entities are not in disabled regions.

#### Ageable

* Entities both have the same adult status.
* Entities have the exact same age.

#### Tameable

* Entities have the same owner.
* Entities both have the same tamed status.

#### Animals

* Animals both have the same breeding status.
* Animals both have the same love status.

#### Axolotl

* Axolotls are of the same variant.
* Axolotls both have the same playing-dead status.

#### Bat

* Bats both have the same awake status.

#### Cat

* Cats have the same collar color.
* Cats are of the same type.

#### Creepers

* Creepers both have the same powered status.

#### Enderman

* Endermans carry the same block.

#### Glow Squid

* Glow squids have the same amount of dark ticks.

#### Goat

* Goats both have the same screaming status.

#### Guardian

* Guardians both are Elder Guardian.

#### Horse

* Horses both have the same carrying chest status.
* Horses have the same color.
* Horses have the same jumping strengh.
* Horses have the same max tame progress.
* Horses have the same style.
* Horses are both of the same variant.

#### Llama

* Llamas have the same color.
* Llama have the same strength.

#### Mooshroom

* Mooshrooms are both of the same type.

#### Ocelot

* Ocelots are both of the same type.

#### Parrot

* Parrtos are both of the same variant.

#### Phantom

* Phantoms have the same size.

#### Pig

* Pigs both have the same saddle status.

#### Pufferfish

* Pufferfish both are on the same state.

#### Rabbit

* Rabbits are both of the same type.

#### Sheep

* Sheep both have the same color.
* Sheep both have the same sheared status.

#### Skeleton

* Skeletons are both of the same type.

#### Slime

* Slimes both have the same size.

#### Tropical Fish

* Tropical Fish both have the same body color.
* Tropical Fish both have the same pattern.
* Tropical Fish both have the same color.

#### Villager / Zombie Villager

* Villagers are both in the same profession.

#### Wolf

* Wolves both have the same angry status.
* Wolves both have the same collar color.

#### Zombie

* Zombies both have the same baby status.

#### Zombie Pigman

* Zombie Pigmans both have the same angry status.

#### Mythic Mobs

* <mark style="color:red;">Entities are the same mob-type of MythicMobs.</mark>

#### LevelledMobs

* <mark style="color:red;">Entities have the same level.</mark>
