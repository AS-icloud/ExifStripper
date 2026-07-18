# Clean Files

A small browser app for removing hidden metadata from images and documents before sharing.

## What it handles

- Photos/images: redraws the image through canvas to remove EXIF/GPS/device metadata.
- PDFs: clears standard PDF title, author, creator, producer, date and keyword fields.
- Word, Excel and PowerPoint files: clears common Office document properties.
- OpenDocument files: clears common ODF metadata.

## GitHub Pages

This project is ready for GitHub Pages because all app paths are relative:

- `./index.html`
- `./manifest.json`
- `./sw.js`
- `./icon-192.png`
- `./icon-512.png`

Upload all files to the repository root, then enable GitHub Pages from the `main` branch.

## Mac Dock / iPhone Home Screen

Open the full GitHub Pages project URL first, for example:

`https://your-user-name.github.io/your-repository-name/`

Then use Safari:

- Mac: `File` -> `Add to Dock`
- iPhone: Share button -> `Add to Home Screen`

Do not add it from the account root URL.
