# Base HTML Shell

Copy-paste template for every SkillBridge Africa page.

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#0a0a0f">
  <title>PAGE TITLE — SkillBridge Africa</title>
  <link rel="stylesheet" href="../pure-css-glassmorphism-liquid-glass-ui-kit/src/style.css">
  <link rel="stylesheet" href="../assets/site.css">
</head>
<body>

  <!-- NAVIGATION -->
  <header class="site-header">
    <nav class="site-nav site-container" aria-label="Main navigation">
      <a href="index.html" class="site-nav__logo">
        <img src="../assets/images/skill-bridge-logo.jpeg" alt="SkillBridge Africa logo">
        SkillBridge Africa
      </a>
      <button class="site-nav__toggle" aria-controls="main-nav" aria-expanded="false" aria-label="Toggle navigation">☰</button>
      <ul class="site-nav__links" id="main-nav" role="list">
        <li><a href="index.html">Home</a></li>
        <li><a href="courses.html">Courses</a></li>
        <li><a href="mentorship.html">Mentorship</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="contact.html">Contact</a></li>
      </ul>
      <div class="site-nav__actions">
        <button class="glass glass-btn theme-toggle-btn" id="theme-toggle" aria-label="Toggle colour scheme">
          <span class="icon-dark" aria-hidden="true">☀️</span>
          <span class="icon-light" aria-hidden="true">🌙</span>
        </button>
      </div>
    </nav>
  </header>

  <main id="main-content">
    <!-- PAGE CONTENT HERE -->
  </main>

  <!-- FOOTER -->
  <footer class="site-footer">
    <div class="site-container">
      <div class="site-footer__inner">
        <div class="site-footer__brand">
          <a href="index.html" class="site-nav__logo">
            <img src="../assets/images/skill-bridge-logo.jpeg" alt="SkillBridge Africa logo">
            SkillBridge Africa
          </a>
          <p>Bridging the skills gap across Africa through quality education, mentorship, and career opportunities.</p>
        </div>
        <ul class="site-footer__links" role="list">
          <li><a href="index.html">Home</a></li>
          <li><a href="courses.html">Courses</a></li>
          <li><a href="mentorship.html">Mentorship</a></li>
          <li><a href="about.html">About</a></li>
          <li><a href="contact.html">Contact</a></li>
        </ul>
        <ul class="site-footer__links" role="list" aria-label="Social media links">
          <li><a href="#" aria-label="LinkedIn">LinkedIn</a></li>
          <li><a href="#" aria-label="Twitter/X">Twitter/X</a></li>
          <li><a href="#" aria-label="Instagram">Instagram</a></li>
        </ul>
      </div>
      <p class="site-footer__copy">© 2026 SkillBridge Africa. All rights reserved.</p>
    </div>
  </footer>

  <script src="../pure-css-glassmorphism-liquid-glass-ui-kit/src/script.js" defer></script>
  <script>
    // Mobile nav toggle
    const toggle = document.getElementById('theme-toggle')?.closest('nav')?.querySelector('.site-nav__toggle');
    document.querySelector('.site-nav__toggle')?.addEventListener('click', function() {
      const nav = document.getElementById('main-nav');
      const open = nav.classList.toggle('is-open');
      this.setAttribute('aria-expanded', open);
    });
  </script>
</body>
</html>
```

## Notes
- Set `aria-current="page"` on the active nav link for each page.
- For `404.html` at root, adjust asset paths to `./` instead of `../`.
