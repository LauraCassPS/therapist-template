# Therapist One-Page Site Template

A single-file, static HTML/CSS template for a solo therapist or small counseling
practice. Built as a clean, elegant base you can copy per client and fill in.

Originally modeled on the layout of a Squarespace therapy site, then rebuilt from
scratch as hand-written HTML/CSS (no build step, no framework, no dependencies
except two Google Fonts).

---

## What's in here

| File | Purpose |
| --- | --- |
| `index.html` | The whole site — markup, styles (in a `<style>` block), and a tiny vanilla-JS snippet. |
| `README.md` | This file. |
| `.gitignore` | Keeps OS/editor cruft out of the repo. |

To preview: just open `index.html` in a browser. To publish: drop the folder on
any static host (Netlify, Cloudflare Pages, GitHub Pages, S3, plain shared hosting…).

---

## Make a new client site in ~15 minutes

1. **Copy the folder** and rename it for the client.
2. **Find & replace the bracketed placeholders** throughout `index.html`:
   `[Practice Name]`, `[Therapist Name]`, `[Credentials]`, `[City]`, `[State]`,
   `[ZIP]`, `[Street Address]`, the email (`hello@example.com`), the phone
   (`(000) 000-0000` / `+10000000000`), and the social URLs.
3. **Edit the copy** in each `<section>` — headlines and body text are plain HTML.
4. **Swap the image placeholders.** Every gray `<div class="ph …">` block marks
   where a photo goes and notes the shape. Replace each with a real image, e.g.:
   ```html
   <img src="images/hero.jpg" alt="Therapy office in Fort Lauderdale"
        width="1600" height="700" loading="lazy" decoding="async" />
   ```
   Shapes used: `wide` ≈ 16:7 (hero), `portrait` ≈ 4:5 (headshots), `square` (service cards).
5. **Rebrand the colors & fonts** from the CSS custom properties in `:root` at the
   top of the `<style>` block (`--ink`, `--plum`, `--accent`, `--paper`, etc.) and
   the two `--serif` / `--sans` font stacks (plus the Google Fonts `<link>`).
6. **Update SEO:** the `<title>`, `<meta name="description">`, the `og:` / `twitter:`
   tags, `<link rel="canonical">`, the favicon links, and — importantly — the
   **JSON-LD structured-data block** near the bottom of `<head>` (this is what lets
   Google show the practice's name, address, phone and hours in search/maps).
   Validate it at <https://search.google.com/test/rich-results>.
7. **Add icons:** drop a `favicon.ico` and a 512×512 `icon.png` next to `index.html`,
   and a `social-preview.jpg` (1200×630) for link previews.
8. **Connect the contact form** — see below.

---

## The contact form

The "Reach Out Today" section has a styled form that is **not wired up** out of the
box (submitting it just shows an alert). To make it actually send:

1. Create a free account with a form backend — e.g. [Formspree](https://formspree.io),
   [Basin](https://usebasin.com), [Web3Forms](https://web3forms.com), or use
   [Netlify Forms](https://docs.netlify.com/forms/setup/) if you host on Netlify.
2. Put its endpoint URL in the form's `action` attribute and **remove the
   `onsubmit="…"` attribute**.
3. Leave the hidden `company` honeypot field in place — it silently catches spam bots.

---

## Accessibility / SEO niceties already baked in

- Semantic landmarks: `<header>`, `<nav aria-label>`, `<main>`, `<footer>`.
- "Skip to content" link for keyboard users; visible focus styles.
- Accessible mobile menu (`aria-expanded`, closes on `Esc` / link tap).
- `prefers-reduced-motion` respected (disables smooth scroll + transitions).
- Open Graph + Twitter Card meta, canonical URL, `theme-color`, `robots`.
- JSON-LD `MedicalBusiness` / `ProfessionalService` structured data.
- Honeypot anti-spam field on the form.
- Sensible heading hierarchy (one `<h1>`, `<h2>` per section, `<h3>` within).

---

## Notes

- No license — all rights reserved. This is a private working template.
- Tested in current Chrome, Safari, Firefox and Edge. Uses `aspect-ratio` and CSS
  custom properties (fine in any browser from ~2021 onward).
- Keep `index.html` readable — it's meant to be edited by hand, not minified.
