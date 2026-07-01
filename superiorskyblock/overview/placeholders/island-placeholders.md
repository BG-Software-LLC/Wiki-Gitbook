# Island Placeholders

{% hint style="info" %}
The placeholders will show information of the island of the player.\
If you want to get information about the island that the player stands inside, add "location" to the placeholder: `superior_island_location_<placeholder>`
{% endhint %}

### superior\_island\_bank

Get balance of an island.

#### Example Output

1,900,000.00

### superior\_island\_bank\_format

Get balance of an island formatted.

#### Example Output

1.9M

### superior\_island\_bank\_int

Get balance of an island as an integer.

#### Example Output

1900000

### superior\_island\_bank\_raw

Get balance of an island in raw format.

#### Example Output

1900000.00

### superior\_island\_bank\_limit

Get the bank limit of an island.

#### Example Output

1,900,000.00

### superior\_island\_bank\_limit\_format

Get the bank limit of an island formatted.

#### Example Output

1.9M

### superior\_island\_bank\_limit\_int

Get the bank limit of an island as an integer.

#### Example Output

1900000

### superior\_island\_bank\_limit\_raw

Get the bank limit of an island in raw format.

#### Example Output

1900000.00

### superior\_island\_bank\_last\_interest

Get time since last interest.

#### Example Output

1 hour, 55 seconds

### superior\_island\_bank\_next\_interest

Get time until next interest.

#### Example Output

1 hour, 55 seconds

### superior\_island\_bans\_count

Get the count of banned players from the island.

#### Example Output

9000

### superior\_island\_bans\_list

Get the list of banned players from the island.

#### Example Output

Notch, Dinnerbone

### superior\_island\_biome

Get the biome of an island.

### superior\_island\_block\_count\_\<block>

Get the amount of specific blocks in an island.

#### Parameters

_\<block>_: The type of block to check count for.

#### Example Usage

`superior_island_block_count_cobblestone`

### superior\_island\_block\_limit\_\<block>

Get a block limit of a block in an island.

#### Parameters

_\<block>_: The type of block to check limit for.

#### Example Usage

`superior_island_block_limit_cobblestone`

### superior\_island\_bonus\_level

Get the extra level bonus of the island.

#### Example Output

1,900,000.00

### superior\_island\_bonus\_level\_format

Get the extra level bonus of the island formatted.

#### Example Output

1.9M

### superior\_island\_bonus\_level\_int

Get the extra level bonus of the island as an integer.

#### Example Output

1900000

### superior\_island\_bonus\_level\_raw

Get the extra level bonus of the island in raw format.

#### Example Output

1900000.00

### superior\_island\_bonus\_worth

Get the extra worth bonus of the island.

#### Example Output

1,900,000.00

### superior\_island\_bonus\_worth\_format

Get the extra worth bonus of the island formatted.

#### Example Output

1.9M

### superior\_island\_bonus\_worth\_int

Get the extra worth bonus of the island as an integer.

#### Example Output

1900000

### superior\_island\_bonus\_worth\_raw

Get the extra worth bonus of the island in raw format.

#### Example Output

1900000.00

### superior\_island\_center

Get the center location of an island.

#### Example Output

SuperiorWorld, 600, 100, 600

### superior\_island\_center\_x

Get the center x-axis of an island.

### superior\_island\_center\_y

Get the center y-axis of an island.

### superior\_island\_center\_z

Get the center z-axis of an island.

### superior\_island\_chest\_size

Get the amount of island chests unlocked for the island.

### superior\_island\_coop\_limit

Get the coop-limit of an island.

### superior\_island\_coop\_list

Get the list of coops of the island.

#### Example Output

Notch, Dinnerbone

### superior\_island\_coop\_size

Get the amount of coop players in the island.

### superior\_island\_creation\_time

Get the date an island was created.

### superior\_island\_crops\_multiplier

Get the crops multiplier of an island.

### superior\_island\_description

Get the description of the island.

### superior\_island\_discord

Get the discord an the island only if player has access to view it.

### superior\_island\_discord\_all

Get the discord an the island, regardless of permission to view it.

### superior\_island\_drops\_multiplier

Get the mob-drops multiplier of an island.

### superior\_island\_end\_unlocked

Get whether the end world is unlocked for an island.

### superior\_island\_entity\_limit\_\<entity>

Get an entity limit of an entity in an island.

#### Parameters

_\<entity>_: The type of entity to check limit for.

#### Example Usage

`superior_island_entity_limit_creeper`

