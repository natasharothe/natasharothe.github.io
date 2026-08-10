# Tashi Tash

Personal creative portfolio and journal for music, movement, travel, and visual notes.

## Live site

[tashitash.com](https://tashitash.com)

## Overview

This repository contains the source for the Tashi Tash website, published via GitHub Pages with a custom domain.

The site is intentionally lightweight and framework-free. It is built with HTML, CSS, and vanilla JavaScript, with selected third-party integrations for media playback and privacy-conscious analytics.

## Features

- Responsive editorial layout
- Scroll reveal interactions using `IntersectionObserver`
- Reduced-motion support via `prefers-reduced-motion`
- Custom reel with video playback, navigation, progress indicators, and audio state handling
- Photo lightbox with keyboard navigation
- Spotify Embed API integration
- Custom GitHub Pages domain via `CNAME`
- GoatCounter analytics

## Technology

- HTML5
- CSS3
- Vanilla JavaScript
- Spotify Embed API
- GitHub Pages
- GoatCounter

## Project structure

```text
.
├── index.html       # Main website, styles, and client-side interactions
├── CNAME            # Custom domain configuration
├── README.md        # Repository documentation
└── media assets     # Images, video clips, and poster frames used by the site
```

## Deployment

The website is deployed from the `main` branch through GitHub Pages and served at the custom domain `tashitash.com`.

## Development notes

The current implementation deliberately keeps the project dependency-free. No build step or package manager is required for the website itself.

Repository housekeeping files such as `.gitignore`, `.gitattributes`, and `.editorconfig` are included to keep local development and future commits consistent without changing the published site.
