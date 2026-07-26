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
- The currently selected map is highlighted and kept at the top of History

### Map Information
- Song title, artist, and mapper
- Difficulty name and star rating
- BPM and map length
- AR, OD, CS, and HP
- Max combo and object count
- Ranking status, genre, and language when available

### Twitch Integration
- Twitch account authorization through the browser
- Automatic chat confirmation when a request is accepted
- Duplicate request detection with chat feedback
- `!queue` command for viewers
- Automatic `/me` queue reminder every 15 minutes while maps are waiting
- Optional extra queue reminder
- Adjustable extra reminder interval from 10 seconds to 10 minutes
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

This does **not** mean Windows has detected the app as a virus.

The app is currently distributed as an unsigned Windows application. Because it is a small, independently distributed program without an established Microsoft SmartScreen reputation, Windows may classify it as an **unrecognized app** when it is downloaded.

To open it:

1. Make sure you downloaded the app from the official GitHub release.
2. Open `OsuMapRequests.exe`.
3. On the SmartScreen window, click **More info**.
4. Click **Run anyway**.

You should never disable Windows Defender or SmartScreen to use the app.

The warning may appear again after updates because each new unsigned build is treated as a new executable by SmartScreen.
