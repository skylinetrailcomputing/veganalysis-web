# Veganalysis brand assets

Single source of truth for non-app brand iconography (issue #134):
favicons, web-manifest icons, social/OG image, wordmark + lockup.

**Do not hand-edit these files.** They are generated. Regenerate from
the `veganalysis` repo:

```sh
# from the veganalysis repo root (sibling checkout):
uv run scripts/generate-brand-assets.py
# writes here by default (../veganalysis-web/assets/brand)
```

The generator (`veganalysis/scripts/generate-brand-assets.py`) ports
the **same parametric geometry** as the app icon
(`veganalysis/scripts/generate-app-icon.py`, #108 v3). Keeping the
two generators adjacent in one repo is deliberate — the web mark
can't silently drift from the shipped App Store icon.

## Inventory

| File | Use |
|---|---|
| `full-mark.svg` / `full-mark-bg.svg` | full #108 composition (transparent / off-white) |
| `simple-mark.svg`, `favicon.svg` | bold ring + leaf, legible < 64px |
| `wordmark.svg` | "Veganalysis", outlined glyphs |
| `lockup.svg` | mark + wordmark, horizontal — landing header, README banners, mail sigs |
| `favicon-16/32/48.png`, `favicon.ico` | classic favicons (simple mark) |
| `apple-touch-icon-180.png` | iOS home-screen |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | web manifest |
| `og-image.png` (1200×630) | Open Graph / Twitter card |
| `lockup.png` | raster header fallback |

SVG masters are authoritative. PNG/ICO are Pillow-rendered to exact
pixel sizes (no SVG→PNG rasterizer dependency). The wordmark is a
flattened outline of Montserrat SemiBold (SIL OFL, vendored at
`veganalysis/scripts/fonts/`); **no font ships at runtime / no CDN**.

## Conventions

- `/favicon.ico` at the **web repo root** is a committed copy of
  `favicon.ico` here, so the browser's legacy bare `/favicon.ico`
  request never 404s. Refresh both when the mark changes:
  `cp assets/brand/favicon.ico favicon.ico`.
- Wiring lives in `index.html` (`<link rel="icon">` set,
  `apple-touch-icon`, `site.webmanifest`, OG/Twitter meta) and
  `site.webmanifest`.
- Palette is ported verbatim from the app icon: leaf `#66BB6A`,
  forest `#1B5E20`, off-white `#F5F8F3`, lens tint `#E8F5E9`.
