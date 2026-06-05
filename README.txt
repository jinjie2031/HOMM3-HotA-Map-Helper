# HOMM3 HotA 1.8 Map Helper V1.2.1

This is a local Windows utility for monitoring the Heroes of Might and Magic III HotA 1.8 random map folder, reading the latest `.h3m` / `.h3c` map file, configuring automatic map filtering rules, and running a mouse macro for:

System Options -> Restart -> Generate New.

## Launch

Run:

```text
HOMM3_HotA_Map_Helper_V1.2.1.exe
```

## Main Features

- Scans `.h3m` / `.h3c` files.
- Default random map folder:

```text
D:\Games\Heroes3\HotA\random_maps
```

- Reads random map title, size, underground layer status, template, seed, and RMG description.
- Automatically refreshes the latest random map.
- Supports all 12 HotA 1.8 towns.
- Supports per-level dwelling conditions with quantities: 1 / 2 / 3 / 4 / 5+.
- Factory supports 7A / 7B dwelling rules.
- Factory level 1 supports Hovel / Halfling Adobe.
- Castle level 6 can optionally require Stables nearby.

## Current Game Map Scan

- Full current map scan:
  - Reads the latest random map from `random_maps`.
  - Counts towns, heroes, dwellings, resources, treasures, banks, and common neutral buildings.
- Player main-town area scan:
  - Reads the latest random map from `random_maps`.
  - Detects the player's controlled main town by player color.
  - Counts only objects in the player's main-town area.
  - Underground starts are counted by the configured underground range rule.

## Auto Filter

- Click Start Auto Filter to evaluate the latest generated random map.
- The tool checks the selected dwelling level and quantity conditions inside the player's main-town area.
- If the map does not meet the conditions, the recorded macro is executed and the tool waits for the next random map.
- A completed scan and evaluation counts as one attempt.
- The tool waits for a new map file and rechecks the file signature before scanning.
- When a matching map is found, the success dialog shows:
  - The selected conditions.
  - The actual quantity found for selected levels.
  - Any same-town wild dwellings with quantity greater than 0.

## Macro

- Records click coordinates for:
  - System Options
  - Restart
  - Generate New
- Supports starting and stopping the auto-filter flow.
- Auto-filter logs are written to:

```text
auto_roll_log.txt
```

## Configuration Files

```text
homm3_map_selector_config.json
homm3_map_selector_user_data.json
```

## V1.2.1 Changes

- Auto-filter attempts are counted after a new map scan and evaluation completes.
- The latest map file signature is rechecked before scanning.
- Success dialog title remains "Matching Map Found".
- Success dialog content starts with "Congratulations: a matching map has been found."
- Success dialog lists selected conditions and found dwelling quantities with quantity first.
- Auto-filter logging was added for troubleshooting stop reasons and map generation flow.
