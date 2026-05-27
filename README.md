# Personal Homepage — Heesoo Jung

An al-folio-inspired academic homepage built with plain HTML/CSS/JS.
No Jekyll build, no npm — just open and edit.

## Structure

```
site/
├── index.html              # Home: bio, news, education, services, selected pubs
├── publications.html       # Full publication list (grouped by year)
├── README.md
└── assets/
    ├── css/main.css        # All styles + theme variables
    ├── js/theme.js         # Light/dark mode toggle (saved in localStorage)
    ├── img/                # Drop your profile.jpg here
    └── pdf/CV_Heesoo_Jung.pdf
```

## Deploy to GitHub Pages

1. Create a public repo named `<your-username>.github.io`.
2. Copy the contents of `site/` into the repo root (not the `site/` folder itself).
3. Push to `main`. GitHub Pages will serve it at `https://<your-username>.github.io/`.

```bash
cd site
git init
git add .
git commit -m "Initial homepage"
git branch -M main
git remote add origin git@github.com:<your-username>/<your-username>.github.io.git
git push -u origin main
```

In repo Settings → Pages, confirm the source is `main` branch / root.

## Customize

### Add your profile photo
1. Drop `profile.jpg` in `assets/img/`.
2. In `index.html`, replace the placeholder:
   ```html
   <div class="hero-photo-placeholder">HJ</div>
   ```
   with:
   ```html
   <img class="hero-photo" src="assets/img/profile.jpg" alt="Heesoo Jung">
   ```

### Update social links
Edit the `<div class="socials">` block in `index.html`. The icons (Scholar, GitHub, LinkedIn, Twitter, Email) point to `#` placeholders — swap in your real URLs.

### Change colors / theme
Edit the CSS variables at the top of `assets/css/main.css`:
```css
:root {
  --accent: #0f7c8a;        /* primary accent color */
  --accent-soft: #e6f4f6;   /* background of pills/badges */
  ...
}
```
The `html[data-theme="dark"]` block right below controls the dark mode palette.

### Add a news entry
In `index.html`, add a `<li>` at the top of `.news-list`:
```html
<li>
  <span class="news-date">May 2026</span>
  <span class="news-text">Paper accepted to <strong>NeurIPS 2026</strong>!</span>
</li>
```

### Add a publication
Copy any `<div class="pub">…</div>` block in `publications.html`. The structure is:
```html
<div class="pub">
  <div class="pub-title">Paper Title</div>
  <div class="pub-authors">Author A, <span class="me">Heesoo Jung</span>, Author C</div>
  <div class="pub-venue">Venue Name, Year</div>
  <div class="pub-links">
    <a class="pub-link" href="URL">code</a>
    <a class="pub-link" href="URL">paper</a>
  </div>
</div>
```
- Wrap your name with `<span class="me">…</span>` to bold it.
- Mark equal contribution with `<sup>*</sup>` after the name.

### Update the CV
Replace `assets/pdf/CV_Heesoo_Jung.pdf` with your latest CV (keep the same filename, or update the link in the navbar of both HTML files).

## Test locally

```bash
cd site
python3 -m http.server 8000
# open http://localhost:8000
```

## Credits
- Style inspiration: [al-folio](https://github.com/alshedivat/al-folio), [Jon Barron's site](https://jonbarron.info), [Haneul Yoo's site](https://haneul-yoo.github.io).
