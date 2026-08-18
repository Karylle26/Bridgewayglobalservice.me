# Bridgeway Global Services — bridgewayglobalservices.me

The company website. One HTML file, no build step, no framework.

---

## How the whole thing is wired

Four separate pieces, each doing one job:

| Piece | What it does | Where |
|---|---|---|
| **Cowork** | Where Claude edits the site with you | Claude desktop app, connected to the folder below |
| **The folder** | The actual files, on your PC | `Documents\GitHub\Bridgewayglobalservice.me` |
| **GitHub Desktop** | Sends the folder up to GitHub | App on your PC |
| **GitHub Pages** | Hosts and serves the website, free | `github.com/Karylle26/Bridgewayglobalservice.me` |
| **GoDaddy** | Owns the domain name and points it at GitHub | Domain: `bridgewayglobalservices.me` |

GoDaddy only sells the address. GitHub Pages is the building. Cowork is where the work happens.

---

## The everyday loop

1. Ask Claude in Cowork for a change
2. Claude edits `index.html` directly in your folder
3. Open `index.html` by double-clicking it, to see the change
4. Happy? Open **GitHub Desktop** → type a short summary → **Commit to main** → **Push origin**
5. Wait ~2 minutes, then load the site with **Ctrl + Shift + R**

**Commit saves to your computer. Push sends it to GitHub.** Both are needed — this is the step most often missed.

Before pushing, you can say **"check the site"** to Claude. It runs a full health check and tells you whether local and live match.

---

## If a commit fails with "lock file already exists"

Close GitHub Desktop completely, then run this in PowerShell:

```powershell
Remove-Item "C:\Users\Radan\Documents\GitHub\Bridgewayglobalservice.me\.git\index.lock" -Force
```

Silence means it worked. Reopen GitHub Desktop and commit again.

---

## What's in here

```
index.html            The entire website — HTML, CSS and JavaScript in one file
CNAME                 Tells GitHub which domain to serve
.gitignore            Keeps internal documents out of the public site
assets/
  logo.png            Header mark
  favicon*.png/.ico   Browser tab icons
  apple-touch-icon    iPhone home-screen icon
  og-image.png        The preview card when the link is shared
  partners/           The ten partner logos, 400×400 each
```

---

## The page, top to bottom

Header (logo, menu, ENG/ME toggle, social, contact button) → hero with three statistics → Mission &amp; Vision → six services → partner grid → contact → footer.

---

## Editing things yourself

All inside `index.html`:

| To change | Look for |
|---|---|
| The three hero numbers | `data-count` — **these are placeholders, replace with real figures** |
| Services | the six `svc-card` blocks |
| Partners | the `pcard` blocks in the partners section |
| Contact details | the `way` blocks |
| Montenegrin translations | `var ME = {` near the bottom |
| Brand colours | the `:root` block at the top of `<style>` |

---

## Still outstanding

- **The hero statistics are invented.** 180 visas, 98% approval, 21 days — replace all three with real numbers before promoting the site.
- **Have a native speaker check the Montenegrin.** Especially *boravak*, *radna dozvola*, *jedinstvena dozvola*.
- **Holiday MNE's logo is 150×150** while the others are 400×400, so it looks softer. Replace when you have a bigger file.
- **No permit counts on the partner tiles yet** — hovering shows the category. Real counts per employer would be stronger.

---

## Publishing settings, for reference

GitHub → repo → **Settings → Pages**: source is *Deploy from a branch*, branch `main`, folder `/ (root)`, custom domain `bridgewayglobalservices.me`.

GoDaddy DNS holds four `A` records on `@` pointing to `185.199.108.153`, `.109.153`, `.110.153`, `.111.153`.
