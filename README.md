# Clean Files

A small browser app for removing hidden metadata from images and documents before sharing.

## What it handles

- Photos/images: redraws the image through canvas to remove EXIF/GPS/device metadata.
- Videos: two methods, see below.
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

## Video

Two methods are offered when a video is added.

**Keep original** (default) rewrites the container in place. Every metadata box is
renamed to a padding box and its contents zeroed, so GPS coordinates, camera make
and model, lens, software, creation dates and titles are gone while the audio and
video streams are byte-for-byte identical. No quality loss, no waiting, same file
size. Works with MP4, M4V, MOV, WebM and MKV.

**Re-encode** decodes the video and records a fresh one through MediaRecorder, so
the output carries no metadata at all. This is the option to use when the file
needs to be smaller or in a different format:

- Format: MP4 (H.264) or WebM (VP9/VP8), whichever the browser supports. Safari
  produces MP4, Chrome and Firefox usually produce WebM.
- Resolution: original, 1080p, 720p, 480p or 360p.
- Target size: same size, 75%, 50%, 25%, or an exact figure in MB. The bitrate is
  calculated from the video's duration to hit that target.

Re-encoding runs in real time, so a three minute clip takes about three minutes,
and the tab must stay in the foreground. Audio is preserved.

Containers other than MP4 and WebM (AVI, WMV, FLV, MPEG and so on) cannot be
rewritten in place, so they fall back to re-encoding, and they only work at all if
the browser can decode them.