### superior\_island\_exists

Get whether an island exists.

### superior\_island\_home

Get the home location of the island of the default dimension.

#### Example Output

SuperiorWorld, 600, 100, 600

### superior\_island\_home\_x

Get the home x-axis of the island of the default dimension.

### superior\_island\_home\_y

Get the home y-axis of the island of the default dimension.

### superior\_island\_home\_z

Get the home z-axis of the island of the default dimension.

### superior\_island\_flag\_\<flag>

Get whether an island flag is enabled in an island.

#### Parameters

_\<flag>_: The island flag to check.

#### Example Usage

`superior_island_flag_always_middle_day`

### superior\_island\_is\_coop

Get whether the player is a coop of an island.

### superior\_island\_is\_leader

Get whether the player is the leader of an island.

### superior\_island\_is\_member

Get whether the player is a member of an island.

### superior\_island\_is\_visitor

Get whether the player is a visitor of an island.

### superior\_island\_last\_time\_updated

Get the time since the island last updated.

#### Example Output

1 hour, 55 seconds

### superior\_island\_leader

Get the leader of an island.

### superior\_island\_level

Get the island-level of an island.

#### Example Output

1,900,000

### superior\_island\_level\_format

Get the island-level of an island formatted.

#### Example Output

1.9M

### superior\_island\_level\_int

Get the island-level of an island as an int.

#### Example Output

1900000

### superior\_island\_level\_raw

Get the island-level of an island in a raw format.

#### Example Output

1900000

### superior\_island\_locked

Get whether the island is locked to public.

### superior\_island\_member\_<#>

Get a name of an island member in an island.

#### Parameters

_<#>_: The position of the member to get the name for, ranging from 0.

#### Example Usage

`superior_island_member_0`

### superior\_island\_mission\_status\_\<mission>

Get the completion status of a mission.

#### Parameters

_\<mission>_: The name of the mission to check.

#### Example Usage

`superior_island_mission_status_miner_1`

### superior\_island\_missions\_completed\_\<category>

Get the amount of missions completed for a category.

#### Parameters

_\<category>_: The name of the missions category to check.

#### Example Usage

`superior_island_missions_completed_miner`

### superior\_island\_name

Get the name of an island.\
The name will be colored if color-support is enabled, otherwise stripped.

### superior\_island\_name\_formatted

Get the name of an island.\
The name will be colored despite the color-support.

### superior\_island\_name\_leader

Get the name of an island or leader's name if island doesn't have a name.

### superior\_island\_name\_stripped

Get the name of an island.\
The name will be stripped despite the color-support.

### superior\_island\_nether\_unlocked

Get whether the nether world is unlocked for the island.

### superior\_island\_normal\_unlocked

Get whether the normal world is unlocked for the island.

### superior\_island\_paypal

Get the Paypal of an island only if player has access to view it.

### superior\_island\_paypal\_all

Get the Paypal of an the island, regardless of permission to view it.

### superior\_island\_players\_count

Get the amount of players currently in the island.

### superior\_island\_players\_list

Get the list of players currently in the island.

#### Example Output

Notch, Dinnerbone

### superior\_island\_permission\_\<permission>

Get whether player has a permission in an island.

#### Parameters

_\<permission>_: The island privilege to check.

#### Example Usage

`superior_island_permission_build`

### superior\_island\_radius

Get the radius of an island.

### superior\_island\_rating

Get the rating of an island.

### superior\_island\_rating\_amount

Get amount of ratings there were given to the island.

### superior\_island\_rating\_stars

Get amount of stars an island has.

### superior\_island\_raw\_bank\_limit

Get the bank limit of the island without upgrades values applying to it.

#### Example Output

1,900,000.00

### superior\_island\_raw\_bank\_limit\_format

Get the bank limit of the island without upgrades values applying to it formatted.

#### Example Output

1.9M

### superior\_island\_raw\_bank\_limit\_int

Get the bank limit of the island without upgrades values applying to it as an integer.

#### Example Output

1900000

### superior\_island\_raw\_bank\_limit\_raw

Get the bank limit of the island without upgrades values applying to it in a raw format.

#### Example Output

1900000.00

### superior\_island\_raw\_coop\_limit

Get the coops limit of the island without upgrades values applying to it.

### superior\_island\_raw\_crops\_multiplier

Get the crops multiplier of the island without upgrades values applying to it.

### superior\_island\_raw\_drops\_multiplier

Get the drops multiplier of the island without upgrades values applying to it.

### superior\_island\_raw\_level

