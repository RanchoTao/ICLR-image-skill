# Typography, Layout, and Color

## Typography

Prefer one manuscript-consistent font family.

Suggested scale for two-column ML papers:
- panel label/title: 8–9 pt bold or semibold;
- axis labels: 7–8 pt;
- tick labels: 6.5–7.5 pt;
- annotations: ~7 pt.

Avoid:
- giant figure-level marketing headlines;
- long subtitles;
- explanatory paragraphs inside panels.

Use short panel titles.

Good:
- “(a) Layerwise response”
- “(b) Early versus final”
- “(c) Reuse regret”

Less suitable:
- “A replicated increase demonstrates a remarkable temporal reorganization…”

Put the full claim in the caption or main text.

## Layout

Prefer strict grids and aligned geometry.

Good structures:
- 2×2;
- 2×3;
- one large panel + two supporting panels;
- overview row + dense evidence row.

Align:
- panel title baselines;
- axis boxes;
- plot widths/heights;
- colorbars;
- row/column spacing.

Avoid “widget” composition where every panel has a different visual weight.

### Whitespace

Use enough whitespace to separate logical groups, but not so much that empirical panels feel sparse.

The dominant canvas area should contain data, not prose.

## Color

A stable global semantic language helps.

Suggested default:
- blue: early / baseline / focal group A;
- orange: late / contrast / focal group B;
- gray: background runs / secondary observations;
- sequential colormap: response magnitude;
- diverging colormap: signed change / correlation when needed.

Do not add extra hues merely to increase visual richness.

Use color to encode:
- magnitude;
- category;
- comparison role;
- sign.

Do not encode the same identity redundantly with axis position + unique color unless needed.

## Lines and markers

Use:
- thin/light lines for individual runs;
- thicker/darker line for aggregate;
- open vs filled markers for secondary categorical distinctions;
- dashed identity/reference line where meaningful.

Avoid extremely thick strokes or oversized markers.

## Heatmaps

- shared color scale for comparable panels;
- one colorbar per logical group, not one per mini-panel;
- meaningful ordering of rows/columns;
- direct labels when the matrix is small enough;
- no decorative cell borders unless they aid reading.

## Small multiples

Use common:
- axis units;
- scales;
- ordering;
- title format;
- aspect ratio.

The point is comparison, so geometric consistency matters more than individual panel decoration.

## Paper-size QA

Inspect at:
1. full-size export;
2. intended two-column width;
3. grayscale;
4. PDF/vector render.

If text requires zooming in the PDF, simplify layout rather than shrinking type indefinitely.
