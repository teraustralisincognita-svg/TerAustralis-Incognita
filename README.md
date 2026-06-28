# TerAustralis Incognita — Website

A static marketing site for **TerAustralis Incognita**, a coordination and
advocacy initiative for sovereign Australian space capability — built on the onshore
recovery, refining and processing of critical minerals and rare earths.

Dark, cosmic, deliberately understated: a cosmic black canvas with violet + pink nebula light, an aurora-green and a warm amber accent, over a gently animated starfield. No build step, no framework — just HTML and Tailwind via CDN, so it
hosts anywhere.

> _Songlines to Starlines · Red Dust to Rockets · Dreamtime to Deep Space_

---

## Pages

| File | Page |
|------|------|
| `index.html` | Home — hero + sovereign-space lead, overview, "why now" |
| `vision.html` | Vision — what it is, minerals-to-space, the coordination/advocacy role |
| `foundations.html` | Foundations — the principles (consent, honesty, partnership) |
| `approach.html` | Approach — how it works, phased compliance, FPIC, Second Founding |
| `momentum.html` | Momentum — honest progress, receipts, what's next |
| `get-involved.html` | Get Involved — audiences, expression-of-interest form, contact |
| `support.html` | Support — kickstart fund, recurring backer tiers, sponsor tiers (Open Collective) |

The navigation and footer are identical on every page (each file is fully
self-contained), so you can add, remove or rename pages by editing those blocks
consistently across the set.

---

## Run it locally

It's plain static files — no install, no build.

**Option A — just open it.** Double-click `index.html`, or drag it into a browser.

**Option B — run a tiny local server** (recommended; makes links behave exactly as in
production). From inside the project folder:

```bash
# Python 3 (already on most machines)
python3 -m http.server 8000
```

Then visit <http://localhost:8000>. Other options if you prefer:

```bash
npx serve          # Node
php -S localhost:8000   # PHP
```

---

## Deploy

### GitHub Pages
1. Create a repo and push these files to the `main` branch (keep `index.html` in the root).
2. In the repo: **Settings → Pages**.
3. Under **Build and deployment**, set **Source = Deploy from a branch**, then choose
   **Branch: `main`** and **Folder: `/ (root)`**, and save.
4. Your site appears at `https://<username>.github.io/<repo>/` within a minute or two.

### Vercel
- **Easiest:** go to <https://vercel.com>, import the GitHub repo (or drag-and-drop the
  folder), and accept the defaults — no framework, no build command, output is the root.
- **CLI:**
  ```bash
  npm i -g vercel
  vercel        # from the project folder; accept the defaults
  ```

Netlify, Cloudflare Pages, GitLab Pages, or any static host work the same way: point
them at the folder, no build command needed.

---

## Before you launch — please update these

A few intentional placeholders are left for you. Each is flagged with a `TODO` comment
in the HTML so it's easy to find (search the files for `TODO`).

1. **Foundations copy (`foundations.html`).** The page currently contains a *draft*
   placeholder, clearly marked between `BEGIN PLACEHOLDER` / `END PLACEHOLDER` comments.
   It ends on your exact closing sentence, but the paragraphs above it are placeholder
   wording. **Replace the draft with your final, approved Foundations text** before going
   live.

2. **Second Founding link.** Every "Second Founding" link uses `href="#"` (see the
   `TODO` comments in the footer of each page, in `approach.html`, and in
   `get-involved.html`). Swap `#` for the real URL once confirmed.

3. **Expression-of-interest form (`get-involved.html`).** A static site has no backend,
   so the form needs an endpoint. The `action` is set to a Formspree placeholder
   (`https://formspree.io/f/your-form-id`). Create a free form at
   <https://formspree.io> (or use Netlify Forms / Getform / Basin / an embedded Google
   Form) and paste your endpoint into the `action` attribute.

4. **Momentum details (`momentum.html`).** The progress items are written truthfully but
   generally. Add real dates, publication names and specifics as each item is confirmed
   or published.

---

## Note on Tailwind

This site loads Tailwind from the CDN (`https://cdn.tailwindcss.com`) for zero-setup
hosting. In the browser console you'll see a note that the CDN build isn't meant for
production — that's expected and harmless for a site this size.

When you want the smaller, faster production build, switch to compiled Tailwind: install
it, move the `tailwind.config` (currently inline in each page's `<head>`) into a
`tailwind.config.js`, and replace the CDN `<script>` with your generated stylesheet.
See <https://tailwindcss.com/docs/installation>.

---

## Editing tips

- **Colours and fonts** live in the inline `tailwind.config` in each page's `<head>`
  (`space`, `violet`, `pink`, `green`, `amber`, `silver`, `ink`, `muted`; Space Grotesk for display, Inter for
  body). Keep them in sync across pages.
- **The animated starfield** lives entirely in the inline `<style>` block: the
  `.star-field::before` / `::after` layers (two parallax star fields), the `.hero-glow`
  nebula, the `.shooting-star` streak, and the `.cosmic` gradient used on the headings.
  Tune density with the `background-size` values, speed with the `starDrift` / `twinkle` /
  `shoot` keyframe durations, and colour with the rgba stops. All motion is disabled under
  `prefers-reduced-motion`.
- **Accessibility** is built in: a skip link, visible gold focus rings, an accessible
  mobile menu toggle, and labelled form fields. Preserve these if you refactor.

---

## Licensing & intellectual property

This project is **dual-licensed**, with the code and the written content under
different terms:

| What | Licence | What it allows |
|------|---------|----------------|
| **Site source code** (HTML, config, styles, scripts) | Proprietary — all rights reserved (`LICENSE`) | View source for personal reference only. No copying, redeploying, or building a derivative/competing site without written permission. |
| **Written content** (vision text, Foundations, messaging) | [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/) (`LICENSE-CC-BY-NC-ND-4.0`) | Share with **attribution**, **non-commercial** use only, and **no derivatives** (no altered re-publishing). |

© 2026 **Crystal Elle Arena-Turner**, trading as **TerAustralis Incognita**.

### A note on what licensing does (and doesn't) do

A licence does **not** physically prevent anyone from copying the site — anyone can
"view source." What it does is set the legal terms for reuse and give you standing
if someone breaches them. The terms above are restrictive (share-with-credit only,
no commercial use, no derivatives), but they are not a technical lock.

### Trademark

**TerAustralis Incognita™** — the name and the logo are claimed as trademarks of the
project. The ™ symbol signals an unregistered claim. For enforceable protection,
register the word mark (and logo) with **IP Australia**
(<https://www.ipaustralia.gov.au>) in the relevant classes. Copyright in the text and
code is automatic and already owned; trademark is what protects the brand identity,
and registration is a separate, recommended step.
