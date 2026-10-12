# smithfamily-website
GitLab Pages website for [smithfamily.co](https://smithfamily.co), built with [Jekyll](https://jekyllrb.com).

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

Pushing to the default branch runs `.gitlab-ci.yml`, which builds the site into `public/` and publishes it to GitLab Pages. Other branches just run a test build.

### Custom domain (smithfamily.co)

In GitLab: **Deploy → Pages → New Domain**, add `smithfamily.co` (and optionally `www.smithfamily.co`), then add the DNS records GitLab shows you at your registrar:

- `smithfamily.co` → `A` record to `35.185.44.232`
- `_gitlab-pages-verification-code.smithfamily.co` → `TXT` record with the verification code
- `www.smithfamily.co` → `CNAME` to `<namespace>.gitlab.io`

Leave "Automatic certificate management using Let's Encrypt" enabled for HTTPS.
