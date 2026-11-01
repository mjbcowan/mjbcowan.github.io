# mjbcowan.com

Personal CV site for Max Cowan. Plain HTML/CSS/JS with no build step, served by GitHub Pages.

- `index.html` holds all the content.
- `styles.css` holds the design. Colours and spacing are tokens at the top.
- `main.js` handles the dark-mode toggle, the active nav link, scroll reveals and the email link.

## Preview locally

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Common edits

- **CV PDF:** download links are switched off for now, and `assets/cv.pdf` is git-ignored so it is never published. To bring them back, supply a PDF without the phone number, remove it from `.gitignore`, and add `<a href="assets/cv.pdf" class="btn-line" target="_blank" rel="noopener">Download CV →</a>` where wanted (intro and Contact).
- **Add the real images:** save them as `assets/portrait.jpg` and `assets/fig-01.jpg` … `fig-04.jpg`, then change the matching `src="assets/….svg"` in `index.html` to `.jpg`. Images are shown in greyscale automatically.
  - `fig-01`: full-width banner, about 21:9.
  - `portrait`: about 4:3.
  - `fig-02` … `fig-04`: publication tiles, about 4:5.
- **Add a publication:** copy an existing `<article class="pub">` block in `index.html` and update its image, text, and `paper` / `doi` links.
- **Add a ledger row** (Experience, Education or Leadership): copy an existing `<div class="ledger-row">` block.

## AI and scraping opt-out

- `terms.html` is the Terms of use page, linked from the footer. It prohibits scraping and AI/ML use of the content and personal information.
- `robots.txt` blocks known AI-training, AI-search and dataset crawlers, and allows ordinary search engines. New AI crawlers appear regularly, so check the list now and then.
- `.well-known/tdmrep.json`, `ai.txt` and the `noai` / `tdm-reservation` meta tags in each page's `<head>` give the same opt-out in other machine-readable formats. Add the two meta tags to any new page.

## Domain (mjbcowan.com)

The `CNAME` file tells GitHub Pages to serve the site at `mjbcowan.com`. At your domain registrar, add:

| Type  | Host | Value                |
|-------|------|----------------------|
| A     | @    | 185.199.108.153      |
| A     | @    | 185.199.109.153      |
| A     | @    | 185.199.110.153      |
| A     | @    | 185.199.111.153      |
| CNAME | www  | mjbcowan.github.io   |

Once GitHub has issued the certificate, turn on **Settings → Pages → Enforce HTTPS**.
