---
description: >-
  You can add different chests to the plugin by adding them to the config file.
  In this tutorial you'll see how it's done, what fields can be added and which
  chests are available.
---

# Configuring Chests

First thing to do is to give your chest a unique name. This name will later be used to give the chests to players with the give command. The name must be unique to your chest, and two chests cannot share the same name. After choosing one, add it to your config under the chests section:

```yaml
chests:
  <chest-name>:
    ...
```

Second step is to choose the type of chest you want to create. There are plenty of different chests you can create, and each of them have a different action it can do:

#### LINKED\_CHEST

The linked-chest mode used to link chests to other chests. All the linked chests will share the same inventory, and it can be opened by different chest blocks accross the world.\
Read more about it [here](linked-chests.md).

#### CHEST

The chest mode used to make the chest functional as a vanilla chest. It can later be expanded to do different tasks, such as selling its contents, craft them or have different pages for the chest.\
Read more about it [here](regular-chests.md).

#### STORAGE\_UNIT

The storage-unit mode makes the chest to be able to hold infinite amount of an item inside it. It has only one slot available, and it can hold only one item at a time without a limit to it.\
Read more about it [here](storage-units.md).

Once you chose your chest, you can add it to the config under the `chest-mode` section:

```yaml
chests:
  <chest-name>:
    chest-mode: <chest>
```

## Chest Sections

In order to properly have your chests registered, you must add the required sections for each chest (These can be found on each chest's page), alongside of a name and a lore to the chest's item. The `item.name` and `item.lore` sections are used for this purpose:

```yaml
chests:
  <chest-name>:
    chest-mode: <chest>
    item:
      name: 'Example Name'
      lore:
      - 'Example Lore'
```

{% hint style="warning" %}
You must configure a name or a lore for each chest, otherwise they will not get registered.
{% endhint %}

Each chest can have optional sections besides the required ones, which can change the behavior of your chests. Here is the list of sections you can use:

### size

Set the amount of rows the chest will have.

#### Section Type

Integer (Number between 1 and 6)

### title

Give a custom title to the chest's inventory title.

#### Section Type

String

### multiplier

Set a sell multiplier for the chest.

#### Section Type

Double (Decimal Number)

### auto-collect

When set, instead of dropping the item on ground, it will be collected straight to the player's inventory.

#### Section Type

Boolean (true/false)

### particles

List of particles to around the chest on ground.

#### Section Type

List

{% hint style="info" %}
You can find a list of particles [on this website](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Particle.html).
{% endhint %}
