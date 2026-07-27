# osu! Requests

A small Windows app I made to handle osu! map requests from Twitch chat without having to constantly copy links around while streaming.

The idea is pretty simple: connect Twitch, connect the osu! account where you want to receive requests, and leave the app running. When someone sends a supported beatmap link in chat, osu! Requests picks it up, adds it to the queue, grabs the map information, and sends the request to you through osu! chat.

It started as something I wanted for a friends stream and slowly turned into a proper little desktop app.

## ⚠️ Current Windows build

The Microsoft Store version is currently being prepared for certification.

Until that is approved, the GitHub `.exe` is an unsigned test build. Because of that, Windows SmartScreen or Smart App Control may warn about it or block it on some PCs.

That warning is related to the build not being signed/reputed yet; it does not automatically mean Windows found malware.

Please only download builds from this repository.

I don't recommend turning off Windows security features just to run the test version. Once the Microsoft Store release is approved, that will become the normal/recommended way to install the app.

---

## What it does

### Map requests

osu! Requests watches your Twitch chat for osu! beatmap links and builds a request queue automatically.

You can:

- open or close requests whenever you need to
- set a queue limit from 10 to unlimited
- move to the next request
- copy the current map link
- view previous requests
- clear the queue
- keep existing requests even after closing submissions

The streamer can still submit a map while the queue is closed or full.

Duplicate requests are also caught automatically so the same map doesn't keep getting added.

### Map info

For supported maps, the app can show things like:

- artist and song title
- mapper
- difficulty
- star rating
- BPM and length
- AR, OD, CS and HP
- max combo
- object count
- ranking status
- genre and language

When someone links a specific difficulty, the app tries to use that exact beatmap instead of just the mapset.

### Mods

Viewers can put mods next to their request and the app keeps them attached to the map.

For example:

`+HD`

`+DT`

`HDDT`

`DTHD`

`HD DT`

`dt hd`

The parser is case-insensitive and is meant to be forgiving about how people type combinations.

Those mods are shown with the request and are also included when the map is delivered through osu! chat.

### Twitch stuff

The app connects to Twitch through browser authorization.

It also has:

- automatic confirmation when a request is accepted
- feedback when the queue is closed or full
- duplicate request messages
- `!queue`
- a queue reminder every 15 minutes while requests are waiting
- an optional extra reminder with a custom interval

`!queue` lets viewers check the current queue without the streamer having to explain it every five minutes. :)

### Sending requests to osu!

The receiving osu! account is connected through OAuth in the browser.

Accepted requests are then sent automatically through osu! chat by the relay account `valocookie`.

That means there is no local server to set up and no osu! client secret for users to configure.

Because the actual delivery happens through osu! chat rather than by controlling the game window, the app isn't tied specifically to one desktop client and is intended to work with both osu!stable and osu!lazer.

---

## Setup

1. Open **osu! Requests**
2. Connect your Twitch account
3. Click **CONNECT OSU!**
4. Log into the osu! account where you want to receive requests
5. Authorize the connection
6. Go back to the app
7. Open the queue and let people start sending maps

That's basically it.

You do not need Python or a local relay/server to use the compiled Windows version.

---

## Download

### Microsoft Store

**Coming soon**

The Windows Store build is currently being prepared for Microsoft certification.

Once it is approved, the Store version will become the recommended download.

### GitHub build

The latest `.exe` can still be used for testing in the meantime.

Just keep in mind that the current GitHub build is unsigned, so Windows may treat it as an unknown application.

---

## A little about the backend

osu! Requests uses a small Cloudflare-hosted relay to handle the connection between the desktop app and the osu! sender account.

The important part for users is that you **do not** have to run any server yourself.

Private sender credentials are not included inside the public Windows app.

---

## Privacy

The app uses Twitch and osu! OAuth to connect your accounts.

The receiving osu! token is used to identify the account you authorized and is not kept by the relay afterward.

The relay stores only the limited account/session information it needs to connect your Twitch identity to the osu! account receiving requests and to prevent abuse.

There are no ads, profiling, or sale of personal information.

---

## Project status

This is still a pretty new project, so I'm actively testing it and fixing weird edge cases as people find them.

The public relay is already running. The next major step is getting the Windows build through Microsoft Store certification so people don't have to deal with unsigned-app warnings.

Bug reports and feedback are very welcome.

---

## Disclaimer

osu! Requests is an independent community project.

It is not affiliated with or endorsed by ppy Pty Ltd., osu!, Twitch, or Twitch Interactive, Inc.
