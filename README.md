## Features

### Map Requests
- Automatic detection of osu! beatmap links in Twitch chat
- Automatic request queue
- Opens the exact difficulty linked by the viewer
- One-click **Open in Lazer**
- Automatically brings osu!lazer to the foreground
- Opened requests automatically advance the queue
- Skip, copy, and clear request controls
- Request history with the ability to reopen older maps
- Current request is highlighted and kept at the top of History
- Adjustable queue size limit from **10 requests to Unlimited**
- Ability to **open or close the request queue at any time**
- Existing requests remain available when the queue is closed
- New submissions are automatically rejected while the queue is closed
- Automatic chat feedback when the queue is full or closed

### Map Information
- Song title, artist, and mapper
- Difficulty name and star rating
- BPM and map length
- AR, OD, CS, and HP
- Max combo and object count
- Ranking status, genre, and language when available
- Exact Beatmap difficulty detection
- Requested mod detection and display
- Supports common mods such as `HD`, `DT`, `HR`, `NC`, `FL`, and combinations such as `+HDDT`

### Twitch Integration
- Twitch account authorization through the browser
- Automatic chat confirmation when a request is accepted
- Requested mods included in confirmation messages
- Duplicate request detection with chat feedback
- Full-queue detection with chat feedback
- Closed-queue detection with chat feedback
- `!queue` command for viewers
- `!queue` shows the current queue size, queue limit, requester order, requested mods, and whether the queue is closed
- Automatic `/me` queue reminder every **15 minutes** while maps are waiting
- Optional extra queue reminder
- Adjustable extra reminder interval from **10 seconds to 10 minutes**
- Automatic Twitch reconnection and token refresh

### Application
- Dark-mode desktop interface
- Standalone Windows `.exe`
- No Python installation required for users
- Designed specifically for osu!lazer

---

## Windows SmartScreen Notice

When opening the app for the first time, Windows may display:

> **Windows protected your PC**  
> Microsoft Defender SmartScreen prevented an unrecognized app from starting.

This does **not** mean Windows has detected the application as a virus.

The application is currently distributed as an unsigned Windows executable. Because it is a small independently distributed program without an established Microsoft SmartScreen reputation, Windows may initially classify it as an **unrecognized app**.

To open it:

1. Make sure you downloaded the application from the official GitHub release.
2. Open `OsuMapRequests.exe`.
3. On the SmartScreen window, click **More info**.
4. Click **Run anyway**.

You should never need to disable Windows Defender or SmartScreen.

The warning may appear again after updates because new unsigned builds can be treated as new executables by SmartScreen.
