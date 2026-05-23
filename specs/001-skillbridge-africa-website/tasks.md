# Tasks: SkillBridge Africa Website

**Input**: Design documents from `specs/001-skillbridge-africa-website/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, contracts/pages.md, contracts/components.md

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (US1–US4)

---

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project scaffolding and shared assets in place before any page work begins.

- [x] T001 Create `pages/`, `assets/images/`, `assets/icons/` directories per plan.md
- [x] T002 Copy `skill-brigde logo.jpeg` to `assets/images/skill-bridge-logo.jpeg`
- [x] T003 Create `404.html` with consistent nav/footer and "Page not found" message linking back to `pages/index.html`

**Checkpoint**: Directory structure ready, shared assets in place.

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Shared HTML partials pattern and base page shell that every page reuses. Must be complete before any user story page is built.

- [x] T004 Create base HTML shell (doctype, `<head>` with UI kit CSS/JS links, meta viewport, theme-color) documented as a copy-paste template in `docs/base-shell.md`
- [x] T005 [P] Build shared navigation header component (logo, nav links: Home/Courses/Mentorship/About/Contact, theme toggle button, mobile hamburger) — document markup pattern in `docs/base-shell.md`
- [x] T006 [P] Build shared footer component (logo, nav links, social placeholders, copyright) — document markup pattern in `docs/base-shell.md`
- [x] T007 Create `assets/site.css` for site-specific overrides (layout, hero, page-specific tweaks) using only CSS custom properties from the UI kit

**Checkpoint**: Base shell + nav + footer ready. All user story pages can now be built independently.

---

## Phase 3: User Story 1 — Discover Platform & Browse Courses (Priority: P1) 🎯 MVP

**Goal**: Visitor lands on the homepage, understands the value proposition, and navigates to the course catalog.

**Independent Test**: Open `pages/index.html` and `pages/courses.html` in a browser. Verify hero content is visible above the fold, all CTAs link correctly, and course cards display title/description/category/level. Run axe audit — zero critical violations.

### Implementation

- [x] T008 [US1] Build `pages/index.html` — Hero section (headline, sub-headline, value proposition, "Browse Courses" + "Find a Mentor" CTAs) using `.glass`, `.glass-card`, `.glass-btn--primary`, `.glass-btn--ghost`
- [x] T009 [US1] Add Features/Benefits section to `pages/index.html` — 3–4 benefit cards using `.glass-card`
- [x] T010 [US1] Add Course Highlights section to `pages/index.html` — 3 featured course cards (title, description, category badge, level badge) with "View All Courses" CTA linking to `pages/courses.html`
- [x] T011 [US1] Add Mentorship Teaser section to `pages/index.html` — brief pitch with "Learn More" CTA linking to `pages/mentorship.html`
- [x] T012 [US1] Add final CTA section to `pages/index.html` — "Get Started" button linking to `pages/contact.html`
- [x] T013 [US1] Build `pages/courses.html` — page header + responsive course grid (all courses as `.glass-card` with title, description, `.glass-badge` for category and level)
- [ ] T014 [US1] Verify keyboard navigation on both pages (Tab through all links/buttons); verify `pages/index.html` and `pages/courses.html` render with JS disabled

**Checkpoint**: US1 fully functional. Homepage and course catalog independently testable and deployable as MVP.

---

## Phase 4: User Story 2 — Learn About Mentorship Program (Priority: P2)

**Goal**: Learner visits the mentorship page, understands the program, and finds a clear apply/contact pathway.

**Independent Test**: Open `pages/mentorship.html`. Verify program overview, 3-step how-it-works, at least 3 mentor cards, and "Apply Now" CTA linking to `pages/contact.html`. Run axe audit — zero critical violations.

### Implementation

- [x] T015 [US2] Build `pages/mentorship.html` — page header + program overview section
- [x] T016 [US2] Add "How It Works" section to `pages/mentorship.html` — 3-step process using `.glass-stepper` or `.glass-card` steps
- [x] T017 [US2] Add Mentor Profiles section to `pages/mentorship.html` — at least 3 mentor cards (avatar placeholder, name, expertise badge, bio) using `.glass-card` + `.glass-avatar`
- [x] T018 [US2] Add Apply/Inquire CTA section to `pages/mentorship.html` — "Apply Now" `.glass-btn--primary` linking to `pages/contact.html`
- [ ] T019 [US2] Verify keyboard navigation; verify page renders with JS disabled

**Checkpoint**: US2 fully functional. Mentorship page independently testable.

---

## Phase 5: User Story 3 — Contact SkillBridge Africa (Priority: P3)

**Goal**: User submits the contact form and receives visible confirmation.

**Independent Test**: Open `pages/contact.html`. Submit with empty fields — verify inline validation. Submit with invalid email — verify error. Submit valid form — verify success feedback. Run axe audit — zero critical violations.

### Implementation

- [x] T020 [US3] Build `pages/contact.html` — page header + contact form (name `.glass-input`, email `.glass-input`, message `.glass-textarea`, submit `.glass-btn--primary`) with `action="https://formspree.io/f/{ID}" method="POST"`
- [x] T021 [US3] Add HTML5 client-side validation (`required`, `type="email"`) as no-JS baseline; add JS-enhanced inline error messages for name, email, message fields
- [x] T022 [US3] Add success confirmation message (shown after Formspree redirect or via JS on submission); add optional alternative contact info section
- [ ] T023 [US3] Verify full keyboard operability of form; verify form HTML5 validation works with JS disabled

**Checkpoint**: US3 fully functional. Contact form independently testable.

---

## Phase 6: User Story 4 — Learn About SkillBridge Africa (Priority: P4)

**Goal**: Visitor reads the About page and understands the organisation's mission, values, and impact.

**Independent Test**: Open `pages/about.html`. Verify mission/vision statement, at least 3 values, and impact/stats section are present. Run axe audit — zero critical violations.

### Implementation

- [x] T024 [US4] Build `pages/about.html` — page header + Mission & Vision section
- [x] T025 [US4] Add Core Values section to `pages/about.html` — 3–5 value cards using `.glass-card`
- [x] T026 [US4] Add Impact/Stats section to `pages/about.html` — key metrics or goals using stat cards (`.glass` surface)
- [ ] T027 [US4] Verify keyboard navigation; verify page renders with JS disabled

**Checkpoint**: US4 fully functional. All five pages independently testable.

---

## Phase 7: Polish & Cross-Cutting Concerns

**Purpose**: Accessibility, responsiveness, theming, and final quality pass across all pages.

- [ ] T028 [P] Run axe DevTools accessibility audit on all 6 pages (`index`, `courses`, `mentorship`, `about`, `contact`, `404`) — fix all critical and serious violations
- [ ] T029 [P] Verify responsive layout on all pages at 320px, 768px, 1280px — fix any overflow or layout breaks in `assets/site.css`
- [ ] T030 [P] Verify light/dark theme toggle works on all pages (`GlassTheme` from UI kit); verify `prefers-color-scheme` default is respected
- [ ] T031 [P] Verify color contrast ≥4.5:1 for all body text in both themes using browser DevTools or Colour Contrast Analyser
- [ ] T032 Verify `prefers-reduced-motion` disables animations on all pages
- [ ] T033 Cross-browser smoke test: open `pages/index.html` in Chrome, Firefox, Safari (or Edge) — verify no visual regressions
- [ ] T034 Run quickstart.md validation: follow setup steps from scratch, confirm local dev server works and Formspree endpoint is configured
- [ ] T035 Final review: confirm all nav links resolve correctly across all pages; confirm `404.html` is served for a missing route on the chosen static host

---

## Dependencies & Execution Order

### Phase Dependencies

- **Phase 1 (Setup)**: No dependencies — start immediately
- **Phase 2 (Foundational)**: Depends on Phase 1 — blocks all user story phases
- **Phases 3–6 (User Stories)**: All depend on Phase 2 completion; can proceed in parallel
- **Phase 7 (Polish)**: Depends on all desired user story phases being complete

### User Story Dependencies

- **US1 (P1)**: No dependency on other stories — pure MVP
- **US2 (P2)**: Independent of US1; shares nav/footer from Phase 2
- **US3 (P3)**: Independent; links to contact.html from US1 and US2 CTAs
- **US4 (P4)**: Independent; no dependencies on other stories

### Within Each User Story

- Page header → sections → CTA → accessibility verification
- Each story complete before moving to next priority

---

## Parallel Opportunities

```
# Phase 2 — run in parallel:
T005  Build shared navigation header
T006  Build shared footer

# Phases 3–6 — run in parallel (different files):
T008–T014  pages/index.html + pages/courses.html   (US1)
T015–T019  pages/mentorship.html                   (US2)
T020–T023  pages/contact.html                      (US3)
T024–T027  pages/about.html                        (US4)

# Phase 7 — run in parallel:
T028  Accessibility audit (all pages)
T029  Responsive layout check
T030  Theme toggle verification
T031  Contrast ratio check
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup
2. Complete Phase 2: Foundational
3. Complete Phase 3: US1 (homepage + courses)
4. **STOP and VALIDATE**: Open in browser, run axe audit, test keyboard nav
5. Deploy to GitHub Pages / Netlify as MVP

### Incremental Delivery

1. Setup + Foundational → shared shell ready
2. US1 → homepage + courses → deploy (MVP)
3. US2 → mentorship page → deploy
4. US3 → contact form → deploy
5. US4 → about page → deploy
6. Polish → production-ready

---

## Notes

- [P] tasks = different files, no shared-state dependencies
- [Story] label maps each task to its user story for traceability
- No test framework required — manual browser + axe DevTools testing per spec
- Commit after each phase or logical group
- Formspree form ID must be substituted before T020 is marked complete
