# Strip EXIF — PWA

Remove EXIF metadata from photos and export as clean JPG or merged PDF.
Works on iPhone, iPad, Mac, Android — any modern browser.

## Deploy to GitHub Pages (free)

1. Go to github.com → sign in → click **New repository**
2. Name it `exif-stripper` → set to **Public** → click **Create repository**
3. Upload these files: `index.html`, `sw.js`, `manifest.json`, `icon.png`
   - Click **Add file** → **Upload files** → drag all four in → **Commit changes**
4. Go to **Settings** → **Pages** → Source: **Deploy from a branch** → Branch: **main** → **Save**
5. Wait ~60 seconds → your app is live at:
   `https://YOUR-USERNAME.github.io/exif-stripper/`

## Add to iPhone home screen

1. Open the URL in Safari
2. Tap the **Share** button (box with arrow)
3. Tap **Add to Home Screen**
4. Tap **Add**

The app now works offline and feels native.

## How EXIF stripping works

The browser draws each photo onto an HTML Canvas and re-exports it as JPEG.
This process drops all metadata — GPS, camera model, timestamp, lens info, etc.
Only pixel data survives. No data ever leaves your device.

## Files

| File | Purpose |
|---|---|
| `index.html` | Entire app |
| `sw.js` | Service worker (offline support) |
| `manifest.json` | PWA install metadata |
| `icon.png` | Home screen icon (add your own 512×512 PNG) |
