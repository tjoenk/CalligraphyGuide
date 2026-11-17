# Calligraphy Guide Sheet

A small single-page tool for making ruled A4 guide sheets for calligraphy practice. Print the sheet, put it on a light box under your paper, and use the lines to keep letter heights and slant even.

Everything runs in one HTML file. It works offline, has no dependencies and needs no install, and the PDF is generated directly in your browser.

<img width="1100" height="760" alt="screenshot" src="https://github.com/user-attachments/assets/e19a753f-bd84-4ac9-b7ba-6286b7505a10" />

## Features

- **Alternating line spacing.** Lines alternate between two gaps (2 mm / 4 mm by default), so you get x-height bands with ascender/descender space between them.
- **Optional slanted lines.** Set any angle (measured from horizontal, 90° = vertical, above 90° leans left) and the spacing between lines.
- **Line style.** Set thickness and colour separately for the horizontal and slanted lines.
- **Page setup.** Choose A4 portrait or landscape, with adjustable margins.
- **Live preview.** The page updates as you change settings.
- **Vector PDF output.** Lines stay crisp at any print resolution.
- **Open after saving.** Optionally opens the PDF in a new tab so you can print it right away.
- **Settings note.** An optional small line in the bottom margin records which settings the sheet was made with.
- **Remembers your settings** between visits (stored locally in your browser).

## Usage

1. Download `calligraphy_guide.html`, or clone the repository.
2. Open the file in any modern browser (Chrome, Edge, Firefox, Safari).
3. Adjust the settings and click **Save PDF**.
4. Print the PDF at **100 % / "Actual size"**.

> ⚠️ **Turn off "Fit to page" when printing.** Scaling the page changes the line spacing. On your first print, measure a few lines with a ruler to check.

If the PDF doesn't open in a new tab after saving, your browser is probably blocking pop-ups for local files. Allow pop-ups, or open the downloaded file yourself.

## Settings

| Setting | Default | Notes |
|---|---|---|
| Page size | A4 portrait | A4 portrait or landscape |
| Margins | 15 mm | Top, bottom, left, right |
| Gap 1 / Gap 2 | 2 mm / 4 mm | The spacing alternates between these two |
| Line thickness | 0.2 mm | Use 0.3–0.4 mm for thicker paper |
| Line colour | Black | |
| Slanted lines | Off | |
| Slant angle | 55° | From horizontal. 90° = vertical |
| Slant spacing | 10 mm | Horizontal distance between slanted lines |
| Slant thickness | 0.15 mm | |
| Slant colour | Grey | A lighter colour keeps the horizontal lines dominant |

### Typical slant angles

| Style | Angle |
|---|---|
| Copperplate / Engrosser's script | ~55° |
| Spencerian | ~52° |
| Italic | ~83–85° (5–7° from vertical) |
| Upright hands (Foundational, Uncial) | 90° or slant off |

## Tips for light box use

- Black lines at 0.2 mm show through most practice papers. For heavier stock, raise the thickness.
- A grey slant colour helps you tell the slant guides from the writing lines at a glance.
- Tape the guide sheet to the light box so it doesn't shift under your paper.

## How it works

The PDF is written by hand in plain JavaScript (a minimal PDF 1.4 file with vector line paths and the built-in Helvetica font), so it doesn't need any library. Slanted lines are clipped mathematically to the ruled area with the Liang–Barsky algorithm. The same geometry drives both the on-screen SVG preview and the PDF, so what you see is what you print.
