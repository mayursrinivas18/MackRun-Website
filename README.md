# mackrun.tech

Single-page marketing site for MackRun, rewritten around the current focus:
**Achilles rehabilitation with physical therapy clinics**, with performance
teams as the next step.

Plain HTML, CSS and JavaScript in one file (`index.html`). No build step.
Images live in `images/` (no more base64 embedding), so the page stays small
and the browser can cache them.

```
mackrun-website/
  index.html        the whole site (styles and script inline)
  vercel.json       clean URLs, image caching, basic security headers
  images/           ankle-pod.png, og-image.png, optional logo.svg (see images/README.md)
```

## Before you deploy

1. **Contact form (Formspree).** Create a form at formspree.io, copy its ID, and
   replace `YOUR_FORM_ID` in `index.html`:
   `action="https://formspree.io/f/YOUR_FORM_ID"`.
   Until you do, the form tells visitors to email you instead of failing silently.
2. **Email address.** Replace `hello@mackrun.tech` (3 places in `index.html`) with
   the inbox you actually read.
3. **Images.** Add `images/ankle-pod.png` and `images/og-image.png`
   (details in `images/README.md`). Without the render, the hero shows a drawn
   pod illustration.
4. **Logo.** The header, footer and browser-tab icon use your MackRun logo (the M
   with the EKG trace, in #E9FFFF and #00FFFF), drawn inline as SVG so it stays
   sharp at any size. A standalone copy is in `images/logo.svg`.

## Deploy on Vercel

- Existing project: replace your current `index.html` with this one, add the
  `images/` folder and `vercel.json`, and push (or drag the folder into the
  Vercel dashboard).
- New project: `npx vercel` in this folder, then attach `mackrun.tech` under
  Project > Settings > Domains.

## Editing content

Each section of `index.html` is marked with a comment
(`<!-- ===== Hero -->`, `<!-- ===== For clinics -->`, ...).

- **Colors** match mackrun.tech and are variables at the top of the `<style>` block:
  base #080810, surface #0C0C1A, card #10101F, cyan #00D4FF (and #0099CC),
  text #FFFFFF / #B8BDD6 / #9BA3C4, plus the faint 60 px cyan grid background.
- **The recovery chart** in the hero is an illustrative example drawn in SVG.
  Replace it with real (anonymized, consented) pilot data once you have it.
- **The dashboard mockup** uses fictional patients.

## Content notes (read before changing the copy)

- **Patents.** The site deliberately stays at a "what it does for clinics"
  level. Keep sensor specifications, sampling rates, algorithms and
  signal-processing methods off the site until your provisional patent
  filing is in, since public disclosure can affect what you can claim.
- **Regulatory.** MackRun isn't FDA-cleared, so the copy describes what it
  measures and shows, not what it diagnoses, treats or prevents. The FAQ and
  footer say so explicitly. Keep "prevents injury", "detects inflammation",
  "diagnoses" and similar claims out of the copy.
- **Names and partners.** Don't name teams, clinics or universities (including
  past pilots) without their written permission.
- **Promises.** Battery life, waterproofing and billing or reimbursement are
  described as goals or left out until pilot units confirm them.

## Built in

- The mackrun.tech dark theme with its cyan accent and grid background
- Responsive down to small phones; the chart and dashboard scroll sideways on narrow screens
- Keyboard focus styles, skip link, reduced-motion support (the chart draws in
  once on load, or appears instantly if the visitor prefers reduced motion)
- Typefaces: Big Shoulders Display (headings) and Source Serif 4 (text), from Google Fonts
