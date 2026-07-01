# IslandMissions

The IslandMissions jar handles tracking island events. Using this jar, you can give players missions that can be completed once an event is fired. The mission checks when an event is fired and a configured condition is met.

## Required Sections

### events

List of events that are required to complete the mission.

Example for usage of this section can be found below.

{% hint style="info" %}
You can find a list of events available [here](https://github.com/BG-Software-LLC/SuperiorSkyblock2/tree/master/API/src/main/java/com/bgsoftware/superiorskyblock/api/events).\
Only islands related events can be used.
{% endhint %}

{% hint style="info" %}
You can add "-target" to track data for target players in events.\
For example, when using IslandKickEvent, by default - the event will be tracked for the player that did the operation (the /is kick command). However, by adding "-target" to the event ("IslandKickEvent-target"), the event will be tracked for the player that was kicked.
{% endhint %}

#### Section Type

Configuration Section

## Optional Sections

### success-check

Condition that must be met for completing a mission. The evaluation of the condition must be true or false.

This requires knowledge in Java. You can use `event` as a variable for the event that was called.

#### Section Type

String

## Example

```yaml
# The mission file to use
mission-file: IslandMissions

# Whether the mission should be given when completing all requirements.
auto-reward: true

# Should block counts of players get reset when completing the mission?
reset-after-finish: true

# Rewards given when completing the mission.
rewards:
  commands:
    - 'eco give %player% 25000'
    - 'is admin msg %player% &e&lExplorer | &7Successfully finished the mission Nether Explorer!'
    - 'is admin msg %player% &e&lExplorer | &7Are you ready for the real challenge?'
    - 'is admin msg %player% &e&lExplorer | &7&oFor more information about the next mission, checkout /is missions'

# List of events that will trigger the mission.
events:
  - IslandSchematicPasteEvent

# Requirement of the event to complete the mission.
success-check: 'event.getSchematic().endsWith("_nether")'

# Icons used in the menus.
icons:
  not-completed:
    type: PAPER
    name: '&aNether Explorer'
    lore:
      - '&7Go to the Nether.'
      - ''
      - '&6Rewards:'
      - '&8 - &7$25,000'
      - ''
      - '&c&l ✘ &7Not Completed'
  can-complete:
    type: PAPER
    name: '&aNether Explorer'
    lore:
      - '&7Go to the Nether.'
      - ''
      - '&6Rewards:'
      - '&8 - &7$25,000'
      - ''
      - '&a&l ✔ &7Click to redeem your reward.'
    enchants:
      DURABILITY: 1
    flags:
      - HIDE_ENCHANTS
  completed:
    type: MAP
    name: '&aNether Explorer'
    lore:
      - '&7Go to the Nether.'
      - ''
      - '&6Rewards:'
      - '&8 - &7$25,000'
      - ''
      - '&a&l ✔ &7Already Claimed.'
```