Get the level value of an island without bonus applied to it.

#### Example Output

1,900,000.00

### superior\_island\_raw\_level\_format

Get the level value of an island without bonus formatted.

#### Example Output

1.9M

### superior\_island\_raw\_level\_int

Get the level value of an island without bonus as an integer.

#### Example Output

1900000

### superior\_island\_raw\_level\_raw

Get the level value of an island without bonus in a raw format.

#### Example Output

1900000.00

### superior\_island\_raw\_radius

Get the radius of the island without upgrades values applying to it.

### superior\_island\_raw\_spawners\_multiplier

Get the spawners multiplier of the island without upgrades values applying to it.

### superior\_island\_raw\_team\_limit

Get the team limit of the island without upgrades values applying to it.

### superior\_island\_raw\_warps\_limit

Get the warps limit of the island without upgrades values applying to it.

### superior\_island\_raw\_worth

Get the worth value of an island without bonus applied to it.

#### Example Output

1,900,000.00

### superior\_island\_raw\_worth\_format

Get the worth value of an island without bonus formatted.

#### Example Output

1.9M

### superior\_island\_raw\_worth\_int

Get the worth value of an island without bonus as an integer.

#### Example Output

1900000

### superior\_island\_raw\_worth\_raw

Get the worth value of an island without bonus in a raw format.

#### Example Output

1900000.00

### superior\_island\_schematic

Get the schematic used to create the island.

**Example Output**

normal

### superior\_island\_size

Get the size of an island.

#### Example Output

41 x 41

### superior\_island\_size\_format

Get the size of an island rounded to 5.

#### Example Output

40 x 40

### superior\_island\_spawners\_multiplier

Get the spawner-rates multiplier of an island.

### superior\_island\_team\_limit

Get the members-limit of an island.

### superior\_island\_team\_list

Get the list of members of an island.

#### Example Output

Notch, Dinnerbone

### superior\_island\_team\_size

Get the amount of members of an island.

### superior\_island\_team\_size\_online

Get the amount of online members of an island.

### superior\_island\_top\_worth\_position

Get the position of an island sorted by worth-value, ranging from 1.

### superior\_island\_top\_level\_position

Get the position of an island sorted by island-levels, ranging from 1.

### superior\_island\_top\_rating\_position

Get the position of an island sorted by ratings, ranging from 1.

### superior\_island\_top\_players\_position

Get the position of an island sorted by visitors and members inside the island, ranging from 1.

### superior\_island\_unique\_visitors\_count

Get the amount of unique visitors that visited an island.

### superior\_island\_unique\_visitors\_list

Get the list of unique visitors that visited an island.

#### Example Output

Notch, Dinnerbone

### superior\_island\_upgrade\_\<upgrade>

Get a level of an upgrade in an island.

#### Parameters

_\<upgrade>_: The name of the upgrade.

#### Example Usage

`superior_island_upgrade_border_size`

### superior\_island\_uuid

Get the uuid of the island.

### superior\_island\_visitor\_last\_join\_\<name>

Get last time a player visited an island.

#### Parameters

_\<name>_: The name of the player to check.

#### Example Usage

`superior_island_visitor_last_join_notch`

### superior\_islan&#x64;_\__&#x76;isitors\_count

Get the amount of visitors on the island.

### superior\_island\_visitors\_list

Get the list of visitors on the sland.

#### Example Output

Notch, Dinnerbone

### superior\_islan&#x64;_\__&#x76;isitors\_location

Get the visit location of an island.

#### Example Output

SuperiorWorld, 600, 100, 600

### superior\_islan&#x64;_\__&#x76;isitors\_location\_x

Get the visit location's x-axis of an island.

### superior\_islan&#x64;_\__&#x76;isitors\_location\_y

Get the visit location's y-axis of an island.

### superior\_islan&#x64;_\__&#x76;isitors\_location\_z

Get the visit location's z-axis of an island.

### superior\_island\_warps

Get amount of warps of an island.

### superior\_island\_warps\_limit

Get the limit of warps of an island.

### superior\_island\_world

Get the name of the world of an island.

### superior\_island\_worth

Get the worth-value of an island.

#### Example Output

1,900,000

### superior\_island\_worth\_format

Get the worth-value of an island formatted.

#### Example Output

1.9M

### superior\_island\_worth\_int

Get the worth-value of an island as an int.

#### Example Output

1900000

### superior\_island\_worth\_raw

Get the worth-value of an island in a raw format.

#### Example Output

1900000
