# RollShelf

## Overview
RollShelf is a single-file thumbnail file explorer that works with local web servers and public GitHub repositories.

## Quick Start
https://covao.github.io/RollPDF/RollShelf.html

Open with a local directory:
```
https://covao.github.io/RollShelf/RollShelf.html
```

Open a GitHub repository:
```
https://covao.github.io/RollShelf/RollShelf.html?url=https://github.com/owner/repo
https://covao.github.io/RollShelf/RollShelf.html?url=https://github.com/owner/repo/tree/branch/path
```

Open a local or intranet server (place `RollShelf.html` on the same server):
```
http://localhost:8080/RollShelf.html?url=http://localhost:8080/files/
http://192.168.1.10/RollShelf.html?url=http://192.168.1.10/media/
```

## Features
- **Single HTML file** — no installation, no dependencies, runs entirely in the browser
- **GitHub mode** — browse any public GitHub repository by passing a `?url=` parameter
- **Local / intranet mode** — browse directories served by Apache or Nginx (place `RollShelf.html` on the same origin)
- **Thumbnail generation** — automatically generates and caches thumbnails for images (PNG, JPG, GIF, WEBP, AVIF, BMP) and PDFs via PDF.js
- **Thumbnail cache** — thumbnails are persisted in IndexedDB and re-used across sessions
- **Sortable** — toggle between name order (A→Z) and reverse-name order; date sort when directory listings include timestamps
- **Zoom** — adjust thumbnail size with zoom in / zoom out buttons; current scale shown as a percentage
- **Scroll modes** — switch between horizontal and vertical grid scrolling
- **Filter / search** — filter files by name in real-time
- **Go up** — navigate to the parent directory with one tap
- **URL sync** — the browser address bar updates on every navigation, enabling bookmarks and back-button support
- **Folder tree sidebar** — collapsible tree for quick folder navigation on local servers
- **Scrollable toolbar** — swipe or drag the toolbar horizontally to reveal all icons on narrow screens
- **Mobile friendly** — touch-optimized with native pan gesture support on the toolbar
- **Custom viewer** — open files in a user-defined viewer URL (configurable via the ⚙ settings)
- **Fullscreen** — one-tap fullscreen toggle

## Requirements
- A modern web browser (Chrome, Edge, Firefox, Safari)
- For local / intranet mode: a web server (Apache, Nginx, etc.) with directory listing enabled, hosting `RollShelf.html` at the same origin as the files

## Usage

### Browse a GitHub repository
Append `?url=` with the GitHub URL of any public repository or subfolder:
```
RollShelf.html?url=https://github.com/covao/RollShelf
RollShelf.html?url=https://github.com/owner/repo/tree/main/docs
```
RollShelf calls the GitHub Contents API to list files and fetches raw file content for thumbnail generation. No authentication is required for public repositories (unauthenticated limit: 60 requests/hour).

### Browse a local or intranet server
Place `RollShelf.html` in the document root (or any directory) of your web server, then open it with a `?url=` pointing to the target directory on the **same origin**:
```
http://localhost:8080/RollShelf.html?url=http://localhost:8080/media/
```
The server must return an HTML directory listing (standard Apache/Nginx autoindex). No server-side code is required.

### Toolbar navigation
- **↑** — go up to the parent folder
- **−  %  +** — zoom thumbnails out / in; percentage label shows current scale
- **Sort** — toggle name order ↔ reverse-name (or date when available)
- **⇄ / ↕** — switch between horizontal and vertical scroll
- **⛶** — toggle fullscreen
- **⚙** — open settings (viewer URL)
- **Search box** — type to filter visible items by file name

Swipe or click-drag the toolbar area to scroll horizontally and reveal hidden buttons on small screens.
