# davisliggett.com

Personal links page for Davis Liggett, served by GitHub Pages at [davisliggett.com](https://davisliggett.com).

## What's here

| File | Purpose |
|---|---|
| `index.html` | The whole site: markup, styles, and inline SVG icons in one file |
| `avatar.jpg` | Profile photo |
| `electindex.png` | ElectIndex logo used on the featured card |
| `og.png` | 1200x630 share image for link previews |
| `favicon.svg`, `favicon-32.png`, `favicon-192.png`, `apple-touch-icon.png` | DLG monogram icons |
| `robots.txt`, `sitemap.xml` | Search engine hints |
| `CNAME` | Custom domain for GitHub Pages (managed by GitHub, do not edit by hand) |

There is no build step and no JavaScript. The only external request is the Manrope font from Google Fonts, with Helvetica and Arial as fallbacks.

## Editing

Open `index.html`. Links live in the `<ul class="links">` list, one `<li>` per card. Each card has a logo tile, a title, a short description, and a handle on the right. Header copy, role pills, and locations are in the `<header>` block. Colors and spacing are CSS variables at the top of the `<style>` block.

To preview locally:

```sh
python3 -m http.server 8765
```

Then open http://127.0.0.1:8765/ in a browser.

## Deploying

Push to `main`. GitHub Pages builds and publishes within about a minute.

GitHub writes its own commits to this repo whenever the Pages custom domain changes, so run `git pull --rebase` before pushing if a push is rejected.

## Domain

DNS is on Cloudflare. The apex uses DNS-only A and AAAA records pointing at GitHub Pages, which issues the HTTPS certificate. The `www` subdomain is proxied through Cloudflare and redirected to the apex by a Cloudflare redirect rule. The `_github-pages-challenge-daveslosttt` TXT record verifies the domain to this GitHub account and should stay in place.
