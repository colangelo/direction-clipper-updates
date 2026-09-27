# Direction (browser extension) — Privacy Policy

_Last updated: 2026-09-27. Applies to the browser extension "Direction"
(formerly "Direction Clipper") on Chrome, Firefox and Safari, version 0.7.18
and later._

## What the extension is

The extension is the browser companion of **Direction**, a self-hosted
personal knowledge server that **you** run and configure. It does two things:

1. **Saves pages.** On *Save* it saves the current page into your Direction
   server, in whichever mode you choose: the readable article with its images,
   the same article as Markdown, or a full snapshot of the whole page as one
   self-contained HTML file.
2. **Closes tabs you have already decided to drop.** In Direction you triage
   your open tabs and mark some to be closed; the extension carries out those
   decisions in the browser.

The extension has no server of its own, no account system, and no analytics.
The developer never receives any of your data.

## What data it handles, and where it goes

- **The page you save.** When you press *Save*, the extension reads the current
  tab and sends the result in one request to the **Direction server URL you
  entered in the options page**. Page content is not uploaded unless you press
  *Save*. The duplicate check described below sends the page URL before Save.
  What is read depends on the mode
  you pick: the readable article and its images, the same article as Markdown,
  or — in full snapshot mode — the entire page, which means fetching the page's
  **subresources** (stylesheets, fonts and images) so they can be inlined into
  one self-contained HTML file. Page scripts are excluded from a snapshot and
  frames are not captured. The title, the byline, and any tags or note you type
  in the popup travel with the clip.
- **Duplicate check (0.7.18 and later).** Opening the clipping popup sends the
  active page's original HTTP(S) URL, including its query and fragment, to your
  configured Direction server to ask whether it is already saved. This happens
  **before Save**, without sending page content. The native Apple share sheet
  similarly checks the shared page URL. A source or connection-setting change,
  or a failed Save, can trigger a fresh check. The lookup sends no cookies,
  bypasses caches, refuses redirects and uses your optional API key. The answer
  is a boolean; checking never blocks saving another copy. Your server may log
  request URLs, so its logging and retention settings apply.
- **Tab closing.** This feature is **off until you explicitly bind the
  install** to a device in the options page. Once bound, every 30 minutes and
  when you press the button in the popup, the extension (a) downloads from your
  server the list of tabs you decided to close, (b) reads the URLs of the tabs
  currently open in this browser **locally**, to find the ones on that list,
  (c) closes only exact, unambiguous matches, and (d) reports back to your
  server, per decision, whether the tab was closed, and the URL it observed for
  that tab. **The extension never uploads your list of open tabs**: the only
  URLs sent by the tab-closing feature are those of tabs you had already marked
  in Direction, together with the outcome. The separate duplicate check sends
  the current page URL as described above.
- **Settings** (server URL, optional API key, the bound device name, last-used
  options) are stored locally in the browser's extension storage and leave it
  only as part of requests to your own server.

The **only** network destinations are (1) the Direction server URL you
configured and (2) the hosts serving the subresources (images, stylesheets,
fonts) of a page you are saving.

## What it does not do

- No analytics, telemetry, or crash reporting.
- No third-party services, ad networks, or trackers.
- No data is sold, shared, or transferred to anyone other than your own server.
- No browsing-history database is collected. The active page URL is sent for
  duplicate checking when you open the clipping popup. Other open-tab URLs are
  read locally for bound close-decision matching; the full tab list is not uploaded.

## Permissions, explained

- `activeTab`: access the current page URL when you open the popup, including
  its duplicate check. `scripting`: read the page content when you press *Save*.
- `storage`: remember your server URL, API key and settings.
- `alarms`: run the tab-closing pass every 30 minutes once you have bound it.
  Browser extension background workers are short-lived, so a plain timer would
  not survive; an alarm is the supported way to wake up on a schedule.
- Host access to all sites (`<all_urls>`): fetch the subresources — images,
  and in snapshot mode stylesheets and fonts too — of any page you save,
  including when the page itself is blocked from fetching them (cross-origin);
  reach whatever host your Direction server runs on; and read the URLs of open
  tabs so close decisions can be matched. No `tabs` permission is requested.

## Retention

The extension retains only your settings, which are removed with the
extension. What happens to a saved clip or a recorded close decision is
governed by your own Direction server, which you control.

## Source

The extension is open source (MIT). Build instructions and source accompany
each release.

## Contact

a.colangelo@pm.me
