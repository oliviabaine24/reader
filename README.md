# reader

A private, localhost RSVP PDF speed reader with a fixed red focal letter.

## Run

1. Install Python 3 and PyMuPDF: `python -m pip install pymupdf`
2. Open a terminal in this folder.
3. Run `python server.py` (on some systems use `python3 server.py`).
4. Open `http://127.0.0.1:8765` in your browser.

Your PDFs are processed locally and are not uploaded to any external service. The server only listens on your own computer (127.0.0.1). Press Ctrl+C in the terminal to stop it.

## Features

- Drag-and-drop PDF extraction
- 100–1000 words/minute
- Centered focal letter, aligned to the same horizontal position
- Natural punctuation pauses (optional)
- Keyboard shortcuts and word skipping
- Progress and estimated reading time
- Original text panel and pasted text support

## Limitations

Image-only scans need OCR (not included). Complex columns, tables, citations, formulas and headers may extract out of order. For academic documents, check the original text when context or exact wording matters.
