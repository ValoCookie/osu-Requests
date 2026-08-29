# osu!StreamDeck

this started as a Twitch beatmap request manager and then i kept adding shit to it.

now it handles requests, OBS overlays, the key visualizer, skin commands, Ranked Play stuff and support for both osu!stable and osu!lazer.

if you want the pre-stream app too: [StreamFlight](https://github.com/ValoCookie/streamflight)

## latest release

<!-- AUTO_VERSION_START -->
**Version 2.1.9 is currently available.**
<!-- AUTO_VERSION_END -->

[download / releases](https://github.com/ValoCookie/osu-Requests/releases)

## what it does

### requests

- watches Twitch chat for osu! beatmap links
- queue and review controls
- limits, filters and duplicate protection
- detects mods written around the map link
- opens maps in stable, lazer or Windows Default
- optional filters for PP, stars, length, BPM, AR, CS, OD, status and mode
- `!myq`, `!skin` and fast `!np`

### OBS / stream stuff

- current map overlay
- queue / request status overlays
- customizable 60 FPS key visualizer
- TOTAL, live BPM and MAX BPM
- trails and different component layouts
- PP counter
- score stats
- now playing
- map timeline
- profile stats
- Ranked Play tracker
- compatible tosu overlays

basically i wanted the stream-side osu! stuff i actually use in one place instead of having a pile of separate tools open (and RonniaBot was down so ye)

### live data / tosu

osu!StreamDeck can use a packaged official tosu runtime for live map and gameplay data.

the tosu part is still its own project and is licensed under LGPL-3.0. i dont claim any of that code as mine.

the build currently pins **tosu v4.25.1**. the exact source/license info is in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

### updates

the app checks for updates in the background and lets you know when a new build is out.

## setup

1. install and open osu!StreamDeck
2. connect Twitch
3. connect the osu! account that should receive requests
4. choose stable, lazer or Windows Default
5. set up whatever queue rules / filters you want
6. add any OBS browser sources you want
7. open requests

## privacy

osu!StreamDeck uses Twitch and osu! OAuth for the account connections the app needs.

Patreon linking is optional and only used for supporter verification. sensitive tokens and server-side secrets are left out of diagnostic exports.

## project status

<!-- AUTO_STATUS_START -->
The latest public release is **v2.1.9**.
<!-- AUTO_STATUS_END -->

still being worked on. bug reports and feedback are very welcome.

## bug reports

use the **BUG REPORT** button inside osu!StreamDeck or open a GitHub Issue.

please dont post Twitch tokens, relay tokens or passwords in the report. i do not need those to debug your issue.

## disclaimer

osu! and related marks belong to ppy Pty Ltd.

osu!StreamDeck is my own independent project and is not affiliated with or endorsed by ppy.

© 2026 ValoCookie
