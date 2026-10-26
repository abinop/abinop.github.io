# abinop.github.io

One-page site for WordPress / WooCommerce maintenance services. Static HTML, no build step.

- `index.html` — the whole site, Greek by default; English via the EN button or `?lang=en`
- `img/alexandros.jpg` — profile photo
- `fonts/` — Commissioner and JetBrains Mono (OFL), Greek + Latin subsets, self-hosted for speed

## Speed check (hero terminal)

The checker calls the Google PageSpeed Insights API. Google's keyless quota is usually used up, so without a key it falls back to a link to pagespeed.web.dev.

To show results on the page itself:
1. Google Cloud Console → create a project → enable **PageSpeed Insights API**.
2. Credentials → **Create API key** → Application restrictions: **Websites**, add `https://abinop.github.io/*` → API restrictions: PageSpeed Insights API only.
3. Put the key in `index.html`: `var PSI_KEY = "...";` (it is public by design; the referrer restriction protects it).

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
