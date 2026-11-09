BALATRO — iPHONE LANDSCAPE / GITHUB PAGES BUILD

This is a self-contained web build. The game engine and game files are embedded
inside index.html; there are no external game asset folders to upload.

GITHUB PAGES
1. Extract this ZIP.
2. Upload ALL extracted files (index.html, sw.js, manifest.webmanifest,
   icon-192.png, icon-512.png, README.txt) to the root of your GitHub repository.
3. In GitHub, open Settings > Pages.
4. Set the deployment source to Deploy from a branch, choose your main branch
   and the /(root) folder, then Save.
5. Open the published HTTPS GitHub Pages URL on your iPhone.

iPHONE PLAYING
- Play with the phone held horizontally (landscape).
- For the best full-screen experience, open the Pages URL in Safari, use Share >
  Add to Home Screen, then launch the installed web app in landscape.
- The page hides browser scrolling/selection gestures and sizes the game canvas
  to the full browser layout viewport (using innerWidth/innerHeight, not iOS visualViewport), including after rotation or returning to the app.
- Touch input is handled by the bundled game runtime and forwarded to the game's
  cursor controls. Tap and drag directly on the game as appropriate.
- The web app manifest requests landscape orientation. iOS Safari may not force
  rotation while the site is in a normal browser tab; rotate the phone manually.
- GitHub Pages must serve the site over HTTPS for the service worker/offline cache
  to work. The game itself loads from the self-contained index.html.

SAVES
The web build stores its virtual game save data in browser storage (IndexedDB).
Use the same iPhone browser or installed web app to keep using the same save data.
Clearing Safari website data can erase local saves.
