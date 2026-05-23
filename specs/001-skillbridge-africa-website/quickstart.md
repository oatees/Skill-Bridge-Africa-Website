# Quickstart: SkillBridge Africa Website

## Prerequisites

- A modern browser (Chrome, Firefox, Safari, or Edge)
- A text editor (VS Code recommended)
- Git (optional, for version control)
- A Formspree account (free) for the contact form

## Project Setup

No build step or package manager required.

1. Clone or download the repository.
2. Open the project root in your editor.
3. The UI kit is already present at `pure-css-glassmorphism-liquid-glass-ui-kit/src/`.

## Running Locally

Open any page directly in a browser:

```
pages/index.html
```

Or use a local dev server for accurate relative path resolution (recommended):

```bash
# Python (built-in)
python -m http.server 8080

# Node.js (npx)
npx serve .
```

Then visit `http://localhost:8080/pages/index.html`.

## Referencing the UI Kit

Each HTML page links the UI kit like this:

```html
<link rel="stylesheet" href="../pure-css-glassmorphism-liquid-glass-ui-kit/src/style.css">
<script src="../pure-css-glassmorphism-liquid-glass-ui-kit/src/script.js" defer></script>
```

## Contact Form Setup

1. Sign up at [formspree.io](https://formspree.io) and create a new form.
2. Copy your form endpoint (e.g. `https://formspree.io/f/abcdefgh`).
3. Set it as the `action` on the contact form in `pages/contact.html`.

## Accessibility Testing

- Install the [axe DevTools](https://www.deque.com/axe/devtools/) browser extension.
- Open each page and run an audit — target zero critical violations.

## Deployment

Push to GitHub and enable GitHub Pages (Settings → Pages → Deploy from branch `master`, root `/`).

For Netlify or Vercel, connect the repository and deploy with no build command and publish directory set to `/`.
