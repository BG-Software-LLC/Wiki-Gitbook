# BlocksMissions

The BlocksMissions jar handles tracking of placement and breaking of blocks in islands. Using this jar, you can give players missions that they need to break certain blocks or place them. The mission checks when players place blocks or break blocks, and track data accordingly.

## Required Sections

### required-blocks

List of blocks that are required to complete the mission.

Example for usage of this section can be found below.

#### Section Type

Configuration Section

## Optional Sections

### only-natural-blocks

Whether to track only natural blocks when players break them.

#### Section Type

Boolean (true/false)

### blocks-placement

When set to true, the mission will track placement of blocks instead of breaking them.

#### Section Type

Boolean (true/false)

### blocks-replace

When set to true, players will be allowed to replace the blocks and gain progress for the misson.

{% hint style="info" %}
This only affects the mission if blocks-placement is set to true.
{% endhint %}

#### Section Type

Boolean (true/false)

## Example

```yaml
# The mission file to use
mission-file: BlocksMissions

# Whether the mission should be given when completing all requirements.
auto-reward: true

# Should block counts of players get reset when completing the mission?
reset-after-finish: true

# Whether only naturally spawned blocks should be counted towards the mission or not.
only-natural-blocks: true

# Rewards given when completing the mission.
rewards:
  commands:
    - 'eco give %player% 1000'
    - 'is admin msg %player% &e&lMiner | &7Successfully finished the mission Miner I!'
    - 'is admin msg %player% &e&lMiner | &7Now that you are familiar with generators, mine some iron.'
    - 'is admin msg %player% &e&lMiner | &7&oFor more information about the next mission, checkout /is missions'

# List of all required blocks must be gathered in order to complete the mission.
required-blocks:
  '1':
    types:
      - 'STONE'
    amount: 48
  '2':
    types:
      - 'COAL_ORE'
    amount: 16

# Icons used in the menus.
icons:
  not-completed:
    type: PAPER
    name: '&aMiner I'
    lore:
      - '&7Mine x48 cobblestone and x16 coal ore.'
      - ''
      - '&6Required Blocks:'
      - '&8 - &7x48 Cobblestone'
      - '&8 - &7x16 Coal Ore'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - '&8 - &7Generator Upgrade'
      - ''
      - '&6Cobblestone Mined: &7{value_stone}/48'
      - '&6Coal Ore Mined: &7{value_coal_ore}/16'
      - '&6Progress: &7{0}%'
      - '&c&l ✘ &7Not Completed'
  can-complete:
    type: PAPER
    name: '&aMiner I'
    lore:
      - '&7Mine x48 cobblestone and x16 coal ore.'
      - ''
      - '&6Required Blocks:'
      - '&8 - &7x48 Cobblestone'
      - '&8 - &7x16 Coal Ore'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - '&8 - &7Generator Upgrade'
      - ''
      - '&6Cobblestone Mined: &748/48'
      - '&6Coal Ore Mined: &716/16'
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
      - '&7Mine x48 cobblestone and x16 coal ore.'
      - ''
      - '&6Rewards:'
      - '&8 - &7$1,000'
      - '&8 - &7Generator Upgrade'
      - ''
      - '&6Cobblestone Mined: &748/48'
      - '&6Coal Ore Mined: &716/16'
      - '&6Progress: &7100%'
      - '&a&l ✔ &7Already Claimed.'
```
