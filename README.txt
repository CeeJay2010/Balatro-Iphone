BALATRO — iPHONE OFFLINE WEB APP

WHAT I CHANGED
- Kept your original single-file game and embedded game assets intact.
- Added a web app manifest and iPhone Home Screen metadata.
- Added a service worker that caches the full game for offline launching.
- Removed the external Cloudflare analytics script, so the game does not need that network request.
- Improved the game's existing IndexedDB save syncing: it now flushes periodically and when the app is backgrounded/closed.
- Added app icons.

IMPORTANT
The original game already uses Emscripten IDBFS backed by IndexedDB for its virtual save folder. The updated file strengthens the timing of saves, but actual save behavior still depends on the game writing its save files through that filesystem.

HOW TO INSTALL ON IPHONE
1. Upload the CONTENTS of this folder to a static HTTPS host (GitHub Pages is one option). Keep index.html, sw.js, manifest.webmanifest, and both icons together in the same folder.
2. Open the hosted HTTPS address in Safari on your iPhone.
3. Wait for the game to finish loading once while online. This lets the service worker cache the 21 MB game.
4. In Safari, tap Share -> Add to Home Screen. If offered, enable "Open as Web App", then tap Add.
5. Launch the new Balatro icon from your Home Screen. Open it once online before testing offline.
6. Turn on Airplane Mode and relaunch to test offline play.

NOTES
- Do not open index.html directly from the Files app if you want the installed offline web-app behavior. Service workers require HTTPS (or localhost).
- Keep using the same hosted address and Home Screen icon; IndexedDB saves are tied to that site origin. Clearing Safari website data or deleting the web app may erase saves.
- The first online load needs enough time to cache the full HTML file. Do not close Safari during the initial install/cache.
