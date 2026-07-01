# EnchantingMissions

The EnchantingMissions jar handles tracking of enchanting items in islands. Using this jar, you can give players missions that they need to enchant certain items. The mission checks when players enchant items, and track data accordingly.

## Required Sections

### required-enchants

List of enchantments that are required to complete the mission.

Example for usage of this section can be found below.

#### Section Type

Configuration Section

## Optional Sections

### enchanted-placeholder

Placeholder that will be used in the item for a completed enchantment.

#### Section Type

String

#### Default Value

Yes

### not-enchanted-placeholder

Placeholder that will be used in the item for a not-completed enchantment.

#### Section Type

String

#### Default Value

Yes

## Example

```yaml
# The mission file to use
mission-file: EnchantingMissions

# Whether the mission should be given when completing all requirements.
auto-reward: true

# Rewards given when completing the mission.
rewards:
  commands:
    - 'eco give %player% 1000'
    - 'is admin msg %player% &e&lEnchanter | &7Successfully finished the mission Enchanter I!'
    - 'is admin msg %player% &e&lEnchanter | &7Now that you are familiar with enchantments, lets go advanced.'
    - 'is admin msg %player% &e&lEnchanter | &7&oFor more information about the next mission, checkout /is missions'

# List of all required blocks must be gathered in order to complete the mission.
required-enchants:
  '1':
    types:
      - 'DIAMOND_HELMET'
    enchants:
      PROTECTION_ENVIRONMENTAL: 4
    amount: 1
  '2':
    types:
      - 'DIAMOND_CHESTPLATE'
    enchants:
      PROTECTION_ENVIRONMENTAL: 4
    amount: 1
  '3':
    types:
      - 'DIAMOND_LEGGINGS'
    enchants:
      PROTECTION_ENVIRONMENTAL: 4
    amount: 1
  '4':
    types:
      - 'DIAMOND_BOOTS'
    enchants:
      PROTECTION_ENVIRONMENTAL: 4
    amount: 1

# Icons used in the menus.
icons:
  not-completed:
    type: PAPER
    name: '&aEnchanter I'
    lore:
      - '&7Enchant a full diamond armor with protection 4'
      - ''
      - '&6Required Enchantments:'
      - '&8 - &7x1 Diamond Helmet (Protection IV)'
      - '&8 - &7x1 Diamond Chestplate (Protection IV)'
      - '&8 - &7x1 Diamond Leggings (Protection IV)'
      - '&8 - &7x1 Diamond Boots (Protection IV)'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Diamond Helmet: &7{enchanted_diamond_helmet}'
      - '&6Diamond Chestplate: &7{enchanted_diamond_chestplate}'
      - '&6Diamond Leggings: &7{enchanted_diamond_leggings}'
      - '&6Diamond Boots: &7{enchanted_diamond_boots}'
      - '&6Progress: &7{0}%'
      - '&c&l ✘ &7Not Completed'
  can-complete:
    type: PAPER
    name: '&aEnchanter I'
    lore:
      - '&7Enchant a full diamond armor with protection 4'
      - ''
      - '&6Required Enchantments:'
      - '&8 - &7x1 Diamond Helmet (Protection IV)'
      - '&8 - &7x1 Diamond Chestplate (Protection IV)'
      - '&8 - &7x1 Diamond Leggings (Protection IV)'
      - '&8 - &7x1 Diamond Boots (Protection IV)'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Diamond Helmet: &7Yes'
      - '&6Diamond Chestplate: &7Yes'
      - '&6Diamond Leggings: &7Yes'
      - '&6Diamond Boots: &7Yes'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Click to redeem your reward.'
    enchants:
      DURABILITY: 1
    flags:
      - HIDE_ENCHANTS
  completed:
    type: MAP
    name: '&aEnchanter I'
    lore:
      - '&7Enchant a full diamond armor with protection 4'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - ''
      - '&6Diamond Helmet: &7Yes'
      - '&6Diamond Chestplate: &7Yes'
      - '&6Diamond Leggings: &7Yes'
      - '&6Diamond Boots: &7Yes'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Already Claimed.'
```
