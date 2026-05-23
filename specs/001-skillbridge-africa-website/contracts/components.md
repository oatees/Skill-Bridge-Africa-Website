# Shared Component Contracts: SkillBridge Africa Website

All components use the `pure-css-glassmorphism-liquid-glass-ui-kit` design system. No custom component library is introduced.

---

## Navigation Header

**Used on**: All 6 pages (5 main + 404)

| Element | Requirement |
|---------|-------------|
| Logo | SkillBridge Africa logo + site name, links to index.html |
| Nav links | Home, Courses, Mentorship, About, Contact |
| Active state | Current page link visually distinguished |
| Theme toggle | Light/dark toggle using `GlassTheme` (`.theme-toggle-btn`) |
| Mobile menu | Hamburger toggle for screens <768px; keyboard accessible |
| Keyboard nav | All links reachable via Tab; mobile menu operable via Enter/Space |

---

## Footer

**Used on**: All 6 pages

| Element | Requirement |
|---------|-------------|
| Logo + tagline | Brief brand statement |
| Nav links | Repeat primary navigation links |
| Social links | Placeholder links (LinkedIn, Twitter/X, Instagram) |
| Copyright | "© 2026 SkillBridge Africa. All rights reserved." |

---

## Course Card

**Used on**: index.html (featured), courses.html (full catalog)

| Element | Requirement |
|---------|-------------|
| Title | Course name, heading level appropriate to context |
| Description | 1–2 sentence summary |
| Category badge | `.glass-badge` with category label |
| Level badge | `.glass-badge` with Beginner / Intermediate / Advanced |
| Duration | Optional — shown if provided |

---

## Mentor Card

**Used on**: mentorship.html

| Element | Requirement |
|---------|-------------|
| Avatar | Image or `.glass-avatar` placeholder |
| Name | Mentor full name |
| Expertise | Primary skill area (badge or subtitle) |
| Bio | 2–3 sentence description |

---

## Contact Form

**Used on**: contact.html

| Element | Requirement |
|---------|-------------|
| Name field | `<input type="text">`, required, `.glass-input` |
| Email field | `<input type="email">`, required, `.glass-input` |
| Message field | `<textarea>`, required, `.glass-textarea` |
| Submit button | `.glass-btn glass-btn--primary`, keyboard accessible |
| Validation | HTML5 `required` + `type="email"` for no-JS baseline; enhanced with JS for inline messages |
| Action | `<form action="https://formspree.io/f/{ID}" method="POST">` |
| Success state | Visible confirmation message after submission |

---

## Component Usage Rules

- All glass surfaces use `.glass` utility class from the UI kit
- Buttons follow `.glass-btn` + modifier pattern (e.g. `--primary`, `--ghost`)
- Badges use `.glass-badge` + accent modifier (e.g. `--aqua`, `--violet`)
- All interactive elements have `:focus-visible` outlines (provided by UI kit)
- Animations respect `prefers-reduced-motion` (enforced by UI kit)
- No inline styles — all visual properties via CSS custom properties (design tokens)
