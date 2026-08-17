# 454109C1 --- Madden NFL 25

**Observed status:** PASS

## Environment

See `TEST_ENVIRONMENT.md` and `TESTING_METHODOLOGY.md`.

## Findings

Boot/cutscenes/audio/controller/gameplay/save/load pass.
`readback_resolve = "none"` caused corrupted/non-green field textures;
`readback_resolve = "full"` corrected the field/grass rendering.

## Community submission note

Search the Xenia Canary compatibility tracker for Title ID `454109C1`
first. Add this result to an existing issue when one exists; avoid
duplicate issues.

## Evidence to add before/with official submission

-   Exact Xenia Canary commit/build identifier
-   Fresh `xenia.log` from the reproduced run
-   Screenshot/video only if it clearly demonstrates the issue and
    contains no copyrighted game data beyond ordinary gameplay capture
