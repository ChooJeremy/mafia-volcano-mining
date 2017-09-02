# KOLMafia Volcano mining

The rules of optimal volcano mining has changed since the previous script. Notably, you no longer want any unsmoothed velvet, they're worthless. You also don't want to spend any turns mining a spot without sparkles. Notably, this means you should not require any potion of detection in most mines.

## Changes

This volcano mining script follows the following ruleset:
* Mine only sparkles in the first 2 rows
* Never mine a spot without sparkles to reach a spot with sparkles
* Do not require potions of detections. After mining a spot, re-parse the mine to see if any new spots with sparkles have appeared.
* If you find gold, find a new mine
* If there are no more visible sparkles, find a new mine
  * If you can't find a new mine (Lowest row has no sparkles), then use a potion of detection, and mine the spot in the lowest row that would reach a sparkle in the 2nd lowest row.
  * If there are no sparkles left in the lowest 2 rows (Should be very rare), abort. (Please verify if the mine parsing is correct)

## Problems

Whenever this script has to use a potion of detection to mine to a sparkle, because there are no sparkles in the lowest row, it mines for the leftmost sparkle, not the sparkle with the largest grouping of sparkle 
(i.e. given the following bottow two rows:)
```
| _ | * | _ | * | * | _ |
| _ | _ | _ | _ | _ | _ |
      ^
      The script will mine here, but this only allows it to reach a single sparkle instead of 2.```

## Logging

This script currently performs a lot of logging, I just developed (and implemented it). It's tested (but not much), be sure to watch it and verify output if you do not wish to use your adventures too inefficiently.

## Contributing / Suggestions

If you have a better idea for how to mine, feel free to submit a pull request / bug report / reddit post / kmail #2196494