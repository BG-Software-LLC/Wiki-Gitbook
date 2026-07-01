---
description: >-
  Linked entities is a feature for optimizing lookups of nearby entities when
  entities spawn by spawners.
---

# Linked Entities

When you have the feature enabled, each spawner will have a potential entity to try and stack its future spawning entities to. This means that the spawners on your world will most likely skip the nearby entities lookup, and instead try to stack their entities into a known one.

## Linked Entities Stacking Algorithm

The stacking algorithm when having linked-entities enabled is a bit different, and only affects entities spawned by a spawner.

#### Linked Entity Lookup

If a spawner has an entity already linked to it, it will try to stack the newly spawned entity to this entity first. The stacking will success only if the entity is still alive and it's in the range that was configured. If the stacking succeed, then the stacking process ends and the plugin skips the rest of the lookup. Otherwise, it continues to the next step.

#### Regular Stacking Process

In case of failing to stack into the linked entity, the plugin continues with the regular stacking algorithm, explained in details [here](https://wiki.bg-software.com/wildstacker/description/entities-stacker#stacking-algorithm).

#### Link Entity

If the entity was successfully stacked to another, the plugin will link the target entity to the spawner. If the entity wasn't stacked to any other entities, the plugin will link this entity to the spawner.

This way, every spawner will most likely have a valid linked entity, which should help with the amount of entity lookups that occur. The lookup task may be heavy (depends on your server version), and this system should help with reducing the amount of lookups that are needed to be performed.
