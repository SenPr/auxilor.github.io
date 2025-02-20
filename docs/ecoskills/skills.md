---
title: "Skills"
sidebar_position: 4
---

Skills are levelled up by completing certain tasks, and grant effects, stats, and other bonuses
when levelling up.

## The Default Skills

| Skill       | Task                      |
|-------------|---------------------------|
| Mining      | Break blocks to earn XP   |
| Combat      | Kill mobs to earn XP      |
| Enchanting  | Enchant items to earn XP  |
| Farming     | Harvest crops to earn XP  |
| Woodcutting | Cut down trees to earn XP |
| Fishing     | Fish to earn XP           |
| Alchemy     | Brew potions to earn XP   |
| Armory      | Take damage to earn XP    |
| Exploration | Move to earn XP           |


## Default configs

The default configs can be found here:

[GitHub](https://github.com/Auxilor/EcoSkills/blob/master/eco-core/core-plugin/src/main/resources/skills/)

## `_example.yml`

```yaml
# The ID of the skill is the name of the .yml file,
# for example mining.yml has the ID of mining
# You can place skills anywhere in this folder,
# including in subfolders if you want to organize your skill configs
# _example.yml is not loaded.

# The name and description, shown to players.
name: Mining
description: Break blocks to earn XP

# Options for the GUI
gui:
  enabled: true # (Optional) If this skill should be shown in the GUI

  icon: player_head texture:eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvZmIxYzI2OGVmZWM4ZDdkODhhMWNiODhjMmJmYTA5N2ZhNTcwMzc5NDIyOTlmN2QyMDIxNTlmYzkzY2QzMDM2ZCJ9fX0=

  lore:
    - "&fImproves Stats:"
    - "&8» &r%ecoskills_defense_name%"
    - "&8» &r%ecoskills_ferocity_name%"
    - "&f"
    - "&fEffects:"
    - "&8» &r&6Versatile Tools %ecoskills_versatile_tools_numeral%"
    - "   %ecoskills_versatile_tools_description%"
    - "&8» &r&6Spelunking %ecoskills_spelunking_numeral%"
    - "   %ecoskills_spelunking_description%"
    - "&8» &r&6Dynamic Mining %ecoskills_dynamic_mining_numeral%"
    - "   %ecoskills_dynamic_mining_description%"

  position:
    row: 3
    column: 3


# There are two ways to specify level XP requirements:
#  1. A formula to calculate for infinite levels
#  2. A list of XP requirements for each level

# Formula
# xp-formula: (2 ^ %level%) * 25
# max-level: 100 # (Optional) The max level, if not specified, there is no max level

# List
xp-requirements:
  - 50
  - 125
  - 200
  - 300
  - 500
  - 750
  - 1000
  - 1500
  - 2000
  - 3500
  - 5000
  - 7500
  - 10000
  - 15000
  - 20000
  - 30000
  - 50000
  - 75000
  - 100000
  - 200000
  - 300000
  - 400000
  - 500000
  - 600000
  - 700000
  - 800000
  - 900000
  - 1000000
  - 1100000
  - 1200000
  - 1300000
  - 1400000
  - 1500000
  - 1600000
  - 1700000
  - 1800000
  - 1900000
  - 2000000
  - 2100000
  - 2200000
  - 2300000
  - 2400000
  - 2500000
  - 2600000
  - 2750000
  - 2900000
  - 3100000
  - 3400000
  - 3700000
  - 4000000
  - 5000000


# The rewards given on level up
# You specify a reward (either a stat or an effect),
# the number of levels to give it, and optionally
# a start and end level, which are inclusive.

# An example reward config:
# - reward: strength
#   levels: 1
#   start-level: 10
#   end-level: 20

rewards:
  - reward: defense
    levels: 2

  - reward: ferocity
    levels: 1
    start-level: 15

  - reward: versatile_tools
    levels: 1

  - reward: spelunking
    levels: 1
    start-level: 10

  - reward: dynamic_mining
    levels: 1


# Effects to run when an item levels up
# %level% is the level the item leveled up to.
# If you want to restrict this to certain levels, you can use
# require: %level% == 20, or require: %level% < 50, etc.
level-up-effects:
  - id: give_money
    args:
      amount: 1000 * %level%


# Custom placeholders to be used in descriptions,
# Don't add % to the IDs, this is done automatically
# The value takes a %level% placeholder and is a mathematical expression
placeholders:
  money: "%level% * 0.4"
  blocks: "ceil(10 - %level% / 10)"


# The chat messages to send on level up,
# and the lore that will be shown with %rewards% in the GUI

# The number dictates the minimum level for this text to show for
# Adding new levels will override this text on those levels or above
reward-messages:
  1:
    - " &8» &r&f+2 %ecoskills_defense_name%"
    - " &8» &r&6Versatile Tools %ecoskills_versatile_tools_numeral%"
    - "    %ecoskills_versatile_tools_description%"
    - " &8» &r&6Dynamic Mining %ecoskills_dynamic_mining_numeral%"
    - "    %ecoskills_dynamic_mining_description%"
  10:
    - " &8» &r&f+2 %ecoskills_defense_name%"
    - " &8» &r&6Versatile Tools %ecoskills_versatile_tools_numeral%"
    - "    %ecoskills_versatile_tools_description%"
    - " &8» &r&6Spelunking %ecoskills_spelunking_numeral%"
    - "    %ecoskills_spelunking_description%"
    - " &8» &r&6Dynamic Mining %ecoskills_dynamic_mining_numeral%"
    - "    %ecoskills_dynamic_mining_description%"
  15:
    - " &8» &r&f+2 %ecoskills_defense_name%"
    - " &8» &r&f+1 %ecoskills_ferocity_name%"
    - " &8» &r&6Versatile Tools %ecoskills_versatile_tools_numeral%"
    - "    %ecoskills_versatile_tools_description%"
    - " &8» &r&6Spelunking %ecoskills_spelunking_numeral%"
    - "    %ecoskills_spelunking_description%"
    - " &8» &r&6Dynamic Mining %ecoskills_dynamic_mining_numeral%"
    - "    %ecoskills_dynamic_mining_description%"


# An XP Gain method takes a trigger, a multiplier, conditions, and filters.
# The multiplier takes the value produced by the trigger and multiplies it
# by some value to calculate the experience that should be given
xp-gain-methods:
  - trigger: break_block
    multiplier: 0.5
    filters:
      blocks:
        - netherrack

  - trigger: break_block
    multiplier: 1
    filters:
      blocks:
        - stone
        - diorite
        - granite
        - andesite
        - cobblestone


# Conditions that must be met to gain XP. While you can add conditions to xp
# gain methods, if you have many this can be annoying, so this is global.
conditions: [ ]
```
