# The Dial — India 📻

A minimal, installable web radio player for live Indian FM and public radio
stations, styled like a vintage analog tuner.

**Current version:** v2.2.0 — see [CHANGELOG.md](./CHANGELOG.md) for full history.

## Features

- Vintage dial UI with a needle that moves to each station's assigned frequency
- Live station list pulled from the open [Radio Browser](https://www.radio-browser.info)
  directory — All India Radio channels, FM stations, and regional-language
  broadcasters, refreshed on every page load
- Search by name, language, or city; filter by state and by genre/language tag
- Falls back across six different Radio Browser servers so one being down
  doesn't break the whole list, with an on-screen diagnostic if all of them fail
- Handles both plain MP3/AAC streams and HLS streams (via hls.js)
- Installable to an iOS or Android home screen — opens full-screen with its own
  icon, no browser address bar
- "Add your own station" box for pasting in any direct stream URL

## Tech

A single self-contained `index.html` — no framework, no build step. Google
Fonts are loaded from their CDN, and hls.js is loaded from jsdelivr for HLS
stream support.

## Running it locally

Just open `index.html` in a browser. It fetches live data from
`api.radio-browser.info` on load, so you need an internet connection for the
station list to populate.

## Deploying

Push `index.html` to any static host — GitHub Pages, Netlify, Vercel, etc.
Streaming and the live station-list fetch need the page served from a real
`http(s)` address; it is **not** meant to be published through Claude's own
hosted-artifact preview, since that environment blocks the cross-origin
network requests this page relies on.

## Installing on a phone

Open the hosted URL in **Safari** on iOS (must be Safari, not Chrome) or
**Chrome** on Android, then use the Share/menu button → **Add to Home
Screen**. It'll behave like a normal installed app from then on.

## Known limitations

- Any individual station can go down independently of this app — that's the
  broadcaster's own server, not a bug here.
- Background/lock-screen playback depends on the mobile browser's own
  behavior; a wrapped native app (see the Capacitor project, if you built it)
  handles this more reliably.
- Custom stations added via "Add your own station" only last for the current
  session and aren't saved anywhere.

## Credits

Station data courtesy of the community-run
[Radio Browser](https://www.radio-browser.info) directory.
