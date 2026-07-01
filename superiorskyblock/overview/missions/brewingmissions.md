# BrewingMissions

The BrewingMissions jar handles tracking of brewing potions in islands. Using this jar, you can give players missions that they need to brew certain potions. The mission checks when players brew potions, and track data accordingly.

## Required Sections

### required-potions

List of potions that are required to complete the mission.

Example for usage of this section can be found below.

#### Section Type

Configuration Section

## Example

```yaml
# The mission file to use
mission-file: BrewingMissions

# Whether the mission should be given when completing all requirements.
auto-reward: true

# Should block counts of players get reset when completing the mission?
reset-after-finish: true

# Rewards given when completing the mission.
rewards:
  commands:
    - 'eco give %player% 1000'
    - 'is admin msg %player% &e&lBrewer | &7Successfully finished the mission Brewer I!'
    - 'is admin msg %player% &e&lBrewer | &7Now that you are familiar with the brewing stand, lets go advanced.'
    - 'is admin msg %player% &e&lBrewer | &7&oFor more information about the next mission, checkout /is missions'

# List of all required blocks must be gathered in order to complete the mission.
required-potions:
  '1':
    # Brew 1 potion of Speed II.
    potions:
      '1':
        type: SPEED
        upgraded: true
        extended: false
        splash: false
    amount: 1

# Icons used in the menus.
icons:
  not-completed:
    type: PAPER
    name: '&aBrewer I'
    lore:
      - '&7Brew x1 Speed II potion.'
      - ''
      - '&6Required Potions:'
      - '&8 - &7x1 Speed II'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Potions Brewed: &70/1'
      - '&6Progress: &7{0}%'
      - '&c&l ✘ &7Not Completed'
  can-complete:
    type: PAPER
    name: '&aBrewer I'
    lore:
      - '&7Brew x1 Speed II potion.'
      - ''
      - '&6Required Potions:'
      - '&8 - &7x1 Speed II'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Potions Brewed: &71/1'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Click to redeem your reward.'
    enchants:
      DURABILITY: 1
    flags:
      - HIDE_ENCHANTS
  completed:
    type: MAP
    name: '&aBrewer I'
    lore:
      - '&7Brew x1 Speed II potion.'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Potions Brewed: &71/1'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Already Claimed.'
```
