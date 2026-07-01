# FarmingMissions

The FarmingMissions jar handles tracking of growth of crops in islands. Using this jar, you can give players missions that they need to plant crops. The mission checks when crops grow, and track data for the player that planted them accordingly.

## Required Sections

### required-plants

List of plants that are required to complete the mission.

This value can be one of the followings:

* BAMBOO
* BEETROOT
* CACTUS
* CARROT
* CHORUS\_FLOWER
* CHORUS\_PLANT
* COCOA
* MELON
* POTATO
* PUMPKIN
* SUGAR\_CANE
* SWEET\_BERRY\_BUSH
* WHEAT

Any other blocks may work - make sure you write the exact same material name of the block.

#### Section Type

Configuration Section

## Example

```yaml
# The mission file to use
mission-file: FarmingMissions

# Whether the mission should be given when completing all requirements.
auto-reward: true

# Should block counts of players get reset when completing the mission?
reset-after-finish: true

# Rewards given when completing the mission.
rewards:
  items:
    '1':
      type: BEETROOT_SEEDS
      amount: 1
    '2':
      type: PUMPKIN_SEEDS
      amount: 1
    '3':
      type: MELON_SEEDS
      amount: 1
  commands:
    - 'eco give %player% 2500'
    - 'is admin msg %player% &e&lFarmer | &7Successfully finished the mission Farmer I!'

# List of all required blocks must be gathered in order to complete the mission.
required-plants:
  '1':
    types:
      - 'CARROT'
    amount: 10
  '2':
    types:
      - 'POTATO'
    amount: 10
  '3':
    types:
      - 'WHEAT'
    amount: 10

# Icons used in the menus.
icons:
  not-completed:
    type: PAPER
    name: '&aFarmer I'
    lore:
      - '&7Plant a small farm.'
      - ''
      - '&6Required Plants:'
      - '&8 - &7x10 Carrots'
      - '&8 - &7x10 Potatoes'
      - '&8 - &7x10 Wheat'
      - ''
      - '&6Rewards:'
      - '&8 - &7x1 Beetroot Seed'
      - '&8 - &7x1 Pumpkin Seed'
      - '&8 - &7x1 Melon Seed'
      - '&8 - &7$2,500'
      - ''
      - '&6Grown Carrots: &7{value_carrots}/10'
      - '&6Grown Potatoes: &7{value_potatoes}/10'
      - '&6Grown Wheat: &7{value_wheat}/10'
      - '&6Progress: &7{0}%'
      - '&c&l ✘ &7Not Completed'
  can-complete:
    type: PAPER
    name: '&aFarmer I'
    lore:
      - '&7Plant a small farm.'
      - ''
      - '&6Required Plants:'
      - '&8 - &7x10 Carrots'
      - '&8 - &7x10 Potatoes'
      - '&8 - &7x10 Wheat'
      - ''
      - '&6Rewards:'
      - '&8 - &7x1 Beetroot Seed'
      - '&8 - &7x1 Pumpkin Seed'
      - '&8 - &7x1 Melon Seed'
      - '&8 - &7$2,500'
      - ''
      - '&6Grown Carrots: &710/10'
      - '&6Grown Potatoes: &710/10'
      - '&6Grown Wheat: &710/10'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Click to redeem your reward.'
    enchants:
      DURABILITY: 1
    flags:
      - HIDE_ENCHANTS
  completed:
    type: MAP
    name: '&aFarmer I'
    lore:
      - '&7Plant a small farm.'
      - ''
      - '&6Rewards:'
      - '&8 - &7x1 Beetroot Seed'
      - '&8 - &7x1 Pumpkin Seed'
      - '&8 - &7x1 Melon Seed'
      - '&8 - &7$2,500'
      - ''
      - '&6Grown Carrots: &710/10'
      - '&6Grown Potatoes: &710/10'
      - '&6Grown Wheat: &710/10'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Already Claimed.'
```
