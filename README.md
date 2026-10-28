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
CNAME               Custom domain for GitHub Pages
sitemap.xml         List of pages for search engines
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
3. **Custom domain:** `novenzara.com` (already set via the `CNAME` file), then tick **Enforce HTTPS** once the certificate is issued.

The site is served at **https://novenzara.com**.

### DNS (at the domain registrar)

| Type  | Host  | Value                      |
|-------|-------|----------------------------|
| A     | `@`   | `185.199.108.153`          |
| A     | `@`   | `185.199.109.153`          |
| A     | `@`   | `185.199.110.153`          |
| A     | `@`   | `185.199.111.153`          |
| AAAA  | `@`   | `2606:50c0:8000::153`      |
| AAAA  | `@`   | `2606:50c0:8001::153`      |
| AAAA  | `@`   | `2606:50c0:8002::153`      |
| AAAA  | `@`   | `2606:50c0:8003::153`      |
| CNAME | `www` | `charles-novenzara.github.io` |

Remove any other A/AAAA/CNAME records for `@` and `www` that point elsewhere.
With `www` set up, GitHub redirects `www.novenzara.com` to `novenzara.com` automatically.
See [GitHub's docs](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site)
for details, including verifying the domain to protect against takeover.
