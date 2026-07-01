---
description: >-
  Loot tables are used to store all the loot data of entities. Using this
  system, the plugin can calculate drops for large amount of mobs.
---

# Loot Tables

The plugin uses predefined loot tables in order to calculate drops for large amount of entities more easily. The plugin also lets you modify the values of the drops and alter the vanilla dropped items of mobs.

{% hint style="danger" %}
This system cannot be disabled, otherwise calculations of drops may be wrong and cause lag to your server.
{% endhint %}

## Loot Tables

Every file is represented as a "loot table". Loot tables contain global settings and pairs. Pairs contain the items, and can be manipulated differently to get different results.

#### Example

```yaml
{
  # We don't want equipment to be dropped.
  "dropEquipment": false,
  # We want a random exp value between 5 and 8.
  "exp": {
    "min": 5,
    "max": 8,
    # Should exp be dropped no matter how the entity was killed?
    "always-drop": true
  },
  # We want a maximum amount of 2 pairs, but at least 1 pair to be chosen.
  "min": 1,
  "max": 2,
  # All the pairs of items are going here
  "pairs": [
  ...
  ]
}
```

## Loot Pairs

Each loot-pair contains configuration about a group of items that will be dropped. When drops are calculated, the plugin chooses loot-pairs to drop, and then it chooses items from these loot-pairs, depend on the configuration of the loot-pairs.

#### Example

```yaml
{
  # All settings related to the table
  ...
  "pairs": [
    # First Pair
    {
      # This pair should always be chosen (100%)
      "chance": 100,
      # Chance is [base-chance] + ([looting-level] * [looting-chance])
      "lootingChance": 2.5,
      # A required permission for the pair to be chosen.
      "permission": "my.permission",
      # A list of items for this pair
      "items": [
        ...
      ]
    },
    # Second Pair
    {
      # This pair will be chosen only if the entity was killed by a player.
      "killedByPlayer": true,
      # This pair will be chosen only 50% of the times.
      "chance": 50,
      # A required spawn cause for the entity so the pair will be chosen.
      "spawn-cause": "SPAWNER",
      # A list of items for this pair
      "items": [
        ...
      ]
    },
    # Third Pair
    {
      # This pair will be chosen only if the entity was killed by an enderman.
      "killer": [
        "ENDERMAN"
      ],
      # This pair will be chosen only 50% of the times.
      "chance": 50,
      # A list of commands for this pair
      "commands": [
        ...
      ]
    }
  ]
}
```

### Advanced Filtering

You can create more complex filtering for loot pairs (as well as loot items) using the advanced filtering format. The format is very simple and doesn't require much from you. Instead of making `killer` as a list of strings, you should create it as a list of json objects with one required field, which is `type`. Then, you can add additional fields for filtering mobs by their attributes which you can get by using the `/data get entity` command.

Here's an example of a loot pair for magma cubes killed by frogs in 1.19:

```json
{
  "killer": [
    "FROG"
  ],
  "chance": 100,
  "items": [
    {
      "killer": [
        {
          "type": "FROG",
          "variant": "minecraft:warm"
        }
      ],
      "type": "PEARLESCENT_FROGLIGHT",
      "chance": 100
    },
    {
      "killer": [
        {
          "type": "FROG",
          "variant": "minecraft:cold"
        }
      ],
      "type": "VERDANT_FROGLIGHT",
      "chance": 100
    },
    {
      "killer": [
        {
          "type": "FROG",
          "variant": "minecraft:temperate"
        }
      ],
      "type": "OCHRE_FROGLIGHT",
      "chance": 100
    }
  ]
}
```

In the example above, magma cubes will drop different froglight blocks depending on the variant of the frog. The `variant` field name was taken directly from the `/data get entity` command, as well as the value of the field. In the background, the plugin does exactly the same - it takes the output of this command and compares it to your filters.

Besides that, you can use `!` to negate an entity from a filter. For example, the following filter will apply to all the mobs that are not blazes:

```json
"killer": [
  "!BLAZE"
]
```

The negate symbol works on entity types, spawn causes and death causes.

## Loot Items

Each loot-item represents an item that can be dropped from a mob. It contains configuration about the item itself (its type, name, lore, etc), the amount of the item to be dropped, chance of the item to be dropped and more.

#### Example

```yaml
{
  # All settings related to the table
  ...
  "pairs": [
    {
      # All settings related to the pair
      ...
      "items": [
        # First item
        {
          # The material type of the item
          "type": "DIAMOND_SWORD",
          # The data value of the item
          "data": 0,
          # A custom name for the item.
          "name": "&6Diamond Sword!!",
          # A custom lore for the item.
          "lore": [
            "&7First line!",
            "&4Second line!"
          ],
          # The chance of this item to be chosen.
          "chance": 50,
          # Minimum amount for the item
          "min": 1,
          # Maximun amount for the item
          "max": 1,
          # A list of enchantments that will be applied to the item.
          "enchants": {
            # First enchantment - Sharpness 5
            "DAMAGE_ALL": 5,
            # Second enchantment - Looting 3
            "LOOT_BONUS_MOBS": 3
          }
        },
        # Second item
        {
          # Values
          ...
          # Should the item amount be increased when using looting?
          # The formula to calculate the item amount is [random number between min and max] + [random number between 0 and the looting level]
          "looting": true,
          # The item will be glowing when dropped (no enchantments will be shown)
          "glow": true,
          # The item that will be dropped if the entity was killed by fire
          "burnable": {
            "type": "COOKED_BEEF",
            "data": 0
          }
        },
        # Third item
        {
          "type": "PLAYER_HEAD",
          # Values
          ...
          # The texture value of the skull.
          # These values can be taken from many sites, such as https://minecraft-heads.com/.
          # The head below will be shown as an orc head.
          "skull": "eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvODJkNmI2MjJmMDZkYmQzYjE5YmY3NjUzOGNhNzA0NzMzZWQwYjAyZTQ0MzhjOWQ4OTY4YTA0YmZiYjI4ZWY2MyJ9fX0=",
          # It is possible to add custom nbt tags to your items.
          "nbt-data": {
            "key1": "Value!",
            "key2": 2
          }
        }
      ]
    }
  ]
}
```

## Loot Commands

Loot commands are similar to items, however instead of dropping an item, you can have a command executed when a mob is killed.

#### Example

```yaml
{
  # All settings related to the table
  ...
  "pairs": [
    {
      # All settings related to the pair
      ...
      "commands": [
        # First command
        {
          # The chance of this command to be chosen
          "chance": 50,
          # Minimum amount for the placeholder
          "min": 1,
          # Maximun amount for the placeholder
          "max": 1,
          # A list of commands that will be ran
          "commands": [
            "give {player-name} diamond {number}",
            "give {player-name} dirt {number}"
          ]
        },
        # Second command
        {
          # The chance of this command to be chosen
          "chance": 50,
          # Minimum amount for the placeholder
          "min": 1,
          # Maximun amount for the placeholder
          "max": 64,
          # A list of commands that will be ran
          "commands": [
            "give {player-name} emerald {number}"
          ]
        }
      ]
    }
  ]
}
```
