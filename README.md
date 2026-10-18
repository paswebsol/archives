# Business Archives Pro — GitHub Pages client deployment

This folder is the **client app only**. The existing Business Archives Pro HTML and its application logic have been retained; PWA manifest, icons, and offline service worker were added for installation on Android, iPhone/iPad, and desktop browsers.

## Publish on GitHub Pages
1. Create/open the GitHub repository for the client app.
2. Upload **all files and the `icons` folder from this package** to the repository root (keep `index.html`, `manifest.webmanifest`, and `service-worker.js` together).
3. In repository **Settings → Pages**, choose **Deploy from a branch**, select your main branch and `/ (root)`, then Save.
4. Open the published HTTPS GitHub Pages address. Do not test installability by opening the HTML as a local file.

## Install on devices
- **Android (Chrome):** open the HTTPS site, tap the browser menu, then **Install app** or **Add to Home screen**.
- **iPhone/iPad (Safari):** open the HTTPS site, tap **Share → Add to Home Screen**. iOS does not always show a browser install prompt.
- **Windows/macOS/Linux:** open the HTTPS site in a supported browser (usually Chrome or Edge) and use the install icon/menu, or keep it bookmarked.

The service worker caches the app shell for offline opening after the first successful online visit. Existing records remain governed by the app's existing browser storage; browser storage is device/browser-specific and should be backed up using the app's own backup feature. Installing the PWA on another device does not automatically copy records.

## Important licence security
**Do not publish `Business Archives Issuer.html` or the owner signing key in this public repository.** This deployment ZIP intentionally contains only the client app. The issuer generates a signed text licence key (no licence JSON file). Issue a separate key for each customer/device/browser.

## Included
- `index.html` — existing client app, now the GitHub Pages entry point
- `manifest.webmanifest` — install metadata
- `service-worker.js` — offline app-shell caching
- `icons/` — install icons

## Licence key activation
- Open `Business Archives Issuer.html` privately, enter the customer name and the Device ID shown by their client app, select a duration, and generate the signed key.
- Copy the full `BAP1.…` key and send it to the customer. The customer pastes it into the client app; no licence JSON file is used.
- The key is RSA-SHA256 signed and verified by the client. Altered or fabricated keys fail signature validation.
- Keep `Business Archives Issuer.html` private; it contains the signing private key. Do not publish it with the client app on GitHub Pages.
