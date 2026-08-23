# osu!StreamDeck v2.1.0

## Highlights

- Added optional Patreon supporter linking through the existing Patreon text.
- Active paid, trial, and gifted ValoCookie memberships can be verified automatically without requiring Patreon and osu! usernames to match.
- Added secure creator-account dev supporter handling and server-side creator campaign verification.
- Patreon client secrets and creator access tokens remain in the Cloudflare Worker, not in the desktop executable.
- Supporter avatar cookie-heart rendering and account-row alignment were polished.
- Queue Reminder now has a clear disabled/greyed-out state when switched off.
- Twitch long-session refresh/reconnect handling and diagnostics were hardened.
- Overlay eyedropper, status-card alignment, supporter footer copy, and other UI details received additional polish.

## Privacy

Patreon linking is optional. User-facing callback pages no longer display internal verification/debug strings. Sanitized verification state remains available through Bug Report diagnostics, with tokens and secrets excluded.

## Publishing

Release tag: `v2.1.0`  
Release asset: `osuStreamDeck.exe`
