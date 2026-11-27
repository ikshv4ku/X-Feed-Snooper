# X-Feed-Snooper

A Chrome extension (Manifest V3) built in 2025 as a learning project with GDSC IIT Roorkee, to explore how browser sessions work. It saves your own x.com session cookies, swaps in a session from a saved profile to view that feed with a read-only overlay, and then restores your original session exactly.

It is the browser half of a two-part project; the Flask backend lives in [VisionX-backend](https://github.com/ikshv4ku/VisionX-backend).

## What it demonstrates

- The `chrome.cookies` API: reading, removing and re-setting cookies across domain and path variants
- Saving and restoring session state with `chrome.storage.local`
- A content script that injects a read-only overlay on x.com
- A popup UI that manages saved profiles

## Important: use only with accounts you own

Session cookies are equivalent to a logged-in password. Anyone holding them has full access to the account, and sharing them may break X's Terms of Service. Use this only with your own test accounts. It is published for learning, not for accessing anyone else's account.

## Run it locally

1. Open `chrome://extensions` and turn on **Developer mode**.
2. Click **Load unpacked** and choose this folder.
3. Open x.com and click the extension icon.

## Files

| File | Role |
|---|---|
| `manifest.json` | MV3 manifest: permissions and host permissions for x.com |
| `popup.html`, `popup.js`, `styles.css` | Profile manager, session swap and restore |
| `content.js` | Read-only overlay on x.com |
| `background.js` | Service worker that answers cookie queries |
