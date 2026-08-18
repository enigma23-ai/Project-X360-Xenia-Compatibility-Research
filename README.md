# Project X-360 — Xenia Compatibility Research

Community compatibility testing, configuration research, workarounds, and reproducible findings for Xbox 360 games tested with Xenia Canary.

This project was created to document real-world Xbox 360 emulation results and contribute useful compatibility information back to the Xenia community.

## Game Compatibility Index

| Title ID | Game | Status | Key Finding |
|---|---|---|---|
| [`415607DA`](415607DA_Marvel_Ultimate_Alliance_Gold_Edition.md) | Marvel Ultimate Alliance Gold Edition | ✅ Playable | Dummy HDD/storage configuration and XMA audio settings documented |
| [`4156082F`](4156082F_Marvel_Ultimate_Alliance_2.md) | Marvel Ultimate Alliance 2 | ✅ Playable | Boot, gameplay, graphics, controller, save/load and relaunch passed |
| [`425307D2`](425307D2_Star_Trek_Legacy.md) | Star Trek: Legacy | ⚠️ Pending | Mission 1 plays correctly; campaign progression/save transition crashes afterward |
| [`45410822`](45410822_Need_for_Speed_ProStreet.md) | Need for Speed: ProStreet | ✅ Playable | Boot, gameplay, graphics, controller and save/load passed |
| [`45410998`](45410998_FIFA_Soccer_13.md) | FIFA Soccer 13 | ✅ Playable | Clean gameplay, graphics and save/load under current baseline |
| [`454109C1`](454109C1_Madden_NFL_25.md) | Madden NFL 25 | ✅ Playable | `readback_resolve = "full"` corrected field/grass rendering |
| [`54540894`](54540894_NBA_2K12.md) | NBA 2K12 | ✅ Playable | Passed under current Project X-360 baseline |
| [`5454089E`](5454089E_MLB_2K12.md) | MLB 2K12 | ⚠️ Playable with workaround | Current-date startup freeze; temporary `2012-09-30` Windows date workaround |

### Priority Research

Two titles currently have dedicated compatibility investigations:

- **Star Trek: Legacy — `425307D2`**  
  Reproducible campaign progression/save-transition failure after Mission 1.  
  See [`PRIORITY_425307D2_Star_Trek_Legacy_Mission1_Crash.md`](PRIORITY_425307D2_Star_Trek_Legacy_Mission1_Crash.md)

- **MLB 2K12 — `5454089E`**  
  Reproducible system-date dependency affecting startup.  
  See [`PRIORITY_5454089E_MLB_2K12_Date_Dependency.md`](PRIORITY_5454089E_MLB_2K12_Date_Dependency.md)

## Purpose

Project X-360 focuses on:

- Testing personally owned Xbox 360 retail discs in Xenia Canary
- Verifying Title IDs and game behavior
- Documenting working configurations
- Recording reproducible bugs and workarounds
- Preserving known-good emulator settings
- Sharing results that may help users and developers improve future compatibility

No copyrighted game files, XEX files, GOD containers, encryption keys, or proprietary Xbox assets are included in this repository.

## Test Environment

**System:** Aurora  
**Operating System:** Windows 11 Pro  
**CPU:** AMD Ryzen 7 7800X3D  
**GPU:** NVIDIA GeForce RTX 5070  
**RAM:** 32 GB DDR5-6000 CL30  
**Emulator:** Xenia Canary

Current known-good baseline includes:

- `hid = "any"`
- `storage_selection_dialog = true`
- `protect_zero = false`
- `use_dedicated_xma_thread = true`
- `xma_decoder = "old"`
- `readback_resolve = "full"`

`mount_cache = true` was also confirmed during Star Trek: Legacy troubleshooting.

## Testing Methodology

Each game is tested using the same baseline first.

When troubleshooting:

1. Change only one variable at a time.
2. Record the original setting.
3. Record the tested setting.
4. Observe the result.
5. Preserve the known-good primary Xenia installation.
6. Use alternate Xenia builds only if a specific game requires one.

Testing includes:

- Boot
- Menus and cutscenes
- Graphics
- Audio
- Controller input
- Sustained gameplay
- Save/load
- Exit/relaunch
- Mission or campaign progression where applicable

See:

- `TESTING_METHODOLOGY.md`
- `TEST_ENVIRONMENT.md`

## Compatibility Results

| Game | Title ID | Result | Notes |
|---|---|---|---|
| Marvel Ultimate Alliance Gold Edition | `415607DA` | PASS | Dummy HDD/storage selection required; `xma_decoder = "old"` fixed audio/static/crash behavior |
| Marvel Ultimate Alliance 2 | `4156082F` | PASS | Passed under current baseline |
| Need for Speed: ProStreet | `45410822` | PASS | Initial controller issue traced to Windows detection, not Xenia |
| Madden NFL 25 | `454109C1` | PASS | `readback_resolve = "full"` fixed corrupted/non-green field textures |
| NBA 2K12 | `54540894` | PASS | Passed under current baseline |
| MLB 2K12 | `5454089E` | PASS WITH WORKAROUND | Requires temporary Windows date change to 2012-09-30 for successful startup |
| FIFA Soccer 13 | `45410998` | PASS | Clean boot, graphics, gameplay, save/load under current baseline |
| Star Trek: Legacy | `425307D2` | PENDING / GAMEPLAY | Mission 1 plays correctly; crash/hang occurs at end-of-mission campaign progression/save transition |

## Highest-Priority Compatibility Findings

### Star Trek: Legacy — `425307D2`

Star Trek: Legacy boots and plays correctly through Campaign Mission 1.

Observed behavior:

- Boot: PASS
- Graphics: PASS
- Audio: PASS
- Controller: PASS
- Mission 1 gameplay: PASS
- End-of-Mission-1 campaign transition: FAIL

The title crashes or hangs during campaign progression/save transition after Mission 1.

`mount_cache = true` was already enabled, so cache mounting alone did not resolve the problem.

See:

`PRIORITY_425307D2_Star_Trek_Legacy_Mission1_Crash.md`

### MLB 2K12 — `5454089E`

MLB 2K12 freezes during startup when Windows uses the current system date.

Temporarily changing Windows to:

`2012-09-30`

allows the game to boot and run normally.

After the date workaround:

- Graphics: PASS
- Audio: PASS
- Controller: PASS
- Gameplay: PASS
- Save/load: PASS

Turning off Autosave and Living Rosters did not eliminate the startup freeze.

A local batch launcher was created to automate the temporary date change and restore Windows time synchronization after Xenia closes.

See:

`PRIORITY_5454089E_MLB_2K12_Date_Dependency.md`

## Research Files

This repository includes:

- Individual compatibility reports for each tested game
- Priority issue reports for unresolved behavior
- Test methodology
- Test environment documentation
- Project X-360 Emulator Map
- Xenia baseline configuration workbook

## Contribution Goal

The goal is to make these findings searchable and useful to:

- Xenia developers
- Xenia Canary contributors
- Emulator users
- Compatibility researchers
- Future community members investigating the same titles

If future Xenia builds resolve the Star Trek: Legacy campaign issue or MLB 2K12 date dependency, this repository will be updated with new findings.

## Disclaimer

Results reflect this specific hardware, software, emulator build, and configuration environment.

Compatibility may vary across systems and future Xenia versions.
