# Research: SkillBridge Africa Website

**Date**: 2026-05-23
**Feature**: specs/001-skillbridge-africa-website

All technical decisions are resolved from the project constitution and existing UI kit. No external research required.

---

## Decision Log

### 1. CSS/JS Framework

- **Decision**: No external framework. Use `pure-css-glassmorphism-liquid-glass-ui-kit` exclusively.
- **Rationale**: Constitution mandates zero external dependencies for core UI. The kit provides all required components (cards, buttons, forms, navigation, modals, toasts, tables).
- **Alternatives considered**: Tailwind CSS, Bootstrap — rejected; violate zero-dependency constraint.

### 2. Contact Form Submission

- **Decision**: Formspree (free tier) as the form backend.
- **Rationale**: No custom backend in scope. Formspree requires only an `action` attribute on the `<form>` tag — no JavaScript needed, works with progressive enhancement.
- **Alternatives considered**: Netlify Forms (requires Netlify hosting), mailto: fallback (poor UX, exposes email) — Formspree is hosting-agnostic and reliable.

### 3. Page Routing

- **Decision**: Plain HTML file-per-page (no SPA router).
- **Rationale**: Static hosting, no build step, works without JavaScript, simplest possible approach.
- **Alternatives considered**: Single-page app with hash routing — unnecessary complexity for 5 pages.

### 4. Theme (Light/Dark)

- **Decision**: Use `GlassTheme` class from the UI kit's `script.js`. Defaults to system `prefers-color-scheme`.
- **Rationale**: Already implemented in the kit with `localStorage` persistence. Zero additional code needed.
- **Alternatives considered**: Custom implementation — redundant.

### 5. Hosting

- **Decision**: GitHub Pages (or any static host — Netlify, Vercel).
- **Rationale**: Free, zero-config for static HTML. No server-side requirements.
- **Alternatives considered**: Custom server — out of scope.

### 6. 404 Page

- **Decision**: `404.html` at repository root with consistent nav/footer.
- **Rationale**: GitHub Pages and most static hosts serve `404.html` automatically for missing routes.
- **Alternatives considered**: None — standard convention.

---

## Resolved Unknowns

All items from Technical Context were pre-resolved. No NEEDS CLARIFICATION markers remain.
