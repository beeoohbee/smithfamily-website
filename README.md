# smithfamily-website
Website for [smithfamily.co](https://smithfamily.co), built with [Jekyll](https://jekyllrb.com).

## Run locally

```sh
bundle install
bundle exec jekyll serve --livereload
```

Then open http://localhost:4000.

## Editing content

| What | Where |
|------|-------|
| Site title, contact email/phone, service area | `_config.yml` |
| Family members (About page) | `_data/team.yml` |
| Services (Services page + homepage highlights) | `_data/services.yml` |
| Page text | `index.html`, `about.html`, `services.html` |
| Styles / colors | `assets/css/main.css` |

Photos go in `assets/img/` and are referenced from `_data/team.yml` (e.g. `photo: /assets/img/bob.jpg`).

## Deployment

Pushing to `main` runs the **Deploy site to GitHub Pages** workflow (`.github/workflows/pages.yml`), which builds the site with the exact gems in `Gemfile.lock` and publishes it. Watch progress under the repo's **Actions** tab; a green check means it's live.

One-time setup, in the repo's **Settings → Pages**:

- **Source:** GitHub Actions
- **Custom domain:** `smithfamily.co` (also stored in the `CNAME` file), with **Enforce HTTPS** checked
- `url:` in `_config.yml` must match (`https://smithfamily.co`) so the sitemap and link previews use full addresses

### DNS for smithfamily.co

At your registrar, point the domain at GitHub Pages:

- `smithfamily.co` → `A` records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- `www.smithfamily.co` → `CNAME` to `beeoohbee.github.io`
