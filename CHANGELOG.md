# Changelog

This website has **4 identifiable converter versions** in the available commit
history. Version names and Android-style version codes below are a proposed
mapping; this is a React/Vite website, not a native Android app, so these are
not APK releases.

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
The version codes here are a proposed, increasing sequence assigned to the four
converter-changing commits. Publish-only commits and changes outside the
converter are not counted as new converter versions.
