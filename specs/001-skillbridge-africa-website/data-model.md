# Content Model: SkillBridge Africa Website

**Date**: 2026-05-23
**Feature**: specs/001-skillbridge-africa-website

This is a static site — no database. The "data model" describes the content structures hardcoded in HTML.

---

## Entities

### Course

Represents a learning offering displayed on the Courses page.

| Field | Type | Required | Notes |
|-------|------|----------|-------|
| title | string | yes | e.g. "Data Analysis with Python" |
| description | string | yes | 1–2 sentence summary |
| category | string | yes | e.g. "Technology", "Business", "Design" |
| level | enum | yes | Beginner / Intermediate / Advanced |
| duration | string | no | e.g. "6 weeks", "Self-paced" |

### Mentor

Represents a mentor profile displayed on the Mentorship page.

| Field | Type | Required | Notes |
|-------|------|----------|-------|
| name | string | yes | Full name |
| expertise | string | yes | Primary skill area |
| bio | string | yes | 2–3 sentence description |
| avatar | image | no | Photo or placeholder avatar |

### Contact Inquiry

Represents a user-submitted contact form entry (handled by Formspree).

| Field | Type | Required | Validation |
|-------|------|----------|------------|
| name | string | yes | Non-empty |
| email | string | yes | Valid email format |
| message | string | yes | Non-empty |

---

## State Transitions

### Contact Form

```
Idle → Filling → Submitted (success feedback shown)
              ↘ Validation Error (inline error messages shown)
```

No other stateful interactions. Theme toggle (light/dark) is managed by `GlassTheme` from the UI kit.
