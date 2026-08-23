# osu!StreamDeck

**A Windows Twitch → osu! request manager and stream-side toolkit for osu!stable and osu!lazer.**

> ### Streamer tools by ValoCookie
> Created and officially published by **ValoCookie**.
> Looking for repeatable pre-stream preparation too? **[Check out StreamFlight →](https://github.com/ValoCookie/streamflight)**

---

## Latest release

<!-- AUTO_VERSION_START -->
**Version 2.1.0 is currently available.**
<!-- AUTO_VERSION_END -->

[**Open the latest GitHub releases →**](https://github.com/ValoCookie/osu-Requests/releases)

---

## What it does

### Twitch map requests

- watches Twitch chat for osu! beatmap links
- queue/review controls, limits, filters and duplicate protection
- natural mod detection including abbreviations and names around the map link
- stable/lazer/Windows Default opening options
- optional PP, stars, length, BPM, AR, CS, OD, status and mode filters
- viewer `!myq`, editable `!skin` and instant-map `!np` backed by the managed local live-data engine

### OBS and stream overlays

- Current Map / queue/request-state Browser Sources
- customizable Key Visualizer with TOTAL, BPM / MAX BPM, trails and component ordering
- PP Counter
- Score Stats
- Now Playing
- Map Timeline
- Profile Stats builder
- Ranked Play tracker
- managed live overlay library/dashboard for compatible tosu counters

The overlay system is designed around configurable components rather than one fixed layout.


### Managed live engine

Current development builds can package a pinned official **tosu** Windows runtime inside the normal single osuStreamDeck executable. osu!StreamDeck starts/reuses that localhost engine automatically for stable/lazer map state and gameplay telemetry. The upstream tosu component remains a separate program licensed under **LGPL-3.0**; ValoCookie does not claim authorship of it.

The build pins **tosu v4.25.1**, verifies the official runtime archive before packaging, and includes the relevant license/source notices. See **[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)** for the exact source tag and license details.

### Patreon supporter linking

- optional Patreon OAuth linking from the in-app Patreon text
- active paid, trial and gifted ValoCookie memberships can be verified automatically
- supporter identity does not depend on Patreon and osu! usernames matching
- Patreon/client secrets remain server-side in the Cloudflare relay
- technical verification details stay out of normal user-facing pages and remain available through sanitized diagnostics

### Updates

The app can check for updates while running and show a small non-focus-stealing notification with the ValoCookie update chime. Official release binaries are distributed through this repository.

---

## Setup

1. Install and open osu!StreamDeck.
2. Connect Twitch.
3. Connect the osu! account that should receive requests.
4. Choose osu!stable, osu!lazer or Windows Default.
5. Configure queue rules and optional filters.
6. Add any OBS Browser Sources you want.
7. Open requests.

---

## Privacy

osu!StreamDeck uses Twitch and osu! OAuth for the account connections needed by the app. Patreon linking is optional and is used only to verify ValoCookie supporter status. Sensitive tokens and server-side secrets are excluded from diagnostics exports.

---

## Project status

<!-- AUTO_STATUS_START -->
The latest public release is **v2.1.0**.
<!-- AUTO_STATUS_END -->

Feedback and bug reports are welcome.

---

## Ownership / disclaimer

Copyright © 2026 ValoCookie.

**Original Creator and Official Publisher: ValoCookie.**

osu! and related marks belong to ppy Pty Ltd. osu!StreamDeck is an independent community project and is not affiliated with or endorsed by ppy.

## Bug reports

Use the **BUG REPORT** button inside osu!StreamDeck or open a GitHub Issue using the included bug report template. Never post Twitch/relay tokens or passwords.
