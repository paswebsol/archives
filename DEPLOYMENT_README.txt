Business Archives — CLIENT DEPLOYMENT

This ZIP contains the client application only. The private licence issuer has deliberately been excluded.

GitHub Pages deployment:
1. Create a separate private/public repository for this one app.
2. Upload/extract the CONTENTS of this ZIP into the repository root (so index.html is at the root).
3. Commit and enable GitHub Pages for the main branch/root folder.
4. Open the published link. The app should show its device/browser ID and request its own signed licence key.
5. Issue a key using the matching private issuer tool and the exact ID shown by the client. Never upload the issuer tool to the public repository.

One key is bound to this app's browser installation ID. Clearing browser storage, changing browser profiles, or moving to another device may require a new key. This offline/browser-based protection is not equivalent to a server-enforced hardware lock and can be bypassed by a determined person who modifies the client code.


LICENSING — SOFTWARE SALES (PASWEB)
This client uses the common Software Sales (PasWeb) Master Issuer and accepts only its own product licence. Keep the separate MASTER_ISSUER_PRIVATE.html file private and offline; do not upload it to GitHub or include it in a client distribution. Copy the exact device ID shown in this app into the issuer, select this app, issue a key, then paste the key into this app.
