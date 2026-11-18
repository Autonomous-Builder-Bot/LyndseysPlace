# Lyndsey's Place — Interactive Room Planner

An interactive, mobile-friendly 2D / 3D floor planner built with Three.js. No build step, npm installation, login, or backend required.

## Features
- Touch / mouse drag to reposition furniture; rotate in 1° increments or with 15° buttons.
- 2D overhead plan and orbitable 3D room views; pan, orbit, pinch to zoom.
- Eight furniture footprints using supplied handwritten dimensions (inches).
- Editable room measurements and 90-degree corners using the Project 3 AR measurement as a starting point.
- Floor grid, wall visibility, snapping, overlap/out-of-room warnings, undo and redo.
- Automatically saves to this browser's `localStorage`.
- Export/import a JSON layout, download a picture, or share a link containing the entire layout (in the URL fragment) to another phone.

## Run
Open `index.html` through a local web server (e.g. `python -m http.server 8000`) or enable GitHub Pages at **Settings → Pages → Deploy from a branch → main / root**. Visit `https://autonomous-builder-bot.github.io/LyndseysPlace/` after Pages has deployed.

The page requires an internet connection to load Three.js from jsDelivr. No other dependencies are hosted externally.

## Measured furniture footprints

| Item | Width × Depth (inches) |
| --- | --- |
| Bed | 82 × 60 |
| TV stand | 58 × 15.5 |
| Couch | 67 × 40 |
| Bedside table | 15.5 × 12 |
| Long table | 35.5 × 13 |
| Glass table | 32 × 32 |
| Metal table | 48 × 27.5 (handwriting ambiguous; verify) |
| Cat stand | 19.5 × 19.5 |

## Room notes

The model represents **one room**, not a complete house. Shape is derived from Project 3, with all walls orthogonal as requested. Top wall is ~196.25 in; upper-right wall is ~71.375 in; lower-right wall ~141.125 in; bottom-right wall ~148.75 in. Small offsets and the unusual upper-left shape are visually estimated and editable. The room works out to approximately **323 sq ft** in this draft. All object heights and finishes, wall height (8 ft), door/window locations, and initial furniture arrangement are illustrative or unknown.

The room origin (0, 0) is the **left end of the main top wall**. Position X is inches to the right and position Y inches down. Room shape controls are in the Edit & Room panel with no furniture selected. Changes persist locally and can be shared via URL.

## Important limitations
- Phone-based AR room measurements disagreed substantially in early scans. Confirm critical wall and recess lengths with a tape measure before relying on exact fit.
- Doorways and windows are not included because their locations and sizes were not provided.
- Furniture models are stylized approximations. Collision warnings assess 2D footprints; they do not prevent placement.
- Layout links include positions and dimensions in the URL, not in any database. Anyone with the link can see the arrangement.