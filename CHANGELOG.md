# Changelog

This website has **7 identifiable converter versions** in the available commit
history. Version names and Android-style version codes below are a proposed
mapping; this is a React/Vite website, not a native Android app, so these are
not APK releases.

## 1.3.3 — 2026-10-25
**Chapter detection accuracy**
- **Version code:** 7
- **Commit:** _not yet committed_
- Heading lines are now checked against the book's dominant heading style
  (brackets, unit, separator, indentation), so lines like `第三章里提到的事情…`
  or indented story paragraphs that merely mention a chapter are rejected.
- Chapter numbers are validated as a sequence. Stray references to other
  chapters are discarded, while skipped numbers and volume restarts at 1 are
  still accepted. A restart is only accepted if chapter 2 follows.
- Tables of contents are detected by their repeated numbers, whether the
  contents list uses Arabic or Chinese numerals, and removed from the chapter
  structure even when the first chapter follows immediately.
- A heading repeated in both Chinese and Arabic numerals (`第九章` / `第9章`)
  becomes one chapter instead of two.
- Everything before the first real chapter (synopsis, author's notes,
  prologue, and the contents list) remains in the front matter section.
- Fixed Lines is still its own option and is never used by Auto when reliable
  headings exist.

## 1.3.2 — 2026-10-25
**Foundation and detection improvements**
- **Version code:** 6
- **Commit:** _not yet committed_
- **Auto** now follows a fixed priority: Chinese chapter headings, English
  chapter headings, explicit separator lines (`***`, `---`, `===`), Markdown
  headings, blank-line structure (only when sections are a sensible size), and
  fixed line counts only as the last resort.
- Chinese heading detection now tolerates skipped chapter numbers, volumes that
  restart numbering, full-width digits, bracketed headings such as `【第1章】`,
  and the 回/节/话 units. A table of contents is ignored and prose lines that
  merely start with a chapter reference are rejected.
- The "Boundary source" card and notice now say which method was used.
- **Separators** now also splits on explicit separator lines before falling back
  to blank-line runs.

## 1.3.1 — 2026-10-25
**Logo and bug-fix release**
- **Version code:** 5
- **Commit:** _not yet committed_
- Added the Leafline logo to the page header and footer, and replaced the
  placeholder orange favicon with the Leafline mark. Added an Apple touch icon
  and theme color.
- Fixed **Fixed lines** mode ignoring the setting whenever chapter headings
  were found.
- Fixed text before the first chapter heading (synopsis, author notes,
  prologue) being silently dropped. It is now kept as a "Front matter" section.
- Fixed a table of contents at the top of a file being detected as the chapter
  list, which put the entire book into the last chapter.
- Fixed garbled text for GBK/GB18030 and UTF-16 `.txt` files. UTF-8 is still
  tried first.
- Fixed the section title being repeated as the first paragraph in
  Separators and Fixed lines splits.
- Fixed the EPUB language being written as `other`; it is now `und`
  (undetermined).
- Fixed the EPUB ZIP entries having an invalid null timestamp.
- Fixed the upload zone opening the file picker twice on Enter, and scrolling
  the page on Space.
- Removed `maximum-scale=1` from the viewport tag so users can pinch-zoom.
- Replaced the developer-facing "first slice" message with plain wording.

## 1.3.0 — 2026-10-24
**Integration-ready modularization**
- **Version code:** 4
- **Commit:** `65731d3` — Refactor txt-epub-converter codebase and add integration guide
- Chapter detection, EPUB generation, and shared types were split into focused
  modules.
- Added a guide for integrating the converter into another website.
- Updated page metadata and made the favicon path work under a subpath.

## 1.2.0 — 2026-08-16
**Leafline visual refresh**
- **Version code:** 3
- **Commit:** `cd886f4` — Update txt-epub-converter styles and add new leafline mockup component
- Refined the page layout, typography, colors, and responsive styling.
- Added a Leafline mockup component elsewhere in the project.

## 1.1.0 — 2026-08-11
**Converter logic and EPUB export updates**
- **Version code:** 2
- **Commit:** `cb416e2` — Update project configuration and refactor text converter application logic
- Expanded EPUB creation with book metadata, chapter files, navigation, and
  optional cover-image handling.
- Refactored frontend logic and updated project configuration.

## 1.0.0 — 2026-08-11
**Initial TXT-to-EPUB website**
- **Version code:** 1
- **Commit:** `5d1ed6e` — Initialize txt-epub-converter artifact and update dependencies
- Added the initial converter page, React/Vite setup, styling, static assets,
  and dependencies.

## Versioning note

The repository has no Android `versionName`, `versionCode`, or release tags.
The version codes here are a proposed, increasing sequence assigned to the converter-changing
commits. Publish-only commits and changes outside the
converter are not counted as new converter versions.
