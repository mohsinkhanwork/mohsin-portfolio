# Mohsin Khan — Portfolio

Personal portfolio site. One self-contained `index.html` — no build step, no dependencies, no framework. Drop it on any host and it works.

**Live:** https://mohsinkhanwork.github.io/mohsin-portfolio/

---

## Files

```
index.html                 the whole site (HTML + CSS + JS in one file)
Mohsin_Khan_Resume.pdf     linked from the "Download résumé" button
.nojekyll                  tells GitHub Pages to serve files as-is
README.md
```

## Deploy to GitHub Pages

```bash
cd mohsin-portfolio
git init
git add .
git commit -m "Portfolio site"
git branch -M main
git remote add origin https://github.com/mohsinkhanwork/mohsin-portfolio.git
git push -u origin main
```

Then in the repo: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)` → Save.**
It goes live at `https://mohsinkhanwork.github.io/mohsin-portfolio/` in about a minute.

If the repo already has commits, use `git push -u origin main --force` on the first push or pull and merge first.

### Custom domain

Add a file named `CNAME` containing only your domain (e.g. `mohsinkhan.dev`), point an `A` record at GitHub's Pages IPs, then set the domain under Settings → Pages.

## Editing the content

Everything lives in `index.html` and is grouped under commented section banners:

| Section | What to edit |
|---|---|
| `TOKENS` (top of `<style>`) | Colours, fonts, max width — change `--signal` to reskin the accent |
| `HERO` | Name, headline, availability status |
| `SIGNATURE` (the `<svg>`) | The architecture diagram — node labels are plain `<text>` elements |
| `WORK` | Project cards. Copy one `<article class="card">` block to add a project |
| `EXPERIENCE` | Job entries, one `<article class="job">` each |
| `STACK` | Skill groups and credentials |
| `CONTACT` | Email, phone, profile links |

**To add a project:** duplicate a card block and set `data-cat` to one of `erp`, `ecom`, `edu`, `infra` so the filter buttons pick it up.

**To change the accent colour:** edit `--signal` (currently amber `#F2B441`) and `--trace` (cyan `#4FC3E8`) in `:root`.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Notes

- Responsive down to 360px; the hero architecture diagram swaps to a stacked flow list below 880px.
- Respects `prefers-reduced-motion` — all animation is disabled for users who ask for it.
- Keyboard accessible with a skip link and visible focus rings.
- Includes Open Graph tags and JSON-LD `Person` schema for search and link previews.
- Fonts load from Google Fonts; the site falls back to system faces if that's blocked.

---

Contact: mkhan9658@gmail.com · [Upwork](https://www.upwork.com/freelancers/~01eda4bc15038bc4e7) · [LinkedIn](https://www.linkedin.com/in/mohsin-khan-22468017b/)
