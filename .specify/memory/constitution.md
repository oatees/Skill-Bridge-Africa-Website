# SkillBridge Africa Constitution

## Project Vision
SkillBridge Africa is a digital platform designed to bridge the skills gap in Africa by connecting learners with quality education, mentorship, and career opportunities. The platform empowers individuals to develop in-demand skills and advance their careers while supporting organizations in building a skilled workforce.

---

## Core Principles

### I. User-Centric Design
Every feature, component, and interaction must prioritize the end user's experience. Design decisions are validated through user research, accessibility standards (WCAG AA compliance), and inclusive design practices. The platform serves diverse users across Africa with varying connectivity, device capabilities, and technical literacy levels.

**Implementation**: 
- All UI components follow the Liquid Glass design system (glassmorphism, accessibility-first)
- Responsive design from mobile-first perspective
- Performance optimization for low-bandwidth environments
- Multilingual support roadmap

### II. Accessibility & Inclusivity
The platform must be accessible to all users, regardless of ability, device, or network conditions. WCAG 2.1 AA compliance is non-negotiable. All interactive elements require keyboard navigation, ARIA labels, and focus management.

**Implementation**:
- Pure CSS + vanilla JavaScript (zero dependencies for core functionality)
- Semantic HTML structure
- Color contrast ratios meet WCAG AA standards
- Support for screen readers and assistive technologies
- Graceful degradation for older browsers

### III. Performance & Efficiency
The platform must load quickly and function reliably on slow networks. Zero external dependencies for core UI ensures fast load times and reduced attack surface.

**Implementation**:
- CSS-only animations (respects `prefers-reduced-motion`)
- Minimal JavaScript footprint
- Static asset optimization
- Progressive enhancement strategy

### IV. Quality & Testing
Code quality is maintained through rigorous testing, code review, and adherence to best practices. All changes must be validated before deployment.

**Implementation**:
- Component-level testing for UI kit
- Integration testing for feature workflows
- Manual accessibility testing
- Code review checklist compliance

### V. Scalability & Maintainability
The codebase must be organized, documented, and easy to extend. Clear separation of concerns and consistent patterns enable team collaboration and future growth.

**Implementation**:
- BEM methodology for CSS organization
- Class-based component architecture for JavaScript
- Comprehensive inline documentation
- Design token system for theming

---

## Technology Stack & Standards

### Frontend
- **HTML5**: Semantic markup, accessibility-first
- **CSS3**: Custom properties (design tokens), BEM methodology, no preprocessors
- **JavaScript (ES6+)**: Vanilla JS, class-based components, no frameworks for core UI
- **Design System**: `@pure-css-glassmorphism-liquid-glass-ui-kit` (15+ components, 12 animations, light/dark themes)

### Design Tokens
All visual properties are defined as CSS custom properties via `@pure-css-glassmorphism-liquid-glass-ui-kit`:
- **Color palette**: Accent colors (aqua, violet, rose, amber, lime), semantic surfaces, text colors
- **Spacing scale**: 2xs (4px) to 4xl (96px)
- **Typography scale**: 2xs (0.68rem) to 4xl (2.8rem)
- **Border radius scale**: xs (6px) to full (9999px)
- **Z-index scale**: base (1) to toast (800)
- **Easing functions**: glass, liquid, smooth, out
- **Duration tokens**: fast (180ms), mid (360ms), slow (600ms)
- **Glass effects**: Blur values (sm to xl), shadows, reflections, borders

### Browser Support
- Modern browsers (Chrome, Firefox, Safari, Edge)
- Graceful degradation for older browsers via `@supports` fallback
- Mobile-first responsive design

### Accessibility Standards
- WCAG 2.1 Level AA compliance
- Keyboard navigation for all interactive elements
- ARIA roles and labels for semantic meaning
- Focus management and visible focus indicators
- Color contrast ratios ≥ 4.5:1 for normal text

---

## Component Architecture

### UI Kit Components
All components follow a consistent pattern:
1. **HTML Structure**: Semantic, accessible markup
2. **CSS Styling**: BEM classes, design tokens, responsive
3. **JavaScript Behavior**: Class-based, event-driven, no global state
4. **Documentation**: Inline comments, usage examples

