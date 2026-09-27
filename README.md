# vinted-label-print

A single-page, offline-first tool for printing Vinted (or other carrier)
shipping labels four-to-a-sheet on A4 label paper (e.g. Avery L7169,
99.1 x 139 mm).

Open `index.html` in a browser — no build step, no server, no dependencies
beyond the CDN-hosted [pdf.js](https://mozilla.github.io/pdf.js/) and
[pdf-lib](https://pdf-lib.js.org/) libraries it loads at runtime. Labels
never leave the browser; nothing is uploaded anywhere.

## What it does

1. Drop in one or more label PDFs, PNGs or JPGs.
2. Each label is automatically cropped to just its printed area. For
   labels that print a solid-bordered box around the address/barcode
   inside a larger dashed cut-line (common with Evri/Vinted labels), the
   crop specifically detects that solid box and ignores the dashed line,
   any "how to send your parcel" instructions column, and any other
   stray content on the page — so the address and barcode print as large
   as possible. Use **Adjust** on a label to redraw the crop by hand if
   the automatic detection guesses wrong.
3. Pick your label paper size (a couple of common presets, or enter your
   own sizes/margins/nudge offsets — these are remembered per device).
4. Choose which of the four spots on the current sheet are free vs.
   already used, so a partially-used sheet can go back through the
   printer.
5. Download a print-ready PDF. Print at 100% / actual size (not "fit to
   page").

## iPhone: send a label straight from the Share Sheet

See the app for the current hosted link. A Shortcuts recipe for sending
a Vinted label PDF straight to this tool from iOS's Share Sheet:

1. In Shortcuts, create a new shortcut with:
   - **Save File** — input: Shortcut Input, destination a fixed folder
     (e.g. `Parcel Labels/`), "Ask Where to Save" off, overwrite on.
   - **Open URLs** — the hosted URL of `index.html`.
2. In the shortcut's settings, turn on **Show in Share Sheet**, set
   **Share Sheet Types** to PDFs (and Images), and turn off **Ask
   Before Running**.
3. From the Share Sheet on a label PDF, tap the shortcut. It saves the
   file and opens the app; tap "tap to choose" then **Browse** — the
   PDF is at the top of **Recents**.

(A website can't register itself as a Share Sheet target on iOS, so this
two-step hand-off — save, then open — is as close to one-tap as the
platform allows.)
