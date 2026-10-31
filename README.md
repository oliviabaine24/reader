# Focus Reader

A private RSVP PDF speed reader with a fixed red focal letter and a jump-to-chapter table of contents. It runs entirely in the browser, so it can be hosted for free on GitHub Pages.

## Publish on GitHub Pages

1. Create a new repository on GitHub (e.g. `focus-reader`).
2. Upload `index.html` and `README.md` to the repository root (Add file → Upload files → Commit).
3. Go to **Settings → Pages**. Under **Build and deployment**, set Source to **Deploy from a branch**, choose `main` and `/ (root)`, then **Save**.
4. After a minute or two, your reader is live at `https://<your-username>.github.io/<repo-name>/`.

To update the site later, upload a new `index.html` and commit; Pages redeploys automatically.

## Run locally

Open `index.html` directly in a browser, or for the most reliable PDF loading run `python3 -m http.server 8000` in this folder and visit `http://localhost:8000`.

## Privacy

PDFs are read inside the visitor's browser with [pdf.js](https://mozilla.github.io/pdf.js/) and are never uploaded anywhere — not to GitHub, not to any server. The page only downloads the pdf.js library itself from cdnjs.

## Features

- Drag-and-drop PDF extraction, or paste text
- 100–1000 words/minute
- Centered focal letter, aligned to the same horizontal position
- Natural punctuation pauses (optional)
- **Contents panel** to jump to chapters and headings, with the current section highlighted and shown under the reader
  - Uses the PDF's own bookmarks when it has them
  - Otherwise detects headings from larger font sizes, then from patterns like "Chapter 3", "2.1 Methods", or ALL-CAPS titles
  - Pasted text supports Markdown `#` headings
- Words hyphenated across line breaks are rejoined
- Keyboard: Space play/pause · ← / → skip a word · [ / ] previous/next section · T open contents · Esc close
- Progress and estimated reading time
- Original text panel

## Limitations

Image-only scans need OCR (not included). Complex columns, tables, citations, formulas and headers may extract out of order. Detected headings (when a PDF has no bookmarks) may include a few extras or miss some. For academic documents, check the original text when context or exact wording matters.
