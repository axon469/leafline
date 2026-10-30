# Changelog

This website has **13 identifiable converter versions** in the available commit
history. Version names and Android-style version codes below are a proposed
mapping; this is a React/Vite website, not a native Android app, so these are
not APK releases.

## 1.3.9 — 2026-10-29
**Accent colors and Material You**
- **Version code:** 13
- **File handling** now contains only the **Download folder** setting. The
  converter defaults section was removed, so the converter always starts with
  Auto detection, 40 lines per chapter, 2 blank lines, and Chinese (Simplified).
- Added **Accent color** at the bottom of **Design style**: ten palettes, each
  shown as four large, slightly overlapping circles in its exact colors, with
  its name and a clear selected indicator. With Standard the options are
  frosted-glass capsules like the reference; with Material You they are tonal
  cards. Every option works with the keyboard.
- Choosing a palette recolors buttons, navigation, links, cards, icons, borders,
  and selected states across the whole website at once, in Light, Dark, and
  AMOLED. Colors are adjusted only as much as needed to keep text readable, and
  the swatches always show the exact palette colors. **Neon Galaxy** is the
  default. The choice is saved, restored after a refresh, and applied before the
  page first paints.
- **Material You** is now a selectable design style: tonal surfaces tinted by
  your accent color, large rounded cards, pill buttons, filled input fields, and
  a tonal indicator in navigation and menus. It works with Light, Dark, AMOLED,
  and every accent palette. Liquid Glass is still marked "Coming soon".

## 1.3.8 — 2026-10-28
**Settings reorganized, Light Mode, and download folder**
- **Version code:** 12
- **Light Mode** now follows the brief exactly: a white background, black text,
  and white buttons with clear dark outlines. Selected options (navigation,
  segmented controls, theme and detection choices) are shown with a heavy black
  outline.
- Removed the "Default" theme. The Theme selector now offers **Light Mode**,
  **Dark Mode**, and **AMOLED Dark**, with a check mark on the selected one.
  Light is the starting theme, and an older saved "Default" choice becomes
  Light.
- Added a **Design style** section to Appearance: Standard (current), and
  "Coming soon" placeholders for Material You and Liquid Glass.
- Moved **Text size** from Appearance to Animations.
- Moved the **Catalogue** options from About to Animations and added a live
  preview that updates as soon as you change the options. Cards are now
  vertical tiles in a grid, and List is a compact row list, so the difference
  is easy to see.
- **File handling** has a new **Download folder** setting: use the browser's
  default, ask every time, or always save to a folder you choose. Browsers that
  do not allow websites to pick a folder (most phones, Firefox, and Safari)
  show a clear note and keep using the normal download.
- **About** has a new **Version history** page that lists every release from
  `CHANGELOG.md`.

## 1.3.7 — 2026-10-28
**Settings page and themes**
- **Version code:** 11
- Settings is now organized into sections instead of one long list:
  **Appearance**, **Animations**, **File handling**, and **About**. On desktop a
  side menu sits next to the section; on mobile Settings opens as a list and
  each section is its own page with a back link. Every section has its own
  address (`#/settings/appearance`, and so on), so links and the browser's back
  button work.
