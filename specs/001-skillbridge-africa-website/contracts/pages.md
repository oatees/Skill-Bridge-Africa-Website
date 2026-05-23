# Page Contracts: SkillBridge Africa Website

Each page contract defines the required sections, key content elements, and acceptance criteria for that page.

---

## Home (`pages/index.html`)

**Purpose**: Primary entry point — communicate value proposition and direct users to key sections.

### Required Sections

| Section | Content | CTA |
|---------|---------|-----|
| Hero | Headline, sub-headline, value proposition | "Browse Courses", "Find a Mentor" |
| Features/Benefits | 3–4 key platform benefits (icons + text) | — |
| Course Highlights | 3 featured courses (Course cards) | "View All Courses" → courses.html |
| Mentorship Teaser | Brief mentorship pitch | "Learn More" → mentorship.html |
| Call to Action | Final conversion section | "Get Started" → contact.html |

### Acceptance Criteria

- Hero content visible above the fold on 375px mobile and 1280px desktop
- All CTAs link to correct pages
- Page passes WCAG AA audit

---

## Courses (`pages/courses.html`)

**Purpose**: Display the full course catalog.

### Required Sections

| Section | Content | CTA |
|---------|---------|-----|
| Page Header | Title + brief description | — |
| Course Grid | All courses as glass cards (title, description, category badge, level badge) | — |

### Acceptance Criteria

- Each course card displays all 4 required fields (title, description, category, level)
- Cards are responsive: 1 column mobile, 2 tablet, 3 desktop
- Page passes WCAG AA audit

---

## Mentorship (`pages/mentorship.html`)

**Purpose**: Explain the mentorship program and prompt users to apply.

### Required Sections

| Section | Content | CTA |
|---------|---------|-----|
| Page Header | Title + program overview | — |
| How It Works | 3-step process (glass stepper or cards) | — |
| Mentor Profiles | Mentor cards (name, expertise, bio, avatar) | — |
| Apply / Inquire | Clear next-step section | "Apply Now" → contact.html |

### Acceptance Criteria

- Program process is clearly explained in 3 or fewer steps
- At least 3 mentor profiles shown
- Apply CTA links to contact.html
- Page passes WCAG AA audit

---

## About (`pages/about.html`)

**Purpose**: Build trust by communicating mission, values, and impact.

### Required Sections

| Section | Content | CTA |
|---------|---------|-----|
| Mission & Vision | Organisation purpose and long-term goal | — |
| Core Values | 3–5 values with brief descriptions | — |
| Impact / Stats | Key metrics or goals (learners reached, courses, etc.) | — |
| Team (optional) | Team member cards if content available | — |

### Acceptance Criteria

- Mission and vision are clearly stated
- At least 3 values shown
- Page passes WCAG AA audit

---

## Contact (`pages/contact.html`)

**Purpose**: Allow users to send inquiries to the SkillBridge Africa team.

### Required Sections

| Section | Content | Notes |
|---------|---------|-------|
| Page Header | Title + brief invitation | — |
| Contact Form | Name, Email, Message fields + Submit | Formspree action URL |
| Confirmation | Success message shown after submission | Inline or Formspree redirect |
| Alternative Contact | Email address or social links | Optional |

### Acceptance Criteria

- Form submits to Formspree endpoint
- Required field validation fires before submission
- Email format validated before submission
- Success feedback visible after submission
- Form is fully operable via keyboard
- Page passes WCAG AA audit

---

## 404 (`404.html`)

**Purpose**: Handle missing routes gracefully.

### Required Sections

- Clear "Page not found" message
- Link back to Home
- Consistent header/footer navigation

### Acceptance Criteria

- Served automatically by static host for missing routes
- User can navigate back to Home in one click