### Component Categories (from `@pure-css-glassmorphism-liquid-glass-ui-kit`)
- **Cards**: Glass cards, profile cards, skeleton loaders
- **Buttons**: Primary, ghost, accent, danger, icon, sizes (sm, default, lg)
- **Forms**: Inputs, selects, checkboxes, radios, switches, textareas, range sliders
- **Navigation**: Tabs, pills (nav), breadcrumbs, dropdowns, toggle groups
- **Feedback**: Toasts (success, error, warning, info), modals, tooltips, notifications
- **Data**: Tables (sortable, searchable, selectable, pagination), steppers (horizontal/vertical)
- **Layout**: Grids, containers, spacing utilities, avatar groups
- **Chips**: Dismissible, selectable, dynamic chip groups
- **Badges & Tags**: Status badges, semantic tags

### Animation Standards (from `@pure-css-glassmorphism-liquid-glass-ui-kit`)
All animations use CSS keyframes (no JavaScript animation libraries) and include 12 liquid glass animations:
1. **Liquid Morph** — Organic shape morphing
2. **Shimmer** — Gradient sweep effect
3. **Float** — Vertical floating motion
4. **Refraction** — Rotating gradient effect
5. **Ripple** — Expanding wave from center
6. **Edge Glow** — Pulsing outer glow
7. **Breathing Blur** — Blur intensity breathing
8. **Depth Shift** — 3D perspective rotation
9. **Cascade Reveal** — Staggered entry animation
10. **Prism Hue Shift** — Color rotation effect
11. **Liquid Drain** — Clip-path drain animation
12. **Surface Tension** — Elastic squash/stretch

All animations:
- Respect `prefers-reduced-motion` media query
- Have clear purpose and duration (fast: 180ms, mid: 360ms, slow: 600ms)
- Use easing functions from design tokens

---

## Development Workflow

### Code Organization
```
project-root/
├── @pure-css-glassmorphism-liquid-glass-ui-kit/
│   ├── src/
│   │   ├── index.html          # Component showcase & demo
│   │   ├── style.css           # Design system + 15+ components
│   │   │                        # 31 sections: tokens, reset, themes,
│   │   │                        # components, animations, layout
│   │   └── script.js           # Component behaviors (class-based)
│   │                            # GlassTheme, GlassModal, GlassTabs,
│   │                            # GlassAccordion, GlassDropdown, etc.
│   ├── LICENSE.txt
│   └── README.md
├── pages/                       # Website pages (to be created)
│   ├── index.html              # Landing page
│   ├── about.html              # About SkillBridge
│   ├── courses.html            # Course catalog
│   ├── mentorship.html         # Mentorship program
│   └── contact.html            # Contact form
├── assets/                      # Images, logos, media
├── .specify/                    # Spec-driven workflow config
└── docs/                        # Documentation
```

### CSS Guidelines (from `@pure-css-glassmorphism-liquid-glass-ui-kit`)
- **BEM Methodology**: `.glass-btn`, `.glass-btn--primary`, `.glass-btn__icon`
- **Single Responsibility**: Each class has one purpose
- **Design Tokens**: Use CSS custom properties (`:root` defines 40+ tokens), never hardcode values
- **Comments**: 31 organized sections with clear TOC
- **Responsive**: Mobile-first, use media queries for larger screens
- **Theme Support**: `[data-theme="light"]` for light mode overrides
- **Fallback Support**: `@supports not (backdrop-filter)` for older browsers
- **Accessibility**: Color contrast ≥ 4.5:1, focus-visible outlines, reduced-motion support

### JavaScript Guidelines (from `@pure-css-glassmorphism-liquid-glass-ui-kit`)
- **Class-Based**: Each component is a class with `init()` static factory method
- **Custom Events**: Emit `glass:*` events for component communication (e.g., `glass:modal:open`)
- **No Global State**: Components are self-contained, no shared mutable state
- **Keyboard Support**: Arrow keys, Tab, Enter, Escape, Home, End
- **ARIA Management**: Update roles and attributes dynamically
- **Focus Management**: Trap focus in modals, manage focus on open/close
- **No Dependencies**: Pure vanilla JavaScript, zero external libraries
- **Components Included**:
  - `GlassTheme` — Light/dark mode toggle with localStorage
  - `GlassModal` — Focus trap, backdrop click, keyboard escape
  - `GlassTabs` — Arrow key navigation, ARIA roles
  - `GlassAccordion` — Expand/collapse with ARIA
  - `GlassDropdown` — Menu with keyboard navigation
  - `GlassToast` — Auto-dismiss notifications
  - `GlassStepper` — Multi-step flow with state management
  - `GlassTable` — Sorting, searching, row selection, pagination
  - `GlassChips` — Dismissible and selectable chips
  - `GlassRipple` — Material-like ripple effect
  - `GlassParallax` — Mouse tilt on cards
  - Plus utilities for navigation, breadcrumbs, avatars

