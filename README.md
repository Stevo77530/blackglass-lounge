# BLACKGLASS Lounge

A calm, remote-friendly front door for existing TizenPortal bookmarks.
Optional TizenBrew module, version 0.1.0. Browser tested; TV testing in progress.

## Features

- Watch, Browse, a shared Favorites shortlist, and Help.
- Large text and a bright gold focus border.
- Arrow/OK/Back navigation and an Original Portal escape route.
- Launches saved cards through TizenPortal, preserving URLs, ad-block bundles,
  and per-site settings. It does not supply content or create bookmarks.
- A saved card named Flixer Ads Off is used by the primary Watch button when
  present. Otherwise it opens Original Portal to choose a saved site.

## Installation

In TizenBrew Module Manager choose Add GitHub Module and enter:

`Stevo77530/blackglass-lounge@v0.1.0`

Keep the original TizenPortal module installed as a fallback. This module uses
its existing storage origin. It does not replace Samsung Home or autolaunch.
No permanent laptop, phone, or local server is required.

## Operation and recovery

Use arrows to move and OK to choose. Back returns to Watch, then Original Portal.
Samsung Home provides the normal route to installed TV apps and inputs.
Choose favorites to edit the shared shortlist. Favorites do not isolate accounts
or watch history. Player controls and subtitles remain the website's own.

Rollback: select the original TizenPortal module in TizenBrew. To remove the
experiment, remove only BLACKGLASS Lounge in Module Manager. Do not clear browser
data or uninstall TizenBrew.

## Technical details

The overlay reads tp_apps without writing it. It stores only its own preferences
under blackglass-lounge-v1 and calls TizenPortal.loadSite with cloned card data.
The Portal page supplies its own runtime. Target pages receive the bundled
TizenPortal 1120 runtime so bundle payloads can be applied there too.

The runtime is derived from https://github.com/axelnanol/tizenportal/tree/1120,
commit 0c1ba77b1a3d779bc12f3bf89ce4745f94398caa. See LICENSE-TizenPortal.
The lounge source is readable at the end of dist/blackglass.js.

TizenBrew loads modules via jsDelivr. Internet access is required. The upstream
Portal HTML may change independently; its version query is not an immutable
pin. This does not upgrade the television's browser engine or guarantee that
every website works. TV reboot, playback, and household acceptance must be
tested on the target device before relying on the module for daily viewing.

No analytics, microphone, camera, credentials, or household bookmark data are
included in this repository.
