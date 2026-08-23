# Direction Clipper — signed Firefox builds

Self-distributed builds of the [Direction](https://github.com/colangelo) web clipper for
Firefox. Every `.xpi` here is **signed by Mozilla** (AMO unlisted channel), so Firefox
installs it normally — it is simply not listed in the AMO catalogue.

## Install

1. Open the latest `.xpi` link directly in Firefox:
   **[direction_clipper-0.6.3.xpi](https://raw.githubusercontent.com/colangelo/direction-clipper-updates/main/direction_clipper-0.6.3.xpi)**
2. Firefox will ask you to confirm the install. That's it.

Updates are automatic from this repository — the extension checks `updates.json`, so you
only ever install by hand once.

If the link downloads the file instead of installing it, drag the downloaded `.xpi` onto
Firefox's `about:addons` page.

## Configure

The clipper sends pages to a **Direction server**, and these public builds ship with **no
server address**. After installing, open the extension's popup and enter the URL of the
Direction instance you want to clip into. Without that, nothing is sent anywhere.

## What's in here

| file | what it is |
|---|---|
| `direction_clipper-*.xpi` | the signed extension, one per release |
| `updates.json` | the update manifest Firefox polls; generated from the xpis present, never hand-edited |

Requires Firefox 142 or newer.
