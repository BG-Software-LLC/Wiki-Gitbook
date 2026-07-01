---
description: >-
  Using upgrades, you can give your players custom perks that are upgradable. In
  this documentation, you will understand how to edit them to your own style!
---

# Upgrades

## Creating your first upgrade

Creating a new upgrade is an easy task to do!\
All the upgrades follow the same rules, but in this tutorial we will create a generator upgrade.

We will start with the basic layout for the upgrade:

```yaml
upgrades:
  island-generators:        # The name of the upgrade.
    '1':                    # The first level of the upgrade.
      <to-do>
    '2':                    # The second level of the upgrade.
      <to-do>
```

All the upgrades work with the same layout: a global section for the upgrade, and sub-sections for every level of the upgrade. You can make as many levels as you want!

Now, we can start working on our first level. We will give it a price-type, price, commands to be executed upon rankup and a required permission to use the upgrade. In this case, I don't want a permission - so I don't add that section.

```yaml
'1':
  price-type: 'money'      # The type of price handler. More information below.
  price: 100000.0          # The price to rank up to the second level.
  commands:
    - 'island admin setupgrade %player% island-generators 2'     # We must change the level of the upgrade manually using a command.
    - 'island admin msgall %player% &e&lUpgrade | &7%player% upgraded your generators to level 2!'   # Message that will be sent to the island members.
  permission:  <your-permission>   # You can add it if you want a required permission to rankup.
```

As you might have noticed, I run /is admin setupgrade - this is required so the plugin will actually change the upgrade's level for the island. Not doing so will make the upgrade to not rankup, as you'll see in the last level.

After we set up the basic layout of the level, we want to give it some values. The values will be synced with the island. You can change crop growth, spawner rates, mob drops, limits, generators and more with the upgrades! For this tutorial, I will change the generator rates using the "generator-rates" section:

```yaml
'1':
 price-type: 'money'
 price: 100000.0
 commands:
   - 'island admin setupgrade %player% island-generators 2'
   - 'island admin msgall %player% &e&lUpgrade | &7%player% upgraded your generators to level 2!'
 generator-rates:
   normal:      # The world environment. Can use normal, nether or the_end.
     STONE: 85
     COAL_ORE: 10
     IRON_ORE: 5 
```

That's it! We completed our first level! Because this is the first level of the upgrade, it will be applied to all the islands by default. It means that all of the islands on my server will have the generator rates that I configured. Now, I will add more levels by following the same layout:

```yaml
upgrades:
 island-generators:
   '1':
     price-type: 'money'
     price: 100000.0
     commands:
       - 'island admin setupgrade %player% island-generators 2'
       - 'island admin msgall %player% &e&lUpgrade | &7%player% upgraded your generators to level 2!'
     generator-rates:
       normal:
         STONE: 85
         COAL_ORE: 10
         IRON_ORE: 5 
   '2':
     price-type: 'money'
     price: 150000.0
     commands:
       - 'island admin setupgrade %player% island-generators 3'
       - 'island admin msgall %player% &e&lUpgrade | &7%player% upgraded your generators to level 3!'
     generator-rates:
       normal:
         STONE: 70
         COAL_ORE: 15
         IRON_ORE: 10
         DIAMOND_ORE: 5
   '3':
     price-type: 'money'
     price: 300000.0
     commands:
       - 'island admin setupgrade %player% island-generators 4'
       - 'island admin msgall %player% &e&lUpgrade | &7%player% upgraded your generators to level 4!'
     generator-rates:
       normal:
         STONE: 50
         COAL_ORE: 25
         IRON_ORE: 15
         DIAMOND_ORE: 10
```

After I configured all of my levels, I must also add the last upgrade - level #4. Unlike the other upgrades, this upgrade will not have the setupgrade command, but will still have values assigned to it:

```yaml
'4':
  price-type: 'money'
  price: 0.0       # I set the price to 0, so my players will always get the warning message.
  commands:
    - 'island admin msg %player% &c&lError | &7You have reached the maximum upgrade for island generators.'
  generator-rates:
    normal:
      EMERALD_ORE: 50
      DIAMOND_ORE: 50
```

Finally, I have a working generator upgrade that will have it's values synced with all the islands. You can change the values anytime you want, and your islands will be synced automatically with it. Removing existing levels is not an option - you can just make the upgrade to do nothing, but removing it completely will cause errors from the plugin.

You can use the following sections to alter island values: \
`crops-growth`: The crop growth multiplier for this upgrade. \
`spawner-rates`: The spawner rates multiplier for this upgrade. \
`mob-drops`: The mob drops multiplier for this upgrade. \
`team-limit`: The team limit for this upgrade. \
`warps-limit`: The warps limit for this upgrade. \
`coop-limit`: The coops limit for this upgrade. \
`border-size`: The border size for this upgrade. \
`block-limits`: The block limits for this upgrade. \
&#xNAN;_&#x55;nder this section, all the blocks will be in the following format: "TYPE: LIMIT"._ \
`entity-limits`: The entity limits for this upgrade. \
&#xNAN;_&#x55;nder this section, all the entities will be in the following format: "TYPE: LIMIT"._ \
`generator-rates`: The generator rates for this upgrade. \
&#xNAN;_&#x55;nder this section, all the rates will be in the following format: "TYPE: CHANCE"._\
&#x20;`island-effects`: The island effects for this upgrade. \
&#xNAN;_&#x55;nder this section, all the effects will be in the following format: "EFFECT: LEVEL"._\
`role-limits`: The role limits for this upgrade. \
&#xNAN;_&#x55;nder this section, all the roles will be in the following format: "ROLE: LIMIT"._&#x20;

## Price Types

The plugin has two pre-defined price types - money based prices and placeholders based prices.\
Simply add the `price-type` section to your upgrade with the price-type you want. Currently there are two different ones: `money` and `placeholders:`

#### money

When using this price-type, money will be taken from the players' bank (Essentials or any other economy plugin).

You must add the following fields to your upgrade to get this working:

| Required Field | Type   | Description                        |
| -------------- | ------ | ---------------------------------- |
| `price`        | Double | The cost to upgrade to next level. |

#### placeholders

When using this price-type, money will be taken by executing custom commands, and the balance will be parsed by a placeholder.

You must add the following fields to your upgrade to get this working:

| Required Field      | Type   | Description                                                                                                                                        |
| ------------------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `price`             | Double | The cost to upgrade to next level.                                                                                                                 |
| `placeholder`       | String | The placeholder that represents the balance of the player.                                                                                         |
| `withdraw-commands` | List   | <p>A list of commands to be executed for withdrawing money.<br>You can use %player% for player's name and %amount% for the amount to withdraw.</p> |

{% hint style="info" %}
You can register custom price types using the API.
{% endhint %}

### Example

In the example below, you can find two upgrades (each has only one level) with different price types.&#x20;

The first upgrade, `money-example-upgrade`, has a `money` price-type configured to it. The second one, `placeholders-example-upgrade`, has a `placeholders` price-type. \
For this example, assume the placeholder `%custom_economy_balace%` returns an integer with the balance of the player and the command `/customeco take <player-name> <price>` takes the given balance from the given player.

```yaml
upgrades:
  money-example-upgrade:
    '1':
      price: 1000000.0
      price-type: 'money'
      commands:
        - ...
  placeholders-example-upgrade:
    '1':
      price: 1000000.0
      price-type: 'placeholders'
      placeholder: '%custom_economy_balance%'
      withdraw-commands:
      - 'customeco take %player% 1000000'
      commands:
        - ...
```
