# Changelog

## v2.3.0 — current
- Full responsive pass: fluid header/readout type sizing, safe-area padding
  for notches and home-indicator areas on installed iOS apps
- Player card no longer stays sticky on phone/tablet widths (was crowding
  the station list on short screens)
- Dial shrinks further on short-height mobile viewports
- Station rows and filter chips tightened for narrow screens, larger touch
  targets, horizontally scrollable genre chips instead of wrapping
- Search box and state dropdown stack full-width below 480px

## v2.2.0
- Added iOS/Android home-screen install support: apple-touch-icon, web-app
  meta tags, and an embedded app icon
- File renamed to `index.html` for static hosting (GitHub Pages, etc.)
- Version tag added to the page footer

## v2.1.0
- Added fallback across six different Radio Browser API servers instead of
  a single hardcoded one
- Added an on-screen technical-details panel when the station directory is
  unreachable, so a real network problem can be told apart from a code bug
- Fixed a bug where the request-timeout mechanism itself broke station
  loading inside sandboxed preview environments (the timeout used
  `AbortSignal`, which can't be passed through some in-app browser previews)

## v2.0.0 — India edition
- Switched from a fixed station list to a live fetch from the Radio Browser
  directory, filtered to India
- Added filtering by state/city and by genre/language tag
- Added HLS stream support (via hls.js) for stations that use that format

## v1.0.0 — initial release
- Vintage radio-dial UI: rotating needle, LCD-style frequency readout
- Fixed list of ~20 international stations (BBC, RAI, WDR, SomaFM, Radio
  Paradise, KEXP)
- Play/pause, volume control, text search, genre filter chips
- "Add your own station" box for custom stream URLs
