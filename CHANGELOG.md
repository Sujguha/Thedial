# Changelog

## v2.6.0 — current
- Added a "Singer spotlights" row: filter chips for Kishore Kumar, Lata
  Mangeshkar, Mohammed Rafi, Asha Bhosle, and a combined "90s Playback
  Legends" chip (Kumar Sanu, Udit Narayan, Alka Yagnik, Anuradha Paudwal)
- Matched by station NAME rather than tags, since dedicated fan-run stations
  in the directory identify themselves by name (e.g. "Kishore Kumar Radio")
  rather than a structured artist tag
- A spotlight chip only appears if a live matching station actually exists
  right now — no dead-end chips that always return empty
- No dedicated Arijit Singh or solo Kumar Sanu station exists in the
  directory as of this build (checked directly) — newer/still-active artists
  tend not to have fan-run dedicated streams the way older legends do; Kumar
  Sanu still surfaces under the 90s Legends spotlight

## v2.5.0
- Added Navratri, Dussehra, and Children's Day as seasonal filter chips
  alongside Diwali/Christmas/New Year
- Navratri and Dussehra dates are derived from real lunar-calendar Dussehra
  dates through 2030 (Navratri = the 9 nights immediately before Dussehra)
- Children's Day uses the fixed Nov 14 date (with a 1-day buffer either side)
- Only one seasonal chip shows at a time, whichever is currently in season

## v2.4.0
- Added a seasonal filter chip that appears automatically around Diwali,
  Christmas, and New Year, matching stations by keyword against their tags
  and names (the directory doesn't tag festivals directly, so this is
  keyword-based rather than an explicit "Diwali" tag)
- Diwali's window uses real lunar-calendar dates through 2030 rather than a
  fixed day, since it shifts every year
- Seasonal chip gets a distinct gold/rust gradient so it stands out from the
  regular genre chips

## v2.3.0
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
