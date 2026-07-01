# ItemsMissions

The ItemsMissions jar handles tracking of items in inventories. Using this jar, you can give players missions that they need to hold an item for completion. The mission checks for the items only when the player tries to complete the mission.

## Required Sections

### required-items

List of items that are required to complete the mission.

Example for usage of this section can be found below.

#### Section Type

Configuration Section

## Example

```yaml
# The mission file to use
mission-file: ItemsMissions

# Whether the mission should be given when completing all requirements.
auto-reward: true

# Should item counts of players get reset when completing the mission?
reset-after-finish: true

# Rewards given when completing the mission.
rewards:
  commands:
    - 'eco give %player% 1000'
    - 'is admin msg %player% &e&lCollector | &7Successfully finished the mission Collector I!'
    - 'is admin msg %player% &e&lCollector | &7Now that you collected the nether star, lets look for the next item.'
    - 'is admin msg %player% &e&lCollector | &7&oFor more information about the next mission, checkout /is missions'

# List of all required blocks must be gathered in order to complete the mission.
required-items:
  '1':
    types:
      - 'NETHER_STAR'
    amount: 1

# Icons used in the menus.
icons:
  not-completed:
    type: PAPER
    name: '&aMiner I'
    lore:
      - '&7Collect x1 nether star.'
      - ''
      - '&6Required Items:'
      - '&8 - &7x1 Nether Star'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Nether Star Collected: &70/1'
      - '&6Progress: &7{0}%'
      - '&c&l ✘ &7Not Completed'
  can-complete:
    type: PAPER
    name: '&aMiner I'
    lore:
      - '&7Collect x1 nether star.'
      - ''
      - '&6Required Items:'
      - '&8 - &7x1 Nether Star'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Nether Star Collected: &71/1'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Click to redeem your reward.'
    enchants:
      DURABILITY: 1
    flags:
      - HIDE_ENCHANTS
  completed:
    type: MAP
    name: '&aMiner I'
    lore:
      - '&7Collect x1 nether star.'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Nether Star Collected: &71/1'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Already Claimed.'
```
