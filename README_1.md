# Focus Reader

A private RSVP speed reader for PDFs, EPUBs and pasted text, with a fixed red focal letter, a jump-to-chapter table of contents, and a Settings panel to switch every feature on or off. It runs entirely in the browser and is hosted on GitHub Pages.

## Publish on GitHub Pages

1. Upload **all** of these files to the root of your repository:
   `index.html`, `sw.js`, `manifest.webmanifest`, `icon.svg`, `icon-192.png`, `icon-512.png`, `icon-512-maskable.png`, `apple-touch-icon.png`, `README.md`
2. **Settings → Pages** → Source: **Deploy from a branch** → `main` / `(root)` → **Save**.
3. After a minute or two it's live at `https://<your-username>.github.io/<repo-name>/`.

`server.py` is no longer needed and can be deleted.

**Updating later:** upload the new files, then bump `VERSION` in `sw.js` (e.g. `focus-reader-v3` → `focus-reader-v4`) so installed copies pick up the change. Hard-refresh (Cmd/Ctrl+Shift+R) if you still see the old version.

## Run locally

`python3 -m http.server 8000` in this folder, then open `http://localhost:8000`.

## Privacy

Files are read inside the browser with [pdf.js](https://mozilla.github.io/pdf.js/) and [JSZip](https://stuk.github.io/jszip/) and are never uploaded anywhere. Reading positions, bookmarks, settings and stats are stored only in that browser's local storage. The page downloads only the two libraries from cdnjs.

## Features

Everything below can be turned on or off under **⚙ Settings**.

**Reading pace**
- Natural pauses at commas and sentence ends
- Smarter timing: longer holds for long words and numbers, pauses at paragraph breaks and before new sections
- Speed ramp-up: starts ~30% slower and reaches full speed over 3 seconds
- 1, 2 or 3 words at a time (chunks never cross a sentence, clause or paragraph)

**When you pause**
- Rewind on pause: back 5 words or to the start of the sentence
- Show the full sentence under the reader; click any word to jump there

**Display**
- Light, dark or match-system theme; adjustable word size
- Text panel: click any word to jump there; optionally highlights and follows the current word

**Clean up the text**
- Skip page numbers and running headers/footers
- Skip the References/Bibliography section
- Remove in-text citations like (Smith et al., 2019) and [12]

**Navigation & tracking**
- Contents panel from PDF bookmarks, EPUB table of contents, or detected headings
- Remember my place: reopen the same file to resume
- Bookmarks (B), listed under Marks and exportable as a text file
- Section range: read only "Chapter 3 → Chapter 5", with playback stopping at the end
- Time left in the current section
- Reading stats: words read and average speed today and over the last 7 days

**App**
- Works offline and can be installed (Install app button in Settings; on iPhone/iPad use Share → Add to Home Screen)
- EPUB support (DRM-protected books can't be read)

## Keyboard

Space play/pause · ← → one word · Shift+← → ten words · [ ] previous/next section · B bookmark · M marks · T contents · S settings · Esc close panel

## Limitations

Image-only scans need OCR (not included). Complex columns, tables, formulas and figure captions may extract out of order. Heading detection for PDFs without bookmarks and citation removal are heuristics and can occasionally miss or over-match, which is why they can be switched off.
