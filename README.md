# Cutblock-age XYZ tile layer for iHunter

1,672 transparent PNG tiles (256x256, EPSG:3857, standard Google/XYZ numbering,
zoom 9-15), colored by cutblock age:

| Age | Color |
|---|---|
| 0-3 yr | pale yellow |
| 4-6 yr | light green |
| 7-25 yr (peak forage) | dark green |
| 26-35 yr | brown |
| 36+ yr / unknown | dark brown |

## 1. Host these files somewhere with a stable URL

These are plain static files — any static host works. Easiest free options:

- **GitHub Pages**: create a repo, push this whole `cutblock_age_tiles` folder to it,
  enable Pages in the repo settings. Your tile URL becomes
  `https://<username>.github.io/<repo>/{z}/{x}/{y}.png`
- **Cloudflare Pages** / **Netlify**: drag-and-drop deploy, similar result.

I can't provision hosting myself (no cloud account access from here) — this part
needs to be done from your own account.

## 2. Add it in iHunter

From the "Add a Base Map" screen:
- **Map Type**: XYZ
- **Server URL**: `https://<your-host>/{z}/{x}/{y}.png`
- **Max Zoom Level**: 15 (tiles don't exist past that — set lower than 17)

## 3. Offline caching — test this before the trip

This is a live tile server: iHunter fetches each tile over the internet the first
time it's viewed. Whether it then caches those tiles for offline use once you
lose signal is **not something I've verified**. Before relying on this in the
field:

1. While still on WiFi/cell, open iHunter with this layer on and pan/zoom across
   your whole hunt area at the zoom levels you'll actually use.
2. Turn on Airplane Mode and confirm the tiles still render.

If they don't persist offline, this layer is only useful with signal, and the
GPX/KML files (or the QField package) remain the reliable offline option.
