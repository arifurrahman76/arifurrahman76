# Md. Arifur Rahman — Personal Academic Website (Dark "Zone of Inhibition" Theme)

Dark, single-page portfolio for Md. Arifur Rahman, veterinarian and researcher in poultry disease diagnostics, veterinary microbiology and molecular diagnostics (Dhaka, Bangladesh).

## Theme

The design is built around an antibiotic susceptibility test:

- Your photo sits on the antibiotic disc in the middle of a live Petri dish, with a dashed ring marking the zone of inhibition.
- Glowing bacterial colonies grow around the zone. Hover over a colony to speed it up, or click the plate to inoculate new ones.
- Section dividers are gel electrophoresis lanes.
- Each publication has a glowing "band" whose length reflects its recency.

No build step and no dependencies.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The whole site: HTML, CSS and JavaScript |
| `portrait.jpg` | Profile photo shown on the antibiotic disc |
| `README.md` | This file |

## Deploy on GitHub Pages

1. Create a public repository named `<your-github-username>.github.io`.
2. Upload `index.html`, `portrait.jpg` and `README.md` to the repository root.
3. Go to **Settings → Pages**, set **Source** to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. The site goes live at `https://<your-github-username>.github.io` after a minute or two.

To preview locally, run `python3 -m http.server 8000` in the folder and open `http://localhost:8000`.

## Customising

- **Publication links:** every entry opens a Google Scholar search for its title. In the `PUBS` array in the script, add `url:"https://doi.org/..."` to an entry to use a direct link instead.
- **Skills and interests:** edit the `SK` object and `INT` array in the script.
- **Education, experience, awards, contact:** plain HTML sections in `index.html`. Search for the section `id`.
- **Profile links:** replace the Scholar, ResearchGate and LinkedIn search links in the Contact section with your real profile URLs.
- **Colours:** change the CSS variables at the top of the `<style>` block (`--g`, `--am`, `--mg`, `--cy`).
- **Dish behaviour:** in the script, `spawn()` creates colonies, `ZONE` sets the inhibition radius, and the loop cap (`cols.length<90`) limits colony count.
- **CV download:** upload `cv.pdf` to the repository and add `<a href="cv.pdf" download>Download CV ↓</a>` to the Contact section.

## Notes

- The page respects `prefers-reduced-motion`, so colonies appear fully grown and animations are off.
- Referee details from the CV are intentionally not published.
- Manuscripts marked "Under review" are not published papers.

## License

© Md. Arifur Rahman. All rights reserved. Please do not reuse the photo or text without permission.
