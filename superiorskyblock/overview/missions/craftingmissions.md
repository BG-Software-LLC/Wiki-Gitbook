# CraftingMissions

The CraftingMissions jar handles tracking of crafting items in islands. Using this jar, you can give players missions that they need to craft items in a crafting table. The mission checks when players craft items, and track data accordingly.

## Required Sections

### craftings

List of recipes that are required to complete the mission.

Example for usage of this section can be found below.

#### Section Type

Configuration Section

## Example

```yaml
# The mission file to use
mission-file: CraftingMissions

# Whether the mission should be given when completing all requirements.
auto-reward: true

# Rewards given when completing the mission.
rewards:
  commands:
    - 'eco give %player% 1000'
    - 'is admin msg %player% &e&lCrafter | &7Successfully finished the mission Crafter I!'
    - 'is admin msg %player% &e&lCrafter | &7Now that you are familiar with recipes, lets go advanced.'
    - 'is admin msg %player% &e&lCrafter | &7&oFor more information about the next mission, checkout /is missions'

# List of all required blocks must be gathered in order to complete the mission.
craftings:
  '1':
    type: 'GOLD_BLOCK'
    amount: 1

# Icons used in the menus.
icons:
  not-completed:
    type: PAPER
    name: '&aCrafter I'
    lore:
      - '&7Craft x1 Gold Block'
      - ''
      - '&6Required Craftings:'
      - '&8 - &7x1 Gold Block'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Gold Block Crafted: &7{value_gold_block}/1'
      - '&6Progress: &7{0}%'
      - '&c&l ✘ &7Not Completed'
  can-complete:
    type: PAPER
    name: '&aCrafter I'
    lore:
      - '&7Craft x1 Gold Block'
      - ''
      - '&6Required Craftings:'
      - '&8 - &7x1 Gold Block'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Gold Block Crafted: &71/1'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Click to redeem your reward.'
    enchants:
      DURABILITY: 1
    flags:
      - HIDE_ENCHANTS
  completed:
    type: MAP
    name: '&aCrafter I'
    lore:
      - '&7Craft x1 Gold Block'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Gold Block Crafted: &71/1'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Already Claimed.'
```
