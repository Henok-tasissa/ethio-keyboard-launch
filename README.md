# Ethio Amharic Keyboard: launch site

Product launch site for **Ethio Amharic Keyboard** on iPhone/iPad and Mac: promo, screenshots, install guide and FAQ.
Plain static HTML/CSS (no build step). Live at **https://ethio-keyboard-launch.vercel.app** (Vercel, auto-deploys on every push to `main`).

| Page | File |
|---|---|
| Home (both platforms) | `index.html` |
| iPhone & iPad | `iphone.html` |
| Mac (download, Tab feature, screenshots) | `mac.html` |
| Install and use guide (Mac + iPhone/iPad) | `guide.html` |
| FAQ | `faq.html` |

Images are in `img/`: `ios-*.jpg` come from the iOS repo's App Store screenshots; `mac-*.jpg` are rendered from the Mac app's own views
(`OUT_DIR=… swift test --filter ScreenshotRenderTests` in the Mac repo), then converted with `sips -s format jpeg -s formatOptions 82 -Z 2000`.

## Deploy (Vercel)
Import this repo at vercel.com/new. Framework preset **Other**, no build command, output directory `.` (repo root). `vercel.json` enables clean URLs.

## Mac download
The button points to the latest GitHub Release asset `Ethio-Amharic-Keyboard.dmg` in this repo. To publish a new version:
```
gh release create vX.Y.Z "/path/Ethio-Amharic-Keyboard-X.Y.Z.dmg#Ethio-Amharic-Keyboard.dmg" --repo Henok-tasissa/ethio-keyboard-launch --title "vX.Y.Z" --notes "..."
```
then update the version text on `mac.html`.

## When the iPhone/iPad app goes live
Replace the "Coming soon" badges and "Notify me" buttons (search for `NOTIFY`-style `mailto:` links and `Coming soon`) in `index.html`, `iphone.html`, `guide.html` and `faq.html` with the App Store link
`https://apps.apple.com/app/id6821792798`.
