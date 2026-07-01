# KillsMissions

The KillsMissions jar handles tracking of mobs killing in islands. Using this jar, you can give players missions that they need to kill mobs. The mission checks when an entity is killed, and track data accordingly.

## Required Sections

### required-entities

List of entities that are required to complete the mission.

Example for usage of this section can be found below.

#### Section Type

Configuration Section

## Example

```yaml
# The mission file to use
mission-file: KillsMissions

# Whether the mission should be given when completing all requirements.
auto-reward: true

# Should block counts of players get reset when completing the mission?
reset-after-finish: true

# Rewards given when completing the mission.
rewards:
  commands:
    - 'eco give %player% 1000'
    - 'is admin msg %player% &e&lSlayer | &7Successfully finished the mission Slayer I!'
    - 'is admin msg %player% &e&lSlayer | &7Your sword hasnt seen blood yet... Kill more mobs!'
    - 'is admin msg %player% &e&lSlayer | &7&oFor more information about the next mission, checkout /is missions'

# List of all required blocks must be gathered in order to complete the mission.
required-entities:
  '1':
    types:
      - 'SKELETON'
      - 'CREEPER'
      - 'ZOMBIE'
      - 'SPIDER'
    amount: 5

# Icons used in the menus.
icons:
  not-completed:
    type: PAPER
    name: '&aSlayer I'
    lore:
      - '&7Kill 5 hostile mobs.'
      - ''
      - '&6Required Kills:'
      - '&8 - &7x5 Skeletons/Creepers/Zombies/Spiders'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Hostiles Killed: &7{1}/5'
      - '&6Progress: &7{0}%'
      - '&c&l ✘ &7Not Completed'
  can-complete:
    type: PAPER
    name: '&aSlayer I'
    lore:
      - '&7Kill 5 hostile mobs.'
      - ''
      - '&6Required Kills:'
      - '&8 - &7x5 Skeletons/Creepers/Zombies/Spiders'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Hostiles Killed: &75/5'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Click to redeem your reward.'
    enchants:
      DURABILITY: 1
    flags:
      - HIDE_ENCHANTS
  completed:
    type: MAP
    name: '&aSlayer I'
    lore:
      - '&7Kill 5 hostile mobs.'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Hostiles Killed: &75/5'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Already Claimed.'
```