### Git Workflow
- Feature branches from `main`
- Descriptive commit messages
- Pull requests with code review
- Automated checks (linting, accessibility, performance)

---

## Quality Standards

### Code Review Checklist
- [ ] Accessibility: WCAG AA compliance verified
- [ ] Performance: No unnecessary dependencies, optimized assets
- [ ] Testing: Manual testing on multiple devices/browsers
- [ ] Documentation: Comments, examples, usage instructions
- [ ] Consistency: Follows BEM, design tokens, naming conventions
- [ ] Security: No hardcoded credentials, XSS prevention

### Testing Strategy
- **Unit Testing**: Component behavior in isolation
- **Integration Testing**: Component interactions, workflows
- **Accessibility Testing**: Keyboard navigation, screen reader compatibility
- **Performance Testing**: Load time, animation smoothness
- **Cross-Browser Testing**: Chrome, Firefox, Safari, Edge, mobile

### Deployment Checklist
- [ ] All tests passing
- [ ] Code review approved
- [ ] Accessibility audit passed
- [ ] Performance benchmarks met
- [ ] Documentation updated
- [ ] Changelog entry added

---

## Business Alignment

### SkillBridge Africa Goals
1. **Accessibility**: Make quality education accessible to all Africans
2. **Affordability**: Provide cost-effective learning solutions
3. **Relevance**: Offer skills aligned with market demand
4. **Community**: Build a supportive learning community
5. **Impact**: Measurable career advancement for learners

### Platform Commitments
- **User Privacy**: Secure data handling, transparent policies
- **Quality Content**: Curated, expert-led courses and mentorship
- **Continuous Improvement**: Regular updates based on user feedback
- **Sustainability**: Viable business model supporting long-term growth

---

## Governance

### Constitution Authority
This constitution supersedes all other development practices and guidelines. It defines the non-negotiable standards for SkillBridge Africa's digital platform.

### Amendment Process
1. **Proposal**: Document the change and rationale
2. **Review**: Team discussion and consensus
3. **Approval**: Lead architect/product owner sign-off
4. **Migration**: Plan for existing code compliance
5. **Documentation**: Update this constitution and related docs

### Compliance Verification
- All PRs must reference constitution compliance
- Code review includes constitution checklist
- Automated tools verify accessibility and performance standards
- Regular audits (quarterly) ensure ongoing compliance

### Escalation Path
- **Minor Issues**: Addressed in code review
- **Major Violations**: Escalated to lead architect
- **Systemic Problems**: Trigger constitution amendment discussion

---

## Related Documentation
- **Design System**: `@pure-css-glassmorphism-liquid-glass-ui-kit/README.md`
- **Component Guide**: `@pure-css-glassmorphism-liquid-glass-ui-kit/src/index.html` (live demo)
- **CSS Reference**: `@pure-css-glassmorphism-liquid-glass-ui-kit/src/style.css` (31 sections, 2000+ lines)
- **JavaScript Reference**: `@pure-css-glassmorphism-liquid-glass-ui-kit/src/script.js` (class-based components)
- **Development Guide**: `.specify/templates/` (planning, implementation, testing)
- **Business Plan**: `SkillBridge_Africa_Complete_Report.docx`
- **Market Research**: `Market Research.docx`
- **Financial Analysis**: `SkillBridge_Africa -Financial Analysis Report.docx`

---

**Version**: 1.1.0 | **Ratified**: 2025-01-15 | **Last Amended**: 2025-01-16

**Custodian**: SkillBridge Africa Development Team  
**Design System**: `@pure-css-glassmorphism-liquid-glass-ui-kit`  
