# Tornado Tracker PWA

A mobile-first Progressive Web App for viewing preliminary US tornado reports.

## Included
- Responsive dark interface designed for Android
- Map markers and report list
- State filter, search, time-window selector, manual refresh
- Installable PWA manifest and service worker
- NOAA/SPC source links and clear caveat about preliminary reports

## Important data limitation
The Storm Prediction Center's live report feed is preliminary. Preliminary reports generally do **not** include official Enhanced Fujita (EF) ratings or surveyed tornado start/end times, so the app labels ratings as pending and duration as not established instead of guessing. Official EF ratings and surveyed path details are finalized later by the National Weather Service/NOAA Storm Events records.

## Run locally
A PWA requires HTTPS or localhost. In this folder, run a local server such as:

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000`. For installation on an Android phone, deploy the folder to a static HTTPS host (GitHub Pages, Netlify, or Cloudflare Pages), then open the HTTPS URL in Chrome and choose **Install app** / **Add to Home screen**.

## Data endpoint note
The SPC daily report archive formats can change and may not be available for every day. This is a lightweight starter app; if the feed format changes, update `fetchDay()` / `normalize()` in `app.js`. The app is not an emergency alert system. Use official NWS warnings for safety decisions.
