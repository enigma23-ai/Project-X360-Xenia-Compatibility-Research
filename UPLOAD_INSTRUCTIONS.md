# WHERE TO POST

## Primary destination --- official Xenia Canary compatibility tracker

https://github.com/xenia-canary/game-compatibility/issues

For each game: 1. Sign in to GitHub. 2. Open the Issues page above. 3.
Search the **Title ID** (for example `425307D2`). 4. If an issue already
exists, post the matching draft as a new comment/update there. 5. If no
issue exists and the repository allows you to create one, use the
repository's current issue template/conventions and paste the matching
draft. 6. Add the exact Xenia build/commit and attach a fresh
`xenia.log` from that game/test.

### Highest-priority reports

1.  `425307D2` --- Star Trek: Legacy Mission 1 progression crash
2.  `5454089E` --- MLB 2K12 date-dependent startup freeze

These contain reproducible failures/workarounds and are the most
valuable developer-facing findings.

## Optional --- your own public research repository

Create a normal public GitHub repository named something like:

`Project-X360-Xenia-Compatibility-Research`

Upload the contents of this package to it. This provides a searchable
long-form archive. In official compatibility comments, you may link back
to the relevant report in your repository as supplemental detail.

## Do NOT upload

-   Xbox 360 game files
-   GOD containers
-   XEX files
-   title updates copied from games
-   encryption keys
-   copyrighted game assets
-   personal paths/logs containing information you do not want public

## Game patches repository

https://github.com/xenia-canary/game-patches

Do not submit these compatibility reports there unless you actually
develop a patch. That repository is for patches, not general
compatibility observations.