- Added a **Theme** selector inside Appearance with four options: **Default**
  (follows the device's light or dark setting), **Light Mode**, **Dark Mode**,
  and **AMOLED Dark** (pure black). The whole website changes immediately,
  including navigation, tool cards, inputs, settings, and the converter.
- The saved theme is applied before the page first paints, so there is no flash
  of the wrong theme on reload. Themes are defined by color tokens, so a new
  theme is one registry entry plus one block of tokens.
- **Animations** can follow the device, be on, or be reduced.
- **File handling** sets starting values for the TXT to EPUB Converter:
  detection method, lines per chapter, minimum blank lines, and book language.
  Changing a default also updates the open converter.
- **About** holds the version, privacy note, and the **Catalogue** options
  (expanded or collapsed categories, cards or list layout) plus a list of
  available tools.
- Settings are saved in the browser and restored after a refresh. Each value is
  checked on load, so one invalid value never resets the others. Number fields
  show an error and keep the previous value. Reset asks for confirmation. If
  the browser blocks storage, a notice explains that settings apply only until
  the tab is closed. Changes also sync between open tabs.

## 1.3.6 — 2026-10-28
**Cleanup and default theme**
- **Version code:** 10
- Removed the Text to PDF and EPUB to TXT placeholder cards. Home now lists
  only tools that are available.
- Home is now an expandable catalogue. Tools are grouped by category, each
  category collapses and expands, and a new tool is added by one registry entry
  without changing the navigation.
- Removed decorative text: the Home introduction, the "Detection modes"
  section, the tool page's marketing heading, the footer slogan, and the brand
  tagline. The tool page now has a plain title and a back link.
- Reset the whole website to the default light theme with system fonts. The
  premium colors, display fonts, gradient buttons, and glass navigation were
  replaced with plain defaults, so they can return later as Settings options.
- Fonts are no longer loaded from Google Fonts, so the page makes no external
  requests.
- The logo and icons are now read from the `assets` folder, with a built-in
  fallback logo if the file is missing.
- Settings keeps text size, reduced motion, privacy, and version, without the
  introduction text.

## 1.3.5 — 2026-10-28
**Website redesign and fast navigation**
- **Version code:** 9
- Leafline is now a multi-tool website. A new **Home** page lists every tool as
  a card; each tool lives at its own address (`#/tools/txt-to-epub`) so links,
  refresh, and the browser's back and forward buttons all work.
- Added persistent two-destination navigation: **Home** and **Settings**. It is
  a floating bar at the top on desktop and a bottom tab dock on mobile, with
  icons and a clear active state. Home stays active while a tool is open.
- Added a **Settings** page for the whole website: text size, reduced motion,
  a privacy note, version info, and reset. Preferences are saved in this
  browser only.
- **TXT to EPUB** is now a self-contained tool with its own page, a back link
  to all tools, and the existing detection, preview, and export unchanged. Its
  state is kept when you visit Settings and come back.
- Tools are registered in one list, so a new tool is one component plus one
  entry. Text to PDF and EPUB to TXT are listed as "Coming soon" and cannot be
  opened until they exist.
- Unknown addresses show a friendly page instead of a blank screen. The page
  title updates for each view.

## 1.3.4 — 2026-10-25
**Detection modes fixes and premium redesign**
- **Version code:** 8
- Redesigned the interface with an emerald palette, Cormorant Garamond and
  Manrope typography, a floating glass navigation bar, premium gradient
  buttons, and a new "Detection modes" section. Logo and favicon recolored to
  match.
- **Auto** now picks the most reliable heading pattern (Chinese or English,
  whichever has more valid headings) before separators, Markdown headings, and
  blank lines. Fixed lines remain the last resort.
- **Separators** now follows its configured rules exactly: separator lines
  plus runs of the chosen minimum blank lines. Changing the setting always
  changes the preview.
- **Fixed lines** always splits by the selected line count, even when headings
  exist, and labels sections "Part N" without altering the text.
- **Manual** now works: edit chapter start lines by line number, starting from
  Auto's suggestion, with Reset from Auto. Text before the first start line is
  kept as front matter.
- Each mode now shows a matching hint, and Manual boundaries reset when a new
  file is loaded.
- Chapter titles keep the full original heading (for example `第一章 夜行`)
  instead of dropping the chapter number.

## 1.3.3 — 2026-10-25
**Chapter detection accuracy**
- **Version code:** 7
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
- Chapter detection, EPUB generation, and shared types were split into focused
  modules.
- Added a guide for integrating the converter into another website.
- Updated page metadata and made the favicon path work under a subpath.

## 1.2.0 — 2026-08-16
**Leafline visual refresh**
- **Version code:** 3
- Refined the page layout, typography, colors, and responsive styling.
- Added a Leafline mockup component elsewhere in the project.

## 1.1.0 — 2026-08-11
**Converter logic and EPUB export updates**
- **Version code:** 2
- Expanded EPUB creation with book metadata, chapter files, navigation, and
  optional cover-image handling.
- Refactored frontend logic and updated project configuration.

## 1.0.0 — 2026-08-11
**Initial TXT-to-EPUB website**
- **Version code:** 1
- Added the initial converter page, React/Vite setup, styling, static assets,
  and dependencies.
