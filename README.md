<div align="center">

<img src="assets/logo.png" alt="Leafline logo" width="120" height="120" />

# Leafline — TXT to EPUB Converter

**Turn a plain-text novel into a chapter-organized EPUB, entirely in your browser.**

![Version](https://img.shields.io/badge/version-1.3.5-8EB69B?style=flat-square)
![Privacy](https://img.shields.io/badge/privacy-no%20server%20upload-8EB69B?style=flat-square)
![Output](https://img.shields.io/badge/output-EPUB-DAF1DE?style=flat-square)
![Built with](https://img.shields.io/badge/built%20with-React%20%C2%B7%20Vite%20%C2%B7%20Tailwind-051F20?style=flat-square)

[Live Demo](https://<your-username>.github.io/txt-to-epub-converter/) · [Changelog](CHANGELOG.md) · [Report a Bug](../../issues)

</div>

---

## Overview

Leafline reads a `.txt` novel, finds where the chapters begin, shows you a calm split preview, and then packages everything into a clean `.epub` file you can open in any e-reader.

Your text and cover image are processed locally. Nothing is uploaded to a server while the EPUB is assembled.

## Tools

Leafline is a growing set of separate tools. Each one has its own page, inputs, actions, and processing logic.

| Tool | Status | Address |
| --- | --- | --- |
| **TXT to EPUB** | Available | `#/tools/txt-to-epub` |
| **EPUB to TXT** | Planned | — |


## TXT to EPUB

### Features

- **Smart chapter detection** — recognizes Chinese headings (`第一百二十章`, including Chinese numerals) and English headings (`Chapter 12`).
- **Six detection methods** — Auto, Chinese chapters, English chapters, Separators, Fixed lines, and Manual.
- **Reliability checks** — Auto mode looks for a trustworthy numbered heading sequence before falling back to another strategy.
- **Preview before you commit** — see the chapter count, character count, and where each boundary came from before any book is made.
- **Book details** — set the title, author, and language (Chinese Simplified, Chinese Traditional, English, Japanese, Korean, or Other).
- **Optional cover image** — PNG, JPEG, GIF, or WebP, embedded in the EPUB when provided.
- **Structured EPUB output** — one file per chapter, a table of contents page, EPUB 3 navigation, and an NCX file for older readers.
- **Handles common encodings** — reads UTF-8 first, then falls back to GBK/GB18030 and UTF-16, so older Chinese `.txt` files open correctly.
- **Keeps everything** — text before the first chapter heading is preserved as a "Front matter" section, and a table of contents at the top of the file is not mistaken for the chapters.
- **Private by design** — parsing and EPUB creation run in your browser, with no account and no upload.

### Quick Start

1. Open the app (or `index.html` locally), then choose **TXT to EPUB** on the Home page.
2. Drop your `.txt` novel onto the page, or choose a file from your device.
3. Pick a **detection method** and review the **chapter preview**.
4. Fill in the **book title**, **author**, and **language**, and optionally add a **cover image**.
5. Click create, then download your EPUB.

### Detection Methods

| Method | Best for |
| --- | --- |
| **Auto** | Most files. Tries, in order: Chinese headings → English headings → explicit separator lines → Markdown headings → blank-line structure → fixed lines (last resort only). |
| **Chinese chapters** | Files using headings like `第12章` or `第十二章`. |
| **English chapters** | Files using headings like `Chapter 12: Title`. |
| **Separators** | Files divided by separator lines (`***`, `---`, `===`) or by runs of blank lines. |
| **Fixed lines** | Always splits every set number of lines, even if headings exist. |
| **Manual** | Full control: edit the line numbers where chapters start, beginning from Auto's suggestion. |

If no reliable pattern is found, Leafline tells you why and shows a fallback split, so you are never left with an empty preview.

## Run Locally

This repository contains the production build as a single self-contained page, so there is nothing to install.

```bash
# Option 1: open the file directly
open index.html

# Option 2: serve it locally
python3 -m http.server 8000
# then visit http://localhost:8000
```

> Fonts (Manrope, Cormorant Garamond, DM Mono, Noto Sans SC) load from Google Fonts. Conversion itself does not need a network connection.

## Deploy

Because the app is a single static page, it works on any static host.


## Repository Structure

```text
txt-to-epub-converter/
├── index.html       
├── CHANGELOG.md      # Version history
├── README.md
└── assets/
    ├── logo.svg                
    ├── logo.png                
    ├── logo-wordmark.svg       
    ├── logo-wordmark.png
    ├── favicon.svg
    ├── favicon-64.png
    ├── apple-touch-icon.png    
    └── social-preview.png      
```


## Changelog

See [CHANGELOG.md](CHANGELOG.md). The current release is **1.3.5 — Website redesign and fast navigation**.

## Contributing

Issues and suggestions are welcome. If you found a book that Leafline split badly, open an issue with a short sample of its chapter headings (no need to share the whole text).

---

<div align="center">

Made for long-form reading.

</div>
