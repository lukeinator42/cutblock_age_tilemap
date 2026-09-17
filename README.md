# Cutblock-age XYZ tile layers — WMU 356 / 354 / 353

Two species-tuned versions of the same underlying cutblock data (ABMI HFI 2023
v1.1), covering the full boundaries of WMU 356/354/353 (Cutbank/Deep
Valley/Simonette), not just a small camp AOI. Both: 25,638 tiles, 256x256 PNG,
EPSG:3857 (Google/XYZ numbering), zoom 9-15, ~43MB each.

## elk/ — elk forage-value coloring

| Age | Color |
|---|---|
| 0-3 yr | pale yellow |
| 4-6 yr | light green |
| 7-25 yr (peak forage) | dark green |
| 26-35 yr | brown |
| 36+ yr / unknown | dark brown |

Elk graze regenerating grasses/forbs, which peak later and last longer than
woody browse.

## moose/ — moose forage-value coloring

| Age | Color |
|---|---|
| 0-1 yr | pale blue |
| 2-4 yr | light blue |
| 5-15 yr (peak browse) | blue-purple |
| 16-25 yr | purple |
| 26+ yr / unknown | dark purple |

Moose browse woody shrub regrowth (willow/aspen/birch), which is available
sooner and gets shaded out / grows out of reach sooner than elk's grass/forb
forage -- the whole palette is deliberately blue/purple, not a re-tinted
green, so it's never ambiguous with the elk layer if both are loaded in the
same app at once.

## Hosting: GitHub Pages

Enable Pages on this repo (Settings -> Pages -> Deploy from a branch -> root).
Tile URLs:

- Elk: `https://<your-username>.github.io/<repo-name>/elk/{z}/{x}/{y}.png`
- Moose: `https://<your-username>.github.io/<repo-name>/moose/{z}/{x}/{y}.png`

Add each as its own Base Map entry in iHunter (Map Type = XYZ, Max Zoom = 15)
so you can toggle between them independently.

**Test offline persistence before relying on either in the field**: while on
WiFi/cell, open the layer, pan/zoom across your hunt area, then switch to
Airplane Mode and confirm tiles still render. Unverified whether iHunter
caches custom XYZ tiles for offline use.

## Data note

Cutblocks were clipped to the *actual* WMU polygon boundaries (not just their
bounding box). Source: ABMI HFI 2023 v1.1,
`o18_TimberHarvest_and_WoodyVegetationRemoval_HFI_2023` layer, read directly
from the province-wide geodatabase.
