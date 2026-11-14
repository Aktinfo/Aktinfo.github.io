# aktinfo.github.io

Personal site for **Ashwani Kant Tiwari** — Database Developer / Data Analyst / MSBI.
Static HTML + CSS only: no build step, no framework, no dependencies.

Live: **https://aktinfo.github.io/**

## Files — everything sits at the repo root

```
index.html                        the whole site (single page)
style.css                         styles: layout, responsive, print
ashwani-kant-tiwari-resume.pdf    Full résumé (designed)
msbi-developer-resume.pdf         MSBI Developer (ATS)
data-analyst-resume.pdf           Data Analyst (ATS)
etl-developer-resume.pdf          ETL Developer (ATS)
.nojekyll                         tells GitHub Pages to serve files as-is
README.md
```

The layout is deliberately flat: GitHub's web uploader cannot preserve nested
folders, so keeping files at the root means the site can be re-uploaded entirely
from a browser without git.

## Run locally

Open `index.html` directly, or serve the folder:

```powershell
python -m http.server 8137 --directory "C:\Users\pixel\Documents\Default Project\site"
```

Then open http://localhost:8137

## Publishing

Already live at https://aktinfo.github.io/ (repo: `Aktinfo/Aktinfo.github.io`,
branch `main`, Pages source = root).

To publish a fresh copy from the browser:

1. https://github.com/Aktinfo/Aktinfo.github.io/upload/main
2. Drag in all files from this folder
3. Commit changes
4. Settings → Pages → Deploy from a branch → `main` / `(root)` → Save

To publish via git:

```powershell
cd "C:\Users\pixel\Documents\Default Project\site"
git remote add origin https://github.com/Aktinfo/Aktinfo.github.io.git
git branch -M main
git push -u origin main
```

## Updating a résumé

Replace the PDF here, keeping the exact filename, then re-upload that one file
through the GitHub web UI (or `git add -A`, `git commit`, `git push`).
Keep the filename unchanged and the site needs no edits.

## Custom domain (optional)

1. Buy a domain, e.g. `ashwanikanttiwari.com`.
2. Repo → Settings → Pages → **Custom domain** → enter it → Save.
3. At the registrar add the records GitHub shows:
   - `A` on the apex → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` for `www` → `aktinfo.github.io`
4. Tick **Enforce HTTPS** once the certificate is issued.
5. Then update `canonical`, `og:url` and the JSON-LD `url` in `index.html`.

## Editing notes

- Résumé links are relative, so the site also works from a subfolder.
- The 5 certification links point at real verification URLs (Microsoft Learn, Credly, Kaggle).
- Print styles strip the nav, buttons and download grid, so Ctrl+P gives a clean summary.
