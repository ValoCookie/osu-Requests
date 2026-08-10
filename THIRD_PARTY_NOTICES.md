# Third-party notices

## tosu

osu!StreamDeck can bundle the official **tosu** Windows runtime as a separately launched localhost telemetry component.

- Project: **tosu**
- Upstream repository: https://github.com/tosuapp/tosu
- Pinned integration release: **v4.25.1**
- Exact corresponding source tag: https://github.com/tosuapp/tosu/tree/v4.25.1
- Official release: https://github.com/tosuapp/tosu/releases/tag/v4.25.1
- License: **GNU Lesser General Public License v3.0 (LGPL-3.0)**
- Upstream copyright notice: Copyright (C) 2023-2026 Mikhail Babynichev <https://kotrik.ru/>

ValoCookie does **not** claim authorship of tosu. The osu!StreamDeck release build downloads the official pinned Windows runtime, verifies the expected SHA-256, keeps it as a separately executed program, and communicates with it through the local WebSocket/JSON API on `127.0.0.1:24050`.

The relevant license texts are kept in the public repository under `THIRD_PARTY_LICENSES/`. Keep this notice, those license texts, and the exact source link above with any release that contains the tosu runtime.

### ValoCookie integration code

ValoCookie maintains the Twitch/request workflow, UI, OBS endpoints and overlay designs, `!np` hot-cache/fallback logic, runtime lifecycle and single-instance guard, diagnostics, update flow and Windows packaging. Those components are not presented as part of tosu.

### Read-only fallback technical references

The ValoCookie fallback map detector was informed by public tosu memory-layout/signature material for compatibility. The private development package documents the exact upstream files in `THIRD_PARTY_TECHNICAL_REFERENCES.txt`.
