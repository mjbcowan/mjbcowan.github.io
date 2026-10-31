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

- **Update the CV PDF:** replace `assets/cv.pdf`. Every "Download CV" link points to it.
- **Add the real images:** save them as `assets/portrait.jpg` and `assets/fig-01.jpg` … `fig-04.jpg`, then change the matching `src="assets/….svg"` in `index.html` to `.jpg`. Images are shown in greyscale automatically.
  - `fig-01`: full-width banner, about 21:9.
  - `portrait`: about 4:3.
  - `fig-02` … `fig-04`: publication tiles, about 4:5.
- **Paper links:** search `index.html` for `TODO`. Replace each `<a class="todo" aria-disabled="true">paper</a>` with `<a href="https://…">paper</a>`, and do the same for `doi`.
- **Add a ledger row** (Experience, Education or Leadership): copy an existing `<div class="ledger-row">` block.

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
