# osu! Requests

A small Windows app I made for handling osu! map requests from Twitch chat without having to constantly copy links around while streaming.

I originally started this because a friend of mine wanted something for her stream after ronniabot wasn't working properly in lazer, and it slowly turned into a proper little desktop app.

The idea is pretty straightforward: viewers paste an osu! beatmap link in Twitch chat, the app picks it up, adds it to a queue, grabs the map information and requested mods, and sends accepted requests directly to the osu! account you connected.

## ⚠️ Current Windows build

The Microsoft Store version is currently in certification.

In the meantime, the GitHub `.exe` is available, but it is unsigned. Because of that, Windows SmartScreen or Smart App Control may warn about it or block it on some PCs.

That warning is related to the build not being signed/reputed yet; it does not automatically mean Windows found malware.

Please only download builds from this page.

I don't recommend turning off Windows security features just to run the app. Once the Microsoft Store version is approved, that will become the normal/recommended way to install it.

---

## What it does

### Map requests

osu! Requests watches your Twitch chat for osu! beatmap links and builds a request queue automatically.

You can:

- open or close requests whenever you need to
- set a queue limit from 1 to unlimited
- move to the next request
- copy the current map link
- open the current map directly in osu!
- view previous requests
- clear the queue
- keep existing requests even after closing submissions

The streamer can still submit a map while the queue is closed or full.

Duplicate requests are also caught automatically so the same map doesn't keep getting added.

When a map is opened from the request window, it can be removed from the active queue while still remaining available in request history.

The app also minimizes its windows after opening a map so osu! can take focus without the request window staying in the way.

### Request history

The History window keeps the requests received during the current app session, including maps that have already left the active queue.

Each history entry shows the map information, requester, requested mods and star rating.

The original osu! beatmap link is also kept in History.

You can:

- click the map link to open it directly in osu!stable or osu!lazer
- copy the map link with the **COPY** button
- reopen an older requested map without changing the current queue

Opening a map from History minimizes both the History window and the main osu! Requests window so osu! can take focus.

Star ratings are kept in their own aligned column to make the History list easier to scan.

### Map info

For supported maps, the app can show things like:

- artist and song title
- mapper
- exact difficulty
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

Because the actual delivery happens through osu! chat rather than by controlling the game window, the app isn't tied specifically to one desktop client and is intended to work with both osu!stable and osu!lazer.

### App startup

The **APP STARTUP** button lets you choose how osu! Requests should behave when it launches.

You can choose between:

- **Open window** — launch the app normally and close it completely when pressing X
- **System tray** — start the app in the Windows system tray and return it to the tray when pressing X

The setting is saved for future launches.

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

---

## Download

### Microsoft Store

**Coming soon**

The Microsoft Store version is currently in certification.

Once it is approved, the Store version will become the recommended download.

### GitHub build

The latest `.exe` can still be used.

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

---

## Project status

The project is still pretty new, so feedback, bug reports, weird edge cases and suggestions are very welcome. :)

The public relay is already running, and I'm still actively testing and improving the desktop app.

The next major step is getting the Windows build through Microsoft Store certification so people don't have to deal with unsigned-app warnings.

---

## Disclaimer

osu! Requests is an independent project.

It is not affiliated with or endorsed by ppy Pty Ltd., osu!, Twitch, or Twitch Interactive, Inc.
