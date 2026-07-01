# StatisticsMissions

The StatisticsMissions jar handles tracking of statistics. Using this jar, you can give players missions that they need to get certain statistics. The mission checks when statistics are gained, and track data accordingly.

## Required Sections

### required-statistics

List of statirtics that are required to complete the mission.

Example for usage of this section can be found below.

#### Section Type

Configuration Section

## Example

```yaml
# The mission file to use
mission-file: StatisticsMissions

# Whether the mission should be given when completing all requirements.
auto-reward: true

# Rewards given when completing the mission.
rewards:
  commands:
    - 'eco give %player% 1000'
    - 'is admin msg %player% &e&lFly | &7Successfully finished the mission Fly I!'
    - 'is admin msg %player% &e&lFly | &7&oFor more information about the next mission, checkout /is missions'

# List of all required blocks must be gathered in order to complete the mission.
required-statistics:
  '1':
    statistics:
      - 'FLY_ONE_CM'
    amount: 1000

# Icons used in the menus.
icons:
  not-completed:
    type: PAPER
    name: '&aFly I'
    lore:
      - '&7Fly 1,000 blocks.'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Blocks Flew: &7{value_fly_one_cm}/1000'
      - '&6Progress: &7{0}%'
      - '&c&l ✘ &7Not Completed'
  can-complete:
    type: PAPER
    name: '&aFly I'
    lore:
      - '&7Fly 1,000 blocks.'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Blocks Flew: &71000/1000'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Click to redeem your reward.'
    enchants:
      DURABILITY: 1
    flags:
      - HIDE_ENCHANTS
  completed:
    type: MAP
    name: '&aFly I'
    lore:
      - '&7Fly 1,000 blocks.'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Blocks Flew: &71000/1000'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Already Claimed.'
```
