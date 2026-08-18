# 425307D2 - Star Trek: Legacy --- crash/hang after Campaign Mission 1

## Summary

Star Trek: Legacy boots and plays correctly through Campaign Mission 1
in the tested Xenia Canary environment. At the end of Mission 1, the
game crashes/hangs during the campaign progression/save transition.

## Reproduction

1.  Launch Star Trek: Legacy.
2.  Start a new Campaign.
3.  Play Mission 1 to completion.
4.  Observe the transition immediately after Mission 1.
5.  The title crashes/hangs instead of progressing normally.

## Working behavior before failure

-   Boot: PASS
-   Menus: PASS
-   Graphics: PASS
-   Audio: PASS
-   Controller: PASS
-   Mission 1 gameplay: PASS

## Failure

-   End-of-Mission-1 campaign progression/save transition: FAIL
-   Campaign continuation: blocked

## Troubleshooting performed

-   Current known-good Project X-360 baseline retained.
-   `mount_cache = true` was already enabled; therefore enabling cache
    mounting alone did not resolve the failure.
-   A separate copied game installation was used for a Velocity/package
    extraction experiment.
-   Velocity rejected the selected container as an STFS package
    (`STFS: Invalid file system header`), and no usable extracted
    `default.xex` test was produced.
-   Original game data and primary Xenia environment were left
    untouched.

 ## Workarounds Investigated

### portable.txt

The use of `portable.txt` was investigated as a possible workaround for the Mission 1 progression/save-transition crash.

Current Xenia Canary documentation indicates that Canary already operates with portable-style local content storage by default. Creating `portable.txt` therefore does not provide an additional behavior change for current Canary builds.

**Result:** Ruled out as a useful workaround for the current Project X-360 test environment.

The Mission 1 crash remains reproducible and unresolved.

## Request / value to developers

The failure is highly reproducible at a specific campaign transition.
Future Xenia/Canary changes affecting save/content/kernel behavior may
be relevant.

## Test environment

-   Windows 11 Pro
-   AMD Ryzen 7 7800X3D
-   NVIDIA GeForce RTX 5070
-   32 GB DDR5-6000 CL30
-   Xenia Canary
-   Title ID: `425307D2`

**Before posting:** add exact Xenia commit/build and attach a fresh
`xenia.log` captured through the Mission 1 failure.
