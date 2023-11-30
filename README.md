## Dungeon Balance

This module is intended to scale based on number of players, instance mobs and bosses' health, mana, and damage. All settings are well-described in the configuration file.

**NOTE 1:** This module requires at least [this commit](https://github.com/azerothcore/azerothcore-wotlk/commit/f127e583aae3cfa51a77d056c1892a7de07ffb52) of AzerothCore in order to work correctly. Older versions are not supported.
**NOTE 2:** This is customized from the source mode called "AutoBalance" found here: https://github.com/azerothcore/mod-autobalance

## In-game Commands
| Command | Permission | Description |
| :------ | :--------- | :---------- |
| `.dungeonbalance setplayers` | All Players | Sets a fixed player count difficulty for the player's current dungeon instance, which doesn't change even if players join or leave. |
| `.dungeonbalance getmapstat` | All Players | Displays AB-calcualted settings for the current map, including player count, difficulty, world modifiers, and others. |
| `.dungeonbalance getcreaturestat` | All Players | Displays AB-calculated settings for the targeted dungeon creature including level scaling, difficulty, modifiers, and boss status. |

## Logger Names
| Logger | Description |
| :----- | ----------- |
| `Logger.module.AutoBalance` | Main logger, verbose debug logs. Map detection, list management, creature adjustments, multiplier, modifiers. Catch-all. |
| `Logger.module.AutoBalance_CombatLocking` | Debug logs related to the combat locking/unlocking mechanism for maps. |
| `Logger.module.AutoBalance_DamageHealingCC` | Debug logs for the spell/melee/CC modifications that are made in real-time. |
| `Logger.module.AutoBalance_StatGeneration` | Detailed debug logs that show all the calculation steps in how different multipliers are derived. |

## References
- [Interactive Inflection Point Spreadsheet](https://docs.google.com/spreadsheets/d/100cmKIJIjCZ-ncWd0K9ykO8KUgwFTcwg4h2nfE_UeCc/copy)
- [InflectionPoint Curve Examples](https://i.imgur.com/x42UnUR.png)
- [Impact of CurveFloor and CurveCeiling on enemy multiplier](https://i.imgur.com/I8S4cwJ.png)
