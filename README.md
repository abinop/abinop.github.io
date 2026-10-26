# abinop.github.io

One-page site for WordPress / WooCommerce maintenance services. Static HTML, no build step.

- `index.html` — the whole site, Greek by default; English via the EN button or `?lang=en`
- `img/alexandros.jpg` — profile photo

## Preview locally

```bash
python3 -m http.server 8765
```

Then open http://localhost:8765/

## Publish on GitHub Pages

1. Create the repo and push both branches:
   ```bash
   gh repo create abinop/abinop.github.io --public --source=. --push
   git push -u origin feature/portfolio-site
   ```
2. Open a PR from `feature/portfolio-site` into `main` and merge it:
   ```bash
   gh pr create --base main --head feature/portfolio-site --fill
   gh pr merge --merge
   ```
3. GitHub → repo **Settings → Pages** → Source: **Deploy from a branch**, Branch: `main`, folder `/ (root)` → Save.
4. After about a minute the site is live at https://abinop.github.io/
