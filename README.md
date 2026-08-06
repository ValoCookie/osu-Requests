# osu!Requests

A Windows Twitch → osu! request manager and stream-side toolkit for **osu!stable** and **osu!lazer**.

> ### Streamer tools by ValoCookie
> osu!Requests handles Twitch map requests, OBS overlays, input visualization and ranked tracking.  
> Looking for repeatable pre-stream preparation too? **[Check out StreamFlight →](https://github.com/ValoCookie/streamflight)**

---

## Latest release

**Version 1.4.2 is currently available.**

[**Open the latest GitHub releases →**](https://github.com/ValoCookie/osu-Requests/releases)

---

## What it does

### Twitch map requests

- watches Twitch chat for osu! beatmap links
- maintains active, pending and historical requests
- supports queue and per-user limits
- supports review mode, duplicate detection and requested mods
- opens requests through Windows Default, osu!stable or osu!lazer
- provides optional filters for PP, stars, length, BPM, AR, CS, OD, status and mode
- includes `!np` for the current or most recently opened requested map

### OBS request overlays

Separate Browser Sources are available for:

- Current Map
- Compact Queue
- Map Requests Open

They can be positioned and styled independently.

### 60 FPS Key Visualizer

The Key Visualizer is a dedicated OBS Browser Source with:

- roughly 60 FPS overlay updates
- background keyboard and mouse capture while the app is minimized
- independent colors for Key 1 and Key 2
- optional independent Mouse 1 and Mouse 2 colors
- a separately customizable trail color
- adjustable trail height, width and duration
- support for common letters, numbers, punctuation, arrows and modifiers
- a cumulative total that resets only when requested

Key Visualizer settings have their own dedicated screen with visible **Save** and **Refresh** controls.

### Ranked Play Tracker

Ranked tracking is available from its own dedicated screen with persistent **Save** and **Refresh** controls.

---

## Setup

1. Install and open osu!Requests.
2. Connect Twitch.
3. Connect the osu! account that should receive requests.
4. Choose osu!stable, osu!lazer or Windows Default.
5. Configure queue rules and optional filters.
6. Add any OBS Browser Sources you want.
7. Open requests.

---

## Privacy

osu!Requests uses Twitch and osu! OAuth for the account connections needed by the app. Sensitive tokens are excluded from diagnostics exports.

---

## Project status

osu!Requests is actively developed. The latest public release is **v1.4.2**.

Feedback, bug reports and strange streamer-specific edge cases are very welcome.

---

## Disclaimer

osu!Requests is an independent project and is not affiliated with or endorsed by ppy Pty Ltd., osu!, Twitch, or Twitch Interactive, Inc.
