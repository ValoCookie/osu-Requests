# osu! Requests

A small Windows app I made for handling osu! map requests from Twitch chat without having to constantly copy links around while streaming.

I originally started this because a friend of mine wanted something for her stream after ronniabot wasn't working properly in lazer, and it slowly turned into a proper little desktop app.

The idea is pretty straightforward: viewers paste an osu! beatmap link in Twitch chat, the app picks it up, adds it to a queue, grabs the map information and requested mods, and sends accepted requests directly to the osu! account you connected.

---

> ### 🎥 Streamer tools by ValoCookie
> **osu!Requests** handles Twitch → osu! map requests.
> Looking for a general pre-stream checklist and health-check app too? **[Check out StreamFlight →](https://github.com/ValoCookie/streamflight)**

---

## 🪟 Current Windows build

osu! Requests is available on the **Microsoft Store**. 🎉

The Microsoft Store remains available as the slower **stable release channel**.

For the newest features and smaller updates, use the **GitHub Releases** build.

[**Download osu! Requests from the Microsoft Store**](https://apps.microsoft.com/detail/9NBFQXB0ZDRT?hl=en-us&gl=GB&ocid=pdpshare)

Newer development builds are published through **GitHub Releases** first, so smaller fixes and beta updates do not have to wait for a Microsoft Store submission.

[**Open osu! Requests releases on GitHub →**](https://github.com/ValoCookie/osu-Requests/releases)

The current development line is **v1.2.5**, adding customizable OBS browser overlays, `!np`, PP filtering, optional review-first handling, richer map filters, queue management, recovery/diagnostics and session stats.

---

## 🧪 Current GitHub development build — v1.2.5

The GitHub build moves faster than the Microsoft Store release and currently adds:

- **three independent OBS Browser Sources**: Current Map, Compact Queue and Map Requests Open — use one, two or all three at once
- **overlay customization** for colors, background opacity, streamer label, queue growth direction, custom sizing, left/right snapping and X/Y positioning
- improved **Current Map overlay positioning**, so the visible card can be placed where you want inside its OBS Browser Source
- Twitch chat command **`!np`** so viewers can see the current / most recently opened requested map
- optional **Review Requests Before Queue** mode with Accept / Reject / Move Up / Move Down
- an **Active Queue Manager** for reordering and removing queued maps without deleting History
- optional map filters for **length, BPM, AR, CS, OD and PP** — leave them blank for unrestricted requests
- **Min/Max PP filtering** based on the estimated maximum PP for a 100% FC on the exact requested difficulty, including requested mods
- rank-status and game-mode filters
- crash/session recovery for the active queue, pending review and History
- redacted diagnostics export
- session statistics with a copyable summary
- shared Twitch permission support for the optional **StreamFlight** integration

---

# What it does

## Map requests

osu! Requests watches your Twitch chat for osu! beatmap links and automatically builds a request queue.

You can:

- open or close requests whenever you need to
- set the overall queue limit from **1 to Unlimited**
- set a separate **per-user queue limit**
- move to the next request manually
- copy the current map link
- open the current map directly in osu!
- view previous requests in History
- reopen older maps without changing the active queue
- clear the active queue separately from History
- keep existing requests even after closing submissions

Duplicate requests are detected automatically so the same map does not keep getting added during the same session.

A map that has already been accepted remains protected from duplicate requests while it exists in History.

**CLEAR HISTORY** resets that session duplicate memory.

---

# Opening maps in osu!

Requested maps can be opened directly from osu! Requests.

The app supports:

- **Windows Default**
- **osu!stable / Classic**
- **osu!lazer**

You can choose your preferred client from **Preferences**.

When a queued map is opened, osu! Requests removes that exact map from the **active queue** after a short safety delay while keeping it safely stored in **History**.

The app also watches supported osu!stable/lazer client activity so it can detect when a queued beatmap link is opened from inside osu! itself.

The goal is simple:

**open the requested map → keep it in History → advance the active queue.**

The main osu! Requests window and History window are automatically minimized when a map is opened so osu! can immediately take focus.

---

# Request History

The **Map Request History** keeps requests received during the current app session, including maps that have already left the active queue.

Each entry keeps useful information such as:

- requester
- artist and song title
- difficulty
- mapper
- ranking status
- requested mods
- star rating
- request time
- original osu! beatmap link

The currently active request is clearly marked with **CURRENT**.

Star ratings use their own aligned column so History stays easy to scan even when usernames and map titles have different lengths.

Each entry also has its own **COPY** button.

You can:

- click the map link to open it directly in osu!
- copy the original link
- reopen an older request
- keep the current active queue untouched when opening an older History entry

Opening a map from History does **not** remove or replace the current active request.

---

# Map information

For supported maps, osu! Requests can display information such as:

- artist and song title
- mapper
- exact difficulty
- star rating
- BPM
- map length
- AR
- OD
- CS
- HP
- max combo
- object count
- ranking status
- genre
- language

When someone links a specific difficulty, the app tries to preserve that exact beatmap instead of treating the request as only a beatmapset.

---

# Requested mods

Viewers can put mods next to their request and osu! Requests keeps them attached to the map.

For example:

`+HD`

`+DT`

`HDDT`

`DTHD`

`HD DT`

`dt hd`

The parser is case-insensitive and intentionally forgiving about how combinations are written.

Requested mods are displayed with the request and are also included when the map is delivered through osu! chat.

---

# Twitch features

osu! Requests connects to Twitch through browser authorization.

It includes:

- automatic confirmation when a request is accepted
- feedback when requests are closed
- feedback when the queue is full
- duplicate-request messages
- customizable queue command aliases
- built-in **`!np` now-playing command**
- configurable queue reminders
- viewer-specific queue limits
- role-based request modes
- excluded-user filtering
- optional Channel Points request mode

---

# Queue controls

## Total queue limit

The overall queue can be limited from:

**1 → Unlimited**

Lowering the limit does not delete maps already waiting.

It only prevents new requests from being accepted until the active queue falls below the selected limit.

---

## Per-user limit

The app also has an optional **PER USER LIMIT**.

This controls how many maps one viewer can have waiting in the active queue at the same time.

It is independent from the total queue limit.

For example:

- Total queue limit: **10**
- Per-user limit: **2**

That means one viewer cannot fill all ten queue positions by themselves.

The broadcaster is exempt from the per-user limit.

---

## Queue reminder

The automatic Twitch queue reminder can be configured from:

**1 minute → 30 minutes**

The reminder runs while requests are waiting.

This helps keep the queue visible in chat without the streamer having to repeatedly mention it.

---

# Preferences

The **PREFERENCES** window keeps the stream-specific request settings together.

## Queue command aliases

The default Twitch command for checking the active queue is:

`!queue`

You can change it or add multiple aliases separated by commas.

For example:

`!queue, !maps, !requests`

Any configured alias can be used by viewers to display the current active queue.

### Now playing command

`!np` is built in for viewers who want to check the map currently being played / most recently opened from the request workflow.

The response includes the map information and osu! link when available. The command has a short per-viewer cooldown to prevent chat spam.

`!np` is reserved by osu! Requests and is separate from the customizable queue aliases.

---

## Preferred osu! app

Choose which osu! client should receive links opened through osu! Requests.

### Windows Default

Uses whichever application Windows currently has registered for osu! links.

### Classic

Prefers **osu!stable / classic**.

### Lazer

Prefers **osu!lazer**.

The preference is saved between sessions.

---

## Star rating limit for requests

You can set a maximum star rating for incoming maps.

Setting the limit to:

**0★ — Unlimited**

allows maps of any star rating.

This can be useful for streams where you want chat requests to stay within a particular difficulty range.

---

## Map filters

The GitHub development build includes optional Min/Max filters for:

- star rating
- map length
- BPM
- AR
- CS
- OD
- PP

**Leave Length, BPM, AR, CS, OD and PP blank to allow any map.** Only fill in Min/Max values when you deliberately want to restrict requests.

For PP filtering, osu! Requests uses the **estimated maximum PP for a 100% FC on the exact requested difficulty**, including requested mods such as `+HDDT`.

If PP filtering is enabled, a request needs to identify a specific difficulty so the app can evaluate it reliably.

You can also control accepted ranking statuses and osu! game modes.

---

## Excluded users

Specific Twitch users can be added to the **Excluded Users** list.

Requests from those users are ignored until they are removed from the list.

This gives the streamer an app-side request filter without needing to block someone from Twitch chat entirely.

---

## Request handling

By default, accepted viewer requests can go directly into the active queue.

Enable **Review requests before adding them to the active queue** when you want incoming maps to wait in Pending first, where you can accept, reject or reorder them.

There are no genre-style request presets to configure — request restrictions live in the normal map filters so the viewer workflow stays straightforward.

---

## Request modes

osu! Requests can restrict map requests based on Twitch roles.

Available role filters include:

- **Subscribers**
- **VIPs**
- **Moderators**

When more than one role is selected, viewers matching **any** selected role may request.

For example, enabling Subscribers and VIPs means either a subscriber **or** a VIP can submit maps.

The broadcaster is always allowed through the role filter.

---

## Channel Points only request mode

The app also supports a **Channel Points Only Request Mode**.

When enabled, map requests are accepted through a selected Twitch Channel Point reward instead of normal chat messages.

The selected reward needs to have **viewer text input enabled**, because the viewer pastes the osu! beatmap link into the redemption message.

This lets streamers turn map requests into a Twitch reward without needing a separate bot command system.

---

# OBS browser overlays

The GitHub development build can host local Browser Source overlays for:

- **Current Map**
- **Compact Queue**
- **Map Requests Open**

Each overlay has its own local URL. Add any of them to OBS as separate Browser Sources — **you can use one or multiple overlays at the same time**.

Overlay appearance and placement can be customized from Preferences, including:

- background, text, accent and open-status colors
- background opacity
- optional streamer label / Twitch username
- custom overlay sizing
- Compact Queue growth from **top → bottom** or **bottom → top**
- snap visible overlay content to the **left** or **right** side
- **X / Y offsets** for fine positioning inside the OBS Browser Source

The left/right snap and X/Y controls also apply to **Current Map**, so the visible card does not have to sit in one fixed location or visually stretch across a wider Browser Source.

---

# How To

osu! Requests includes a built-in **HOW TO** window.

It gives a quick reference for both viewers and the streamer, including:

- how viewers request maps
- supported mod syntax
- duplicate-request behavior
- the currently configured queue command
- how the per-user limit works
- streamer exemptions
- what happens when a requested map is opened

So the basic usage rules are available directly inside the app instead of living only in this README.

---

# Sending requests to osu!

The receiving osu! account is connected through OAuth in the browser.

Accepted requests are delivered automatically through osu! chat by the relay account:

`valocookie`

Because delivery happens through osu! chat rather than by directly controlling the game window, the request-delivery system is designed to work with both **osu!stable** and **osu!lazer**.

The desktop app does not contain the private sender-account credentials.

---

# App startup

The **APP STARTUP** button controls how osu! Requests behaves when it launches.

There are two modes.

## Open Window

The app behaves like a standard desktop application.

It starts with the main window visible.

Pressing **X** completely closes osu! Requests.

## Start in Tray

The app starts minimized in the Windows system tray.

Pressing **X** sends the application back to the tray instead of closing it.

To fully close osu! Requests while using this mode, choose **Exit** from the tray icon.

The selected startup behavior is saved for future launches.

---

# Microsoft Store stable — what's new in 1.0.3.0

**Version 1.0.3.0** is the current Microsoft Store stable build.

This update includes a pretty large collection of stream-management and quality-of-life improvements.

### Request History

- redesigned Map Request History
- clickable osu! beatmap links
- individual **COPY** buttons
- aligned star-rating column
- **CURRENT** request indicator
- request timestamps
- reopening previous maps without affecting the active queue
- separate queue and History clearing

### osu! integration

- direct map opening from osu! Requests
- support for Windows Default, Classic and Lazer preferences
- improved exact-map detection
- queued maps can advance when opened in osu!
- opened maps remain in History
- automatic window minimization when opening maps

### Queue controls

- overall queue limit from **1 to Unlimited**
- optional per-user queue limit
- configurable queue reminder from **1 to 30 minutes**
- improved duplicate-request handling
- clearing History resets session duplicate memory

### Twitch request controls

- customizable queue command aliases
- maximum star-rating filter
- excluded-user list
- Subscriber request filter
- VIP request filter
- Moderator request filter
- combined role filtering
- Channel Points only request mode

### App usability

- expanded **Preferences**
- built-in **HOW TO** guide
- simplified **APP STARTUP** button
- configurable Open Window / Start in Tray behavior
- improved X-button behavior
- improved system-tray behavior
- general UI cleanup and spacing improvements
- additional map/request detection improvements

---

# Setup

1. Open **osu! Requests**
2. Connect your Twitch account
3. Connect the osu! account where you want to receive requests
4. Authorize the connection in your browser
5. Return to osu! Requests
6. Open **Preferences** and configure any request rules you need
7. Choose your preferred osu! client if needed
8. Set your queue and per-user limits
9. Open the queue
10. Let chat start sending maps

That's basically it. 💜

---


## GitHub build

Newer desktop builds are published through GitHub Releases first so beta fixes and smaller updates can ship without waiting for the Microsoft Store review cycle.

Keep in mind that a standalone GitHub `.exe` may be unsigned, so Windows SmartScreen or Smart App Control can warn about or block it on some PCs.

You should not need to disable Windows security features to use osu! Requests.

For the simplest installation experience, use the Microsoft Store build.

---

# A little about the backend

osu! Requests uses a small Cloudflare-hosted relay to handle communication between the desktop application and the osu! sender account.

The important part for normal users is:

**you do not need to run a server yourself.**

Private sender credentials are not included inside the public Windows app.

---

# Privacy

The app uses Twitch and osu! OAuth to connect your accounts.

The receiving osu! token is used to identify the account you authorized and is not kept by the relay afterward.

The relay stores only the limited account/session information it needs to connect your Twitch identity to the osu! account receiving requests and to prevent abuse.

---

# Acknowledgements

osu! Requests got better thanks to a few people who helped test it at different stages of development, report bugs, try weird edge cases, and give feedback along the way. 💜

Special thanks to:

- **@ToxicTheTrashPanda**
- **@Syvatzia**
- **@ValoKarma**

for helping test osu! Requests throughout development and for all the bug reports, feedback, ideas, and general chaos testing.

---

# Project status

osu! Requests is still a pretty new project, so feedback, bug reports, weird edge cases and suggestions are very welcome. :)

The app is publicly available through the Microsoft Store, the Cloudflare relay is running, and development is continuing.

The Microsoft Store remains the slower stable channel. The current GitHub development line is **v1.2.5**.

---

# Disclaimer

osu! Requests is an independent project.

It is not affiliated with or endorsed by **ppy Pty Ltd., osu!, Twitch, or Twitch Interactive, Inc.**
