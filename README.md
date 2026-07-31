# jmcburneylin.me — site source

A single-page site: `index.html` (all CSS/JS inline), plus `resume.pdf`.
No build step, no dependencies to install — just static files.

## Hosting it

Any static host works. Two easy free options:

**GitHub Pages**
1. Create a repo (e.g. `jmcburneylin.me`), add `index.html`, `resume.pdf`, and the `images/` folder.
2. Repo Settings → Pages → deploy from the `main` branch, root folder.
3. Point your domain's DNS at GitHub Pages (A records + CNAME file), or use the default `*.github.io` URL.

**Netlify**
1. Drag the `site` folder onto app.netlify.com/drop, or connect the GitHub repo.
2. Add your custom domain in Site settings → Domain management.

## Things to swap in

- **`resume.pdf`** — already your current resume, dated 1/13/25. Replace the file (keep the same filename) whenever you update it; the download buttons point at `resume.pdf` directly.
- **Hero photo** — currently pulling your headshot from Google's CDN (the same one your old Google Sites page used). Google's hosting is off-limits for the sandbox that built this preview, but it will load fine once live. For long-term reliability, download that image, save it as `images/hero.jpg`, and update the `<img src="...">` in the hero section to `images/hero.jpg`.
- **"Life outside the lab" photos** — currently four placeholder cards (trail running, Bear & Molly, woodshop, kitchen). Drop real photos into `images/` and swap each:
  ```html
  <div class="life-card placeholder"><div class="life-card-label">Trail running,<br>Santa Cruz Mtns</div></div>
  ```
  becomes:
  ```html
  <div class="life-card"><img src="images/trail.jpg" alt="Trail running in the Santa Cruz Mountains"><div class="life-card-label">Trail running, Santa Cruz Mtns</div></div>
  ```
- **ResearchGate link** — the Publications section links to your ResearchGate profile since that's the one verified index of your papers I could find. If you set up a Google Scholar profile, swap the `href` on the `#scholarBtn`... (search `researchgate.net/profile/Jim-Mcburney-Lin` in `index.html`).

## Design notes

- Palette and type are intentionally not the "generic AI portfolio" look — a warm sand/forest/clay palette (Santa Cruz coast + redwoods) instead of the usual cream-and-terracotta combo, paired with Fraunces (display serif) + Inter (body) + IBM Plex Mono (dates/labels/tags).
- The "Path" section timeline is a literal trail — dotted line, waypoint markers, "you are here" marker on your current role — a nod to both your neuroscience research (neural pathways) and your trail-running life.
- Respects `prefers-reduced-motion`, has visible keyboard focus states, and is responsive down to small phones.
