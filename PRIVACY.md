# Direction Clipper — Privacy Policy

_Last updated: 2026-09-05. Applies to the browser extension "Direction Clipper" (Chrome, Firefox, Safari)._

## What the extension is

Direction Clipper saves web pages into **Direction**, a self-hosted personal
knowledge server that **you** run and configure. The extension has no server of
its own, no account system, and no analytics.

## What data it handles, and where it goes

- **The page you clip.** When you press *Save*, the extension extracts the
  readable article (or the full page, if you choose) from the current tab,
  fetches the page's images, and sends them in one request to the **Direction
  server URL you entered in the options page**. Nothing is sent until you have
  configured that URL, and nothing is sent unless you press *Save*.
- **Tags and notes you type** in the popup are sent along with the clip, to the
  same server.
- **Settings** (your server URL, an optional API key, and your last-used
  options) are stored locally in the browser's extension storage. They never
  leave your browser except as part of requests to your own server.

The **only** network destinations are (1) the server URL you configured and
(2) the image hosts of the page you are clipping, which are fetched to capture
the images.

## What it does not do

- No analytics, telemetry, or crash reporting.
- No third-party services, ad networks, or trackers.
- No data is sold, shared, or transferred to anyone. The developer never sees
  your data: it goes from your browser to your server.
- No browsing history is read or recorded. The extension only acts on the tab
  you clip, when you clip it.

## Permissions, explained

- `activeTab`, `scripting`: read the page you are clipping when you press *Save*.
- `storage`: remember your server URL and settings.
- Host access to all sites (`<all_urls>`): needed to fetch images on any page
  you clip when the page's own context is blocked from fetching them
  (cross-origin images), and to reach whatever host your Direction server runs
  on.

## Retention

The extension retains nothing but your settings, which you can clear at any
time by removing the extension. What happens to a saved clip is governed by
your own Direction server, which you control.

## Source

The extension is open source (MIT). Build instructions and source accompany
each release.

## Contact

a.colangelo@pm.me
