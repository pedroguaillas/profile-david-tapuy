# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```sh
npm run dev       # dev server at localhost:4321
npm run build     # production build to ./dist/
npm run preview   # preview production build locally
npm run astro ... # astro CLI (e.g. astro add tailwind, astro check)
```

Node >=22.12.0 required.

## Architecture

Astro 6 project (basics template) for David Tapuy's profile/portfolio site. No framework integrations yet — pure Astro components.

**Routing:** File-based. `src/pages/index.astro` → `/`. Add pages by dropping `.astro` files in `src/pages/`.

**Component pattern:** Pages compose layouts and components. `Layout.astro` wraps everything via `<slot />`. Page-level data and imports go in the frontmatter fence (`---`).

**Assets:** Static files in `public/` served at root. Processed assets (SVG, images) in `src/assets/` — import them in components for Astro's asset pipeline.

**Styling:** Scoped `<style>` blocks per component. Global styles go in `Layout.astro` or a dedicated CSS file imported there.

**Config:** `astro.config.mjs` — currently empty `defineConfig({})`. Add integrations (Tailwind, React, etc.) here via `astro add <integration>`.
