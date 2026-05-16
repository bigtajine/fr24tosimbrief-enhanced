# FR24 → SimBrief **Enhanced**

Static web app that pulls FlightRadar24 flight details (via the upstream API) and opens **SimBrief** dispatch with sensible defaults—without ads or trackers.

**Live site (GitHub Pages):**  
https://bigtajine.github.io/fr24tosimbrief-enhanced/

## What this fork aims to fix

This project aims to **correct mistakes and gaps** in how FR24-style workflows send data to SimBrief—for example:

- **Flight identity:** Uses numeric **`fltnum`**, **IATA `airline`**, and **`callsign`** (ICAO-style) instead of mixing marketing flight numbers or ICAO-only airline codes into the wrong fields.
- **US carriers:** Adds **`units=LBS`** for US-flag airlines when generating dispatch links so weights match typical US ops (country from FR24 when present, plus a curated US ICAO list as fallback).
- **Privacy / UX:** Removes third-party advertising scripts and unnecessary trackers from the mirrored UI.
- **Branding:** Clearly labeled **Enhanced** so it is distinct from the original public site.

Upstream flight/history APIs still point at **`fr24tosimbrief.com`** from this build; if you self-host APIs later, adjust those URLs in `docs/index.html`.

## Repo layout

| Path | Purpose |
|------|--------|
| `docs/` | GitHub Pages root (`index.html`, vendored Leaflet, `robots.txt`, `.nojekyll`) |

## Local preview

From the repo root:

```bash
cd docs
python -m http.server 8080
```

Open http://localhost:8080/

## Deploy

Pages is configured to publish from the **`docs`** folder on **`main`**. Push to `main` to refresh the live site.

## License / attribution

Flight data concepts tie to FlightRadar24; OFP generation is via SimBrief. Respect their terms of use when integrating or extending.
