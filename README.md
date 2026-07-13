# EMSO Console

An interactive **Electromagnetic Spectrum Operations** training sandbox — a dark, tactical
visualization of how radar, electronic warfare, datalinks, and SATCOM interact in a
Pacific-theater scenario. Everything runs client-side in a single HTML file (Canvas + vanilla
JS, no build step, no dependencies).

## What's in it

- **Blue radar sim** — AWACS, fighter, and Aegis destroyer sensors; selectable bands (L–Ku),
  waveforms (pulsed / CW / pulse-Doppler), PRF, and scan modes (search / track-while-scan /
  single-target-track).
- **Zoom & inspect** — scroll to zoom, drag to pan, double-click any blue unit for an
  over-the-shoulder schematic with its emitters working (nose gimbal, rotodome, SPY faces,
  IFF interrogation, EA pods). Toggle a heading-up view.
- **ELINT threat ID** — passive ESM intercepts red emitters and fuses them into a platform
  classification with a live confidence score (a unique fire-control radar confirms a type;
  a shared search radar stays ambiguous until corroborated).
- **Red IADS kill chain** — a red AEW aircraft passes tracks over a tactical datalink to an
  HQ-9 SAM battery. Break the chain by jamming the datalink (Growler) and the red SATCOM
  uplink (ground jammer) to get a strike package through.
- **SATCOM** — blue/red geostationary links with selectable bands, jammable footprints, and
  a Ka spot beam that defeats an in-footprint uplink jammer by geometry.
- **Scenario presets** — ISR / ELINT collect, Blue ingress, Red anti-access — plus a full
  matrix of individual toggles.

> Educational simulation only. All platforms, ranges, and behaviors are illustrative
> approximations, not real system parameters. Marked `UNCLASS // SIM`.

## Run it locally

It's a static file — just open `index.html` in a browser. Or serve it:

```bash
# Python 3
python -m http.server 8000
# or Node
npx serve .
```

Then visit <http://localhost:8000>.

## Deploy on Render (free static site)

**Option A — Blueprint (uses `render.yaml`):**
1. Push this repo to GitHub (see below).
2. In Render: **New +** → **Blueprint** → select this repo → **Apply**.

**Option B — Manual:**
1. In Render: **New +** → **Static Site** → connect this repo.
2. **Build Command:** leave blank. **Publish Directory:** `.`
3. **Create Static Site.**

Render gives you a public `https://emso-console.onrender.com`-style URL you can open from any device.

## Deploy anywhere else

Any static host works with zero config: GitHub Pages, Netlify, Cloudflare Pages, Vercel —
just point them at this folder with `index.html` as the entry.

## Push to GitHub

This folder is already a git repo with a first commit. Create an empty repo on GitHub
(no README/license), then:

```bash
git remote add origin https://github.com/VaughanMills/emso-console.git
git branch -M main
git push -u origin main
```
