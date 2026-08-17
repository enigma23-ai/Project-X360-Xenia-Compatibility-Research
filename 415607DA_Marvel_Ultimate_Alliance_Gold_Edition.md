# 415607DA --- Marvel Ultimate Alliance Gold Edition

**Observed status:** PASS

## Environment

See `TEST_ENVIRONMENT.md` and `TESTING_METHODOLOGY.md`.

## Findings

Boot/gameplay/cutscenes/audio/controller/save/load all pass. Dummy
HDD/storage selection resolved 'No storage device selected'.
`protect_zero = false` resolved post-intro loading freeze.
`xma_decoder = "old"` fixed choppy/static audio and crash behavior.

## Community submission note

Search the Xenia Canary compatibility tracker for Title ID `415607DA`
first. Add this result to an existing issue when one exists; avoid
duplicate issues.

## Evidence to add before/with official submission

-   Exact Xenia Canary commit/build identifier
-   Fresh `xenia.log` from the reproduced run
-   Screenshot/video only if it clearly demonstrates the issue and
    contains no copyrighted game data beyond ordinary gameplay capture
