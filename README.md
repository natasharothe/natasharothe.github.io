# Tashi Tash

Personal creative portfolio and journal for music, movement, travel, and visual notes.

## Live site

[tashitash.com](https://tashitash.com)

## Overview

This repository contains the source for the Tashi Tash website, published via GitHub Pages with a custom domain.

The site is intentionally lightweight and framework-free. It is built with HTML, CSS, and vanilla JavaScript in a single `index.html`, with web fonts and privacy-conscious analytics as the only third-party services.

The page has five sections: Listen, Reel, Blue Series, Journal, and About.

## Features

- Responsive editorial layout
- Custom tracklist player: one row per song with cover, play button, seekable waveform, and running time
- Waveforms drawn from the measured loudness of each track, redrawn to fit the available width
- Continuous playback: one track at a time, rolling on to the next when a song ends
- Media Session support, so the lock screen, control centre, AirPods, and car controls show title, artist, and cover and can pause, skip, and seek
- Cover and photo lightbox with keyboard navigation
- Custom reel with video playback, navigation, progress indicators, and audio state handling
- Scroll reveal interactions using `IntersectionObserver`
- Reduced-motion support via `prefers-reduced-motion`
- Open Graph tags and JSON-LD structured data for link previews and search
- Custom GitHub Pages domain via `CNAME`
- GoatCounter analytics

## Technology

- HTML5
- CSS3
- Vanilla JavaScript
- Media Session API
- Google Fonts (Archivo, Space Mono)
- GitHub Pages
- GoatCounter

## Project structure

```text
.
├── index.html            # Main website, styles, and client-side interactions
├── CNAME                 # Custom domain configuration
├── README.md             # Repository documentation
├── .gitignore            # Keeps system and local files out of the repository
├── <song>.mp3            # One audio file per track, e.g. nothing-out-loud.mp3
├── <song>-cover.jpg      # Square cover for that track, 1000 × 1000
├── tashi-clip*.mp4       # Reel clips, each with a *-poster.jpg frame
├── *.jpeg                # Blue Series and Journal photos
└── icons and og-image    # Favicons, touch icons, and the link preview image
```

## Adding a track

Each song is one `.player` block in the Listen section of `index.html`. A new track needs:

1. The audio file and a square cover in the repository root, named after the song (`song-name.mp3`, `song-name-cover.jpg`).
2. A copy of an existing `.player` block with the title, file names, and track number changed.
3. The song's length in the time label (`0:00 / 3:37`) and its loudness curve in `data-peaks` (110 values between 0 and 1).

The player picks up every `.player` block on the page automatically, including for skip and lock-screen controls.

## Deployment

The website is deployed from the `main` branch through GitHub Pages and served at the custom domain `tashitash.com`. A push is live about a minute later.

GitHub Pages lets browsers cache files for up to ten minutes. Cover images therefore carry a version tag in `index.html` (`cover.jpg?v=1117`); raise the number when a cover is replaced under the same file name so visitors get the new image straight away.

## Development notes

The current implementation deliberately keeps the project dependency-free. No build step or package manager is required for the website itself.

All tracks play through a single audio element whose source changes from song to song. This is what allows skipping and auto-advance to keep working on a locked phone, where browsers refuse to start a different audio element in the background.

A `.gitignore` keeps system files and local environment files from being committed by accident. It has no effect on the published site.
