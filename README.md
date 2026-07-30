# osu!Requests

A Windows app for handling **osu! map requests from Twitch chat** without spending half the stream copying links around.

> ### 🎥 Streamer tools by ValoCookie
> **osu!Requests** handles Twitch → osu! map requests.  
> Looking for a pre-stream checklist and health-check workspace too? **[Check out StreamFlight →](https://github.com/ValoCookie/streamflight)**

---

## Current build

**Current GitHub build: v1.2.5**

osu!Requests supports both **osu!stable** and **osu!lazer**.

[**Open the latest GitHub releases →**](https://github.com/ValoCookie/osu-Requests/releases)

---

## Why I made it

I originally started this because a friend wanted something for her stream after ronniabot was not working properly in lazer.

It slowly turned into a proper desktop app.

The basic idea is still simple: viewers paste an osu! beatmap link in Twitch chat, osu!Requests picks it up, checks the request rules, grabs the map information and requested mods, adds it to the queue, and sends accepted requests to the connected osu! account.

---

# What it does

## Twitch map requests

osu!Requests watches Twitch chat for osu! beatmap links and builds a request queue automatically.

You can:

- open or close map requests
- set an overall queue limit
- set a per-user queue limit
- review requests before they enter the active queue
- accept, reject and reorder pending requests
- reorder or remove maps already in the active queue
- move to the next request manually
- open the current request directly in osu!
- keep opened requests in History
- reopen older maps without changing the active queue
- detect duplicate requests during the session

---

## osu!stable + osu!lazer

Requested maps can be opened through:

- **Windows Default**
- **osu!stable**
- **osu!lazer**

Choose the preferred client in **Preferences**.

When a queued request is opened, osu!Requests can advance that map out of the active queue while keeping it safely stored in History.

---

## Map information

For supported requests, osu!Requests can display information including:

- artist and title
- mapper
- exact difficulty
- star rating
- BPM
- map length
- AR
- CS
- OD
- HP
- max combo
- object count
- ranking status
- requested mods
- estimated PP where available

Specific difficulty links are preserved whenever possible instead of being reduced to only the beatmapset.

---

## Request filters

Most request filters are optional.

Leave a Min/Max field blank when you do not want that value restricted.

Available filters include:

- star rating
- map length
- BPM
- AR
- CS
- OD
- PP
- ranking status
- osu! game mode

### PP filtering

**MIN PP / MAX PP** uses the estimated maximum PP for a **100% FC on the exact requested difficulty**, including requested mods.

For example, a `+HDDT` request is evaluated with HDDT rather than as nomod.

---

## Requested mods

Viewers can include mods with their request.

Examples:

```text
+HD
+DT
HDDT
DTHD
HD DT
dt hd
```

The parser is intentionally forgiving about capitalization and common combination formats.

Requested mods remain attached to the map and are included when the request is delivered through osu! chat.

---

## Twitch controls

osu!Requests includes:

- request confirmation messages
- closed-queue feedback
- full-queue feedback
- duplicate-request messages
- customizable queue command aliases
- configurable queue reminders
- viewer-specific queue limits
- Subscriber / VIP / Moderator request filters
- excluded-user filtering
- optional Channel Points request mode

The broadcaster remains exempt from normal viewer restrictions.

---

## `!np`

Viewers can use:

```text
!np
```

to see the most recently opened/current requested map known to osu!Requests.

The response can include the map, difficulty, star rating, requested mods, link and requester.

`!np` tracks maps handled through the osu!Requests request/open flow; it is not intended as a universal detector for every map manually played outside the request system.

---

# OBS browser overlays

osu!Requests hosts three separate local Browser Source overlays:

- **Current Map**
- **Compact Queue**
- **Map Requests Open**

You can add one, two or all three to OBS at the same time.

Overlay options include:

- background color
- text color
- accent color
- open-status color
- background opacity
- streamer label
- show/hide streamer name
- custom sizing
- left/right snapping
- X/Y positioning
- queue growth from top → bottom or bottom → top

The Current Map overlay uses the same positioning controls, so it is not locked to one place inside the Browser Source.

---

# Review mode

Enable:

> **Review requests before adding them to the active queue**

when you want incoming requests to wait in Pending.

From there, you can accept, reject or reorder them before they enter the live queue.

Leave it off when you want accepted requests to go directly into the queue.

---

# History and queue management

History keeps requests received during the current session, including maps that have already left the active queue.

Entries keep useful details such as:

- requester
- request time
- map link
- artist/title
- difficulty
- mapper
- requested mods
- ranking status
- star rating

Opening an older History entry does not replace or remove the current active request.

The active queue also has its own manager for reordering and removing maps without deleting History.

---

# Recovery and diagnostics

osu!Requests keeps a recovery snapshot while it is running.

After an unclean shutdown, the app can offer to restore unfinished queue/session state.

It also includes a diagnostics export designed to remove sensitive tokens before creating a support ZIP.

---

# Sending requests to osu!

The receiving osu! account is connected through browser OAuth.

Accepted requests are delivered through osu! chat by the relay account:

```text
valocookie
```

The desktop app does not contain the private sender-account credentials.

---

# Setup

1. Open **osu!Requests**
2. Connect Twitch
3. Connect the osu! account that should receive requests
4. Open **Preferences**
5. Choose osu!stable, osu!lazer or Windows Default
6. Configure any queue rules or optional filters
7. Add OBS overlays if you want them
8. Open requests
9. Let chat cause problems 💜

---

# Privacy

osu!Requests uses Twitch and osu! OAuth for the account connections needed by the app.

The relay only keeps the limited account/session information required for request delivery and abuse prevention.

---

# Acknowledgements

Special thanks to:

- **@ToxicTheTrashPanda**
- **@Syvatzia**
- **@ValoKarma**

for testing osu!Requests, reporting weird edge cases, suggesting features and generally finding ways to break things.

---

# Project status

osu!Requests is actively developed.

The **current GitHub build is v1.2.5**.

Feedback, bug reports and strange streamer-specific edge cases are very welcome.

---

# Disclaimer

osu!Requests is an independent project.

It is not affiliated with or endorsed by **ppy Pty Ltd., osu!, Twitch, or Twitch Interactive, Inc.**
