# Jaway Construction Services Inc.

Static marketing site for Jaway Construction Services Inc. — a single-file, self-contained HTML bundle plus project photos.

**Live site:** _will appear at_ `https://<your-username>.github.io/jaway-construction-site/` _once GitHub Pages is enabled._

## How to view locally

Double-click `index.html`. Keep it in the same folder as the `images/` directory — the page loads project photos from there.

## Folder layout

```
jaway-construction-site/
├── index.html        ← open this
├── README.md         ← this file
├── .nojekyll         ← tells GitHub Pages to serve files as-is
└── images/
    ├── 1.png         → Infrastructure (Selected work gallery)
    ├── 2.png         → Commercial      (Selected work gallery)
    ├── 3.png         → Residential     (Selected work gallery)
    └── 4.png         → Ground Up / Permitting to Handover (About section)
```

## Photo mapping

### About section (Ground up / Permitting to handover)

| Element        | Source        | Behavior                                              |
| -------------- | ------------- | ----------------------------------------------------- |
| Hero photo     | `images/4.png`| Gentle zoom on hover, clipped to the 520 px frame.    |
| Black badge    | _(inline)_    | Centered below the photo; lifts on hover.             |

### Selected work gallery

| Tile           | Source        | Caption                       |
| -------------- | ------------- | ----------------------------- |
| Residential    | `images/3.png`| RESIDENTIAL — Custom home build  |
| Commercial     | `images/2.png`| COMMERCIAL — Retail & fit-out    |
| Infrastructure | `images/1.png`| INFRASTRUCTURE — Public works    |

A dark linear gradient sits over the bottom 55% of each tile so the white captions stay readable on bright photos.

## Contact section

The contact panel surfaces all the ways to reach the business:

- **Phones:** 306-614-9579 / 306-614-0300
- **Facebook:** [Jaway Construction Services Inc.](https://www.facebook.com/p/Jaway-Construction-Services-Inc-61569589214465/)
- **Instagram:** _coming soon_
- **Viber / WhatsApp:** wired to the primary phone line via `viber://` and `wa.me/` URL schemes
- **Email:** `jawayconstructionservices@gmail.com`
- **Address:** Preeceville, SK, Canada – S0A 3B0

## Swapping a photo

Replace the matching file inside `images/`, keeping the same filename. No HTML edits required. For example, drop a new commercial shot in as `images/2.png` to change the Commercial tile.

## How the page is built

`index.html` is a single, self-contained "offline bundle" — the page markup, all CSS, and a base64-encoded image manifest are embedded in one file. On load, an in-page loader decodes the manifest into blob URLs and swaps in the real document. A small block of custom JavaScript at the top of the loader is where this project's customizations live: it injects the four project photos into the right slots, repositions the "Ground up / Permitting to handover" badge, adds hover animations, and recolors the footer logo (black house → white, red hammers preserved) via an inline SVG `feColorMatrix` filter.

## GitHub Pages

The `.nojekyll` file disables Jekyll processing so the `images/` directory is served verbatim. To enable hosting, go to **Settings → Pages**, set the source to **Deploy from a branch**, branch **main**, folder **/(root)**, then save.
