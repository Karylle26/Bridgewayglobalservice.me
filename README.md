# Bridgeway Global Services — bridgewayglobalservices.me

Website for Bridgeway Global Services d.o.o. — visa, residence permit (boravak) and working permit processing in Podgorica, Montenegro.

## What's here

```
index.html          The whole website — HTML, CSS and JavaScript in one file
CNAME               Tells GitHub Pages which domain to serve
assets/partners/    Partner logo images (see "Missing images" below)
```

Everything is in one file on purpose. No build step, no npm, no framework — open `index.html` in a browser and it works.

## Missing images

The partner logos are not in this repo yet. Download them from the live site and put them in `assets/partners/`:

| File | Source |
|---|---|
| `noa.jpg` | https://bridgewayglobal.services/assets/partners/noa.jpg |
| `wulfenia.jpg` | https://bridgewayglobal.services/assets/partners/wulfenia.jpg |
| `casa-del-mare.jpg` | https://bridgewayglobal.services/assets/partners/casa-del-mare.jpg |
| `gastro-pub.jpg` | https://bridgewayglobal.services/assets/partners/gastro-pub.jpg |
| `talia.jpg` | https://bridgewayglobal.services/assets/partners/talia.jpg |
| `heritage-grand.jpg` | https://bridgewayglobal.services/assets/partners/heritage-grand.jpg |
| `uniqa.png` | https://bridgewayglobal.services/assets/partners/uniqa.png |
| `adriatica.jpg` | https://bridgewayglobal.services/assets/partners/adriatica.jpg |
| `palm-beach.jpg` | https://bridgewayglobal.services/assets/partners/palm-beach.jpg |
| `la-unica.jpg` | https://bridgewayglobal.services/assets/partners/la-unica.jpg |

Also add `assets/og-image.png` (1200×630) — the preview image shown when the link is shared on Facebook, LinkedIn or WhatsApp.

## Publishing it

1. Commit and push this folder to GitHub.
2. On GitHub: **Settings → Pages → Source: Deploy from a branch → `main` / root**.
3. At your domain registrar, point `bridgewayglobalservices.me` to GitHub Pages:
   - `A` records for the root domain → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` record for `www` → `Karylle26.github.io`
4. Back in **Settings → Pages**, tick **Enforce HTTPS** once the certificate is issued (can take up to an hour).

## Contact forms

The two forms currently validate the input and show a success message, but **they do not send anything anywhere yet**. To make them deliver real emails, connect them to a form service — Formspree, Web3Forms and Netlify Forms all work with a plain HTML site. Look for the `TODO` comment near the bottom of `index.html`.

## Editing content

Common things to change, all inside `index.html`:

- **Stat numbers** — search for `data-count` in the hero section
- **Services** — the six `<div class="svc-card">` blocks
- **Process steps** — the four `<div class="step">` blocks
- **Contact details** — the `#contact` section
- **Brand colours** — the `:root` block at the top of the `<style>` tag (`--green-900` and `--gold`)
