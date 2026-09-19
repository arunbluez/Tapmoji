# Tapmoji

A big-keyboard emoji canvas for a toddler on an iPad. Tap an emoji to drop it on the canvas and hear its name, drag it around, double-tap to spin it, pinch to resize, drag it onto the 🧹 corner to remove it, or tap the 🧹 button top-right to clear the whole canvas. Swipe the picker left or right to change category. The scene is saved on every change and comes back exactly as it was after the app is killed, the iPad restarts, or Guided Access ends. Works fully offline as a home-screen web app. No framework, no build step, no network calls after install.

Files: `index.html` (all the code), `sw.js` (offline cache), `manifest.json`, `icon-512.png`.

## Deploy — GitHub Pages

1. Repo `tapmoji`, files at root. Push to `main`.
2. Settings → Pages → Source: *Deploy from a branch* → `main` / `/ (root)` → Save.
3. Live in ~1 min at `https://<user>.github.io/tapmoji/`.
4. On each update: bump `CACHE` in `sw.js`, push, then open the app on the iPad once while online.

All paths in `manifest.json` and `sw.js` are relative (`./`) because the app is served from a subpath.

Note: GitHub only starts a Pages build for pushes made from a GitHub account (the website editor, the GitHub app, or a local machine). Pushes made through a Claude Code session land on `main` but do not start a build, so after such an update make any small commit yourself, or re-save the Pages source in Settings, and check the "pages build and deployment" run under Actions.

## Install on the iPad (at home, on Wi-Fi)

1. Open the URL in Safari.
2. Share → *Add to Home Screen*.
3. Open it from the home screen once while online (this caches everything).
4. Airplane Mode on, close and reopen the app. It must load and speak. Do this before the flight.

Home-screen web apps are exempt from Safari's 7-day storage eviction; cache and localStorage survive.

## Guided Access (keeps him inside the app)

Settings → Accessibility → Guided Access → on, set a passcode. Open Tapmoji, triple-click the top button, tap *Start*. Triple-click + passcode to exit. Set Auto-Lock to Never (or disable Sleep/Wake in the Guided Access options) for the flight.

## Parent controls

Bottom-right corner, faint icons. Hold 🧹 for 2 seconds to clear the canvas (the visible 🧹 button top-right does the same with one tap). Hold ⚙ for 2 seconds for settings: speech on/off, sounds on/off, voice language (only languages with an installed voice are listed), speech rate, and a hold-to-reset button that wipes everything. Tap outside the card to close it.
