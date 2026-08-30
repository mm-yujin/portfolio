# 김유진 — Portfolio

Single-page portfolio in two languages. No build step, no external dependencies.

| File | |
|---|---|
| `index.html` | English — for r/INAT and English-speaking teams |
| `index.ko.html` | 한국어 — same content |
| `assets/` | 41 screenshots (~1.3 MB), extracted from the Korean PDF portfolio |
| `REDDIT_POST.md` | r/INAT post draft |
| `_unused/` | pulled from the page but kept locally; git-ignored, never published |

Both pages share `assets/` and link to each other through the EN/KO switch in the
top-right corner. `index.html` is the default page, so the GitHub Pages URL lands on
English; the Korean version is at `.../index.ko.html`.

**Edits have to be made in both files** — they are independent HTML, not a template.

## Deploy to GitHub Pages

```bash
git init && git add . && git commit -m "Add English portfolio"
```

Then create an empty repo on GitHub (name it `portfolio`, or `<username>.github.io`
if you want it at the root of your account), and push:

```bash
git remote add origin https://github.com/YOUR-USERNAME/portfolio.git && git branch -M main && git push -u origin main
```

Finally, on GitHub: **Settings → Pages → Source: Deploy from a branch → `main` / `(root)` → Save**.
The page goes live at `https://YOUR-USERNAME.github.io/portfolio/` in a minute or two.

## Export a PDF

Open `index.html` in Chrome → `Ctrl+P` → **Destination: Save as PDF**. The print
stylesheet switches to a light document layout, shrinks screenshots, and keeps cards
from splitting across pages, so leave *Background graphics* **off** for the cleaner result.

## Things to fill in before publishing

Search **both** `index.html` and `index.ko.html` for `EDIT:` — three spots each:

1. **Header buttons** — GitHub / Discord / itch.io links (commented out).
2. **Availability** — the "Commitment" line under *What I'm looking for* currently says
   "part-time, outside of working hours". Put real hours there if you're comfortable
   (e.g. "~10 hrs/week"); INAT readers weigh that heavily.
3. **Footer contact** — a Discord handle if you want DMs there instead of email.

Your phone number is deliberately **not** on the page — it is a public URL.

## Screenshots

`assets/` is named by project prefix: `pinkrobot-`, `drb-` (Disney Realm Breakers),
`csb-` (Cheonsangbi M), `ff7-`, `tunic-`, `fps-`, `momo-`. To swap one out, replace the
file and keep the name — no HTML change needed. To add one, copy an existing block:

```html
<div class="shots shots-2">
  <figure class="shot">
    <img src="assets/your-file.jpg" alt="What it shows" loading="lazy">
    <figcaption>One line of context.</figcaption>
  </figure>
</div>
```

Grid classes: `shots-1` (full width), `shots-2`, `shots-3`.

Figure classes control scaling. Plain `class="shot"` stretches the image to the full
column width, which **upscales and blurs anything narrower than the column** (~880 px at
`shots-1`). Use `class="shot nat"` for small images so they render at native size,
`class="shot p"` for portrait phone captures, and `class="shot tall"` for very tall images.

**Before publishing, check these are all cleared for public use.** They are captures of
shipped builds, which is normal portfolio practice, but The Pink Robot was still in
prototype/demo when you worked on it — make sure every Pink Robot shot matches what is
already public on the Steam page or the demo.
