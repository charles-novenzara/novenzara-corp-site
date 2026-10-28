# novenzara-corp-site

Corporate website for Novenzara, served as a static site by GitHub Pages.

## Structure

```
index.html          Home page
404.html            Not-found page (served automatically by GitHub Pages)
assets/css/         Stylesheets (design tokens at top of style.css)
assets/js/          Scripts
assets/img/         Images and favicon
robots.txt
.nojekyll           Tells Pages to serve files as-is (no Jekyll build)
```

No build step — edit the HTML/CSS/JS directly.

## Local preview

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Publishing with GitHub Pages

1. Repo **Settings → Pages**.
2. **Source:** "Deploy from a branch"; **Branch:** `main`, folder `/ (root)`.
3. The site appears at `https://charles-novenzara.github.io/novenzara-corp-site/` within a minute or two.

### Custom domain (optional)

Add a `CNAME` file at the repo root containing the domain (e.g. `www.novenzara.com`),
set the same domain under Settings → Pages, and configure DNS per
[GitHub's docs](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site).

> Note: `404.html` uses root-relative paths (`/assets/...`), which resolve correctly
> on a custom domain. Pages under `index.html` use relative paths and work either way.
