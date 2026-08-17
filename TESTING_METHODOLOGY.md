# Testing Methodology

## Baseline-first policy

Every newly added game is tested on the same known-good primary Xenia
Canary installation before any game-specific changes are attempted.

## One-variable troubleshooting

When a problem is found, only one configuration variable is changed at a
time. The original value, tested value, observed result, and final
known-good value are recorded.

## Validation checklist

-   Boot
-   Menus/cutscenes where applicable
-   Graphics
-   Audio
-   Controller
-   Sustained gameplay
-   Save
-   Load
-   Exit and relaunch
-   Progression/mission transitions where relevant

## Preservation policy

The working primary emulator is never replaced merely because a newer
build exists. Alternate builds are tested separately and retained only
if a specific title benefits from them.

## Scope

These results describe this specific hardware/software environment and
should not be interpreted as guarantees for all systems.
