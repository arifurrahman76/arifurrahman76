# Md. Arifur Rahman — Personal Academic Website

Personal portfolio for Md. Arifur Rahman, veterinarian and researcher in poultry disease diagnostics, veterinary microbiology and molecular diagnostics (Dhaka, Bangladesh).

Single-page static site with no build step and no dependencies. It features a DNA-themed design (animated double helix, scrolling A/T/G/C strip, helix-cutout headings), optional sound effects, light and dark themes, and a filterable publication list where every entry is a link.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The whole site: HTML, CSS and JavaScript in one file |
| `portrait.jpg` | Profile photo shown in the hero section |
| `README.md` | This file |

## Deploy on GitHub Pages

1. Create a new public repository named `<your-github-username>.github.io`.
2. Upload `index.html`, `portrait.jpg` and `README.md` to the repository root.
3. Go to **Settings → Pages**, set **Source** to **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute or two the site is live at `https://<your-github-username>.github.io`.

## Preview locally

Open `index.html` in any browser. To serve it over HTTP instead, run this in the project folder:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Customising

All content is edited directly in `index.html`.

**Publications.** Near the top of the `<script>` block, the `PUBS` array holds published papers and `REV` holds manuscripts under review. Each entry looks like this:

```js
{y:2026, t:"Paper title", j:"Journal, volume, pages", a:"Authors"}
```

Links are generated automatically as Google Scholar searches for the title. To use a direct link, replace the `.map(p=>({...p,url:sc(p.t)}))` step, or add a `url` to an entry and change the mapping to keep it, for example:

```js
].map(p=>({...p, url: p.url || sc(p.t)}))
```

Then add `url:"https://doi.org/..."` to each entry.

**Skills and interests.** Edit the `SKILLS` object and the `INT` array in the same script block.

**Education, experience, awards, contact.** These are plain HTML sections in `index.html`. Search for the section `id` (`education`, `experience`, `awards`, `contact`) and edit the text.

**Profile links.** In the Contact section, replace the Google Scholar, ResearchGate and LinkedIn search links with your actual profile URLs.

**Photo.** Replace `portrait.jpg` with a new image of the same filename. A portrait with a 4:5 aspect ratio works best.

**Colours.** The palette is defined as CSS variables at the top of the `<style>` block (`--a`, `--b`, `--c`, `--d`). The four accent colours match the A, T, G, C bases in the sequence strip.

**Adding a CV download.** Upload your CV as `cv.pdf` to the repository, then add this to the nav or contact section:

```html
<a href="cv.pdf" download>Download CV ↓</a>
```

## Features

- Responsive layout for desktop and mobile
- Light and dark themes, following the system setting with a manual toggle
- Sound effects built with the Web Audio API (no audio files). They are off by default and can be switched on with the speaker button in the nav bar.
- Respects the `prefers-reduced-motion` setting by disabling animations
- Year filters for the publication list (All, 2026, 2025, Under review)

## Browser support

Works in current versions of Chrome, Edge, Firefox and Safari.

## Notes

- Referee details from the CV are intentionally not published on the site.
- Manuscripts marked "Under review" are not published papers.

## License

© Md. Arifur Rahman. All rights reserved. Please do not reuse the photo or text without permission.
