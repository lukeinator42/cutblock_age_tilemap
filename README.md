# Cutblock-age XYZ tile layer — WMU 356 / 354 / 353 (Cutbank / Deep Valley / Simonette)

25,638 transparent PNG tiles (256x256, EPSG:3857, standard Google/XYZ numbering,
zoom 9-15), covering the full boundaries of these three WMUs (~204 x 148 km),
not just the original small camp AOI. 42.9 MB total.

Same age/color scheme as before:

| Age | Color |
|---|---|
| 0-3 yr | pale yellow |
| 4-6 yr | light green |
| 7-25 yr (peak forage) | dark green |
| 26-35 yr | brown |
| 36+ yr / unknown | dark brown |

## Hosting + iHunter setup

Same as the camp-AOI version:
1. Push this folder to a GitHub repo, enable **Pages** (Settings -> Pages ->
   Deploy from a branch -> root).
2. In iHunter's "Add a Base Map": Map Type = XYZ, Server URL =
   `https://<your-username>.github.io/<repo-name>/{z}/{x}/{y}.png` (check
   whether the numbered folders landed at the repo root or one level deeper,
   same as before), Max Zoom = 15.
3. **Test offline persistence before the trip** (WiFi on, pan/zoom the whole
   area, then Airplane Mode) -- unverified whether iHunter caches custom XYZ
   tiles for offline use.

## Data note

Cutblocks were clipped to the *actual* WMU polygon boundaries (not just their
bounding box), so cutblocks from neighbouring WMUs that happen to fall inside
the bbox aren't included. Source: ABMI HFI 2023 v1.1, `o18_TimberHarvest_and_WoodyVegetationRemoval_HFI_2023` layer, read directly from the province-wide
geodatabase (not the camp-AOI-clipped copy used elsewhere in this project).
