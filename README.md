# osu!lazer Requests

A lightweight Windows desktop utility for managing osu!lazer beatmap requests from Twitch chat and delivering accepted requests directly to a connected osu!lazer account.

> ## ⚠️ Windows test-build notice
>
> **osu!lazer Requests is currently undergoing Microsoft Store certification.**
>
> The current GitHub `.exe` is an **unsigned test build**. Windows Smart App Control or Microsoft Defender SmartScreen may therefore warn that the app is unrecognized or block it.
>
> This warning does **not automatically mean Windows detected malware**; the GitHub build simply does not yet have Microsoft Store signing and reputation.
>
> For now, only use builds downloaded directly from this official repository. **Do not disable Windows security features system-wide just to run osu! Requests.**
>
> Once Microsoft Store certification is complete, the recommended Windows installation will be the Microsoft Store version, which will be signed through the Store distribution process.

---

## What osu!lazer Requests does

osu!lazer Requests connects to a Twitch channel, watches chat for supported osu! beatmap links, adds valid requests to a queue, retrieves beatmap information, detects requested mods, and automatically sends accepted requests to the connected osu! recipient account through osu! chat.

The desktop app is designed for streamers who want a simple request workflow without needing viewers to use a separate website or form.

---

## Features

### Twitch map requests

- Automatic detection of osu!lazer beatmap links in Twitch chat
- Automatic request queue with a highlighted current request
- Exact beatmap difficulty detection when a difficulty-specific link is provided
- Duplicate-request protection with Twitch chat feedback
- Adjustable queue limit from **10 requests to Unlimited**
- Open or close the request queue at any time without removing existing requests
- New viewer requests are automatically rejected while the queue is closed
- Automatic feedback when the queue is full or closed
- The authenticated streamer can still add their own requests when the queue is closed or full
- Session request history
- Current request remains highlighted at the top of History
- `NEXT`, `COPY LINK`, `HISTORY`, and `CLEAR` controls

### osu!lazer delivery

- Connect the receiving osu!lazer account through browser-based OAuth
- Accepted Twitch requests are delivered automatically through osu! chat
- Requests are sent by the relay sender account `valocookie`
- The receiving user's osu! OAuth token is used only to identify the authorized account and is not retained by the relay

### Map information

When available, osu! Requests displays:

- Song title and artist
- Mapper
- Difficulty name
- Star rating
- BPM
- Map length
- AR, OD, CS, and HP
- Max combo
- Object count
- Ranking status
- Genre and language
- Exact beatmap URL

### Requested mods

osu!lazer Requests detects common requested mods from Twitch chat and keeps them attached to the request.

Examples include:

- `+HD`
- `+DT`
- `+HR`
- `+NC`
- `+FL`
- combined requests such as `+HDDT`

Mods can be written alongside the beatmap link and are shown in the queue, Twitch feedback, history, and osu! delivery message.

### Twitch integration

- Twitch account authorization through the browser
- Automatic chat confirmation when a request is accepted
- Requested mods included in confirmation messages
- Duplicate-request feedback
- Full-queue feedback
- Closed-queue feedback
- `!queue` command for viewers, shows queue size, queue limit, requester order, requested mods, and whether the queue is closed
- Automatic `/me` queue reminder every **15 minutes** while maps are waiting
- Optional extra queue reminder that can be adjusted from **10 seconds to 10 minutes**
- Automatic Twitch reconnection and token refresh

### Public relay

The current public version uses a Cloudflare-based relay so users do not need to run a local Python server.

The relay uses:

- Cloudflare Workers for the public HTTPS API
- Cloudflare D1 for persistent relay/session data
- A Cloudflare Durable Object to serialize outgoing osu! messages from the shared sender account
- Twitch identity validation before recipient sessions or relay requests are accepted

Private osu! sender credentials are **not embedded in the public Windows application**.

### Application

- Dark-mode desktop interface
- Standalone Windows application
- Designed for Twitch streamers and osu! players

---

## Download

### Microsoft Store

🕒 **Certification in progress**

The Microsoft Store release is currently being reviewed by Microsoft.

Once certification is complete, the Microsoft Store version will become the recommended way to install osu! Requests on Windows because it will use Microsoft Store signing and distribution.

### GitHub test build

The current GitHub `.exe` remains available for testing.

Because it is an unsigned executable, Windows may display an unrecognized-app warning, Microsoft Defender SmartScreen warning, or Smart App Control block.

Smart App Control does not provide a per-app **Run anyway** option in every configuration. Some testers may therefore be unable to launch the unsigned GitHub build without changing Windows security settings.

**I do not recommend disabling Windows security features system-wide simply to test the application.**

(But I Myself have it off)

Only download test builds from this official repository.

---

## Basic setup

1. Launch osu! Requests.
2. Connect your Twitch account through the browser.
3. Click **CONNECT OSU!**.
4. Sign in to the osu! account that should receive map requests.
5. Authorize basic account identification.
6. Return to osu! Requests.
7. Open the request queue and let viewers submit supported osu! beatmap links in Twitch chat.

Accepted requests are automatically sent to the connected osu! account.

---

## Privacy and account connections

osu!lazer Requests connects to Twitch and osu!lazer through OAuth.

The desktop application stores its connection/session information locally for the signed-in Windows user.

The public relay validates Twitch identity, links it to the authenticated receiving osu!lazer account, and forwards accepted beatmap requests to that verified recipient.

The receiving user's osu!lazer access token is used only long enough to identify the authorized account and is not stored by the relay.

The relay may store limited account/session information required to provide the service, such as Twitch user ID/login, connected osu!lazer user ID/username, hashed relay-session identifiers, expiry information, and rate-limit state.

The project does not sell personal information or use it for advertising.

---

## Project status

The public Cloudflare relay is online and the first Microsoft Store package is currently in certification.

GitHub remains the home of the source code and development/test releases. Once Microsoft Store certification is complete, the Store will be the recommended trusted Windows installation channel.

---

## Disclaimer

osu!lazer Requests is an independent utility and is not affiliated with or endorsed by Twitch Interactive, Inc. or ppy Pty Ltd.
