# 5454089E - MLB 2K12 --- date-dependent startup freeze; playable with 2012-09-30 host date

## Summary

MLB 2K12 is playable in the tested Xenia Canary environment, but startup
freezes when the host Windows date is the current 2026 date. Temporarily
setting Windows to **2012-09-30** before launch allows the title to
proceed and run normally.

## Reproduction

1.  Launch MLB 2K12 with Windows using the current date.
2.  Proceed through the initial startup/title flow.
3.  The game freezes before normal gameplay.
4.  Close Xenia.
5.  Temporarily set Windows date to `2012-09-30`.
6.  Relaunch the same game with the same Xenia configuration.
7.  The title proceeds normally and gameplay is available.

## Tested in-game changes

-   Autosave = Off
-   Living Rosters = Off

Neither setting eliminated the startup freeze when Windows remained on
the current date.

## Working result after date workaround

-   Boot: PASS
-   Graphics: PASS
-   Audio: PASS
-   Controller: PASS
-   Gameplay: PASS
-   Save/Load: PASS

## Current workaround

A local batch launcher temporarily sets the Windows date to 2012-09-30,
launches MLB 2K12, waits for Xenia to close, then requests Windows time
synchronization. Manual date change also works.

## Request / value to developers

This appears worth investigating as a date/time or calendar behavior
difference visible to the guest. A future emulator-level fix that
removes dependence on the host date would eliminate the workaround.

## Test environment

-   Windows 11 Pro
-   AMD Ryzen 7 7800X3D
-   NVIDIA GeForce RTX 5070
-   32 GB DDR5-6000 CL30
-   Xenia Canary
-   Title ID: `5454089E`

**Before posting:** add exact Xenia commit/build and attach a fresh
`xenia.log`.
