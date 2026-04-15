# Shreejal Luitel — Portfolio

Personal portfolio site (regulatory science, AI, and drug development), built with React and Vite.

**Live site:** [https://luitelshreejal.github.io/luitelshreejal/](https://luitelshreejal.github.io/luitelshreejal/)

## GitHub Pages — fix a blank site

GitHub must serve the **built** site (`dist/`), not the repo root. Your live page was still the dev `index.html` (`<script src="/src/main.tsx">`), which browsers cannot run on Pages — that shows up as a **blank white screen**.

### One-time settings

1. Push **`main`** so the **Build and deploy site** workflow runs (see **Actions** tab; approve it if asked).
2. **Settings → Pages → Build and deployment**
3. Under **Source**, choose **Deploy from a branch**.
4. Set **Branch** to **`gh-pages`** and folder **`/(root)`** — not `main`.  
   The workflow creates/updates **`gh-pages`** with only the production files from **`dist/`**.

If **Source** is set to **GitHub Actions** instead, switch it to **Deploy from a branch** and use **`gh-pages`** as above (this repo deploys by pushing that branch).

### Repo name and `base` URL

Repo **`luitelshreejal`** → site path **`/luitelshreejal/`**. `vite.config.ts` uses `base: "/luitelshreejal/"`. If you rename the repo, update `base` to `"/NEW-NAME/"`.

For **`https://luitelshreejal.github.io/`** (no subpath), use a repo named **`luitelshreejal.github.io`** and set `base: "/"`.

## Development

Use **`http://localhost:8080/luitelshreejal/`** (same `base` as production).

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

The workflow copies `index.html` to `404.html` in `dist/` for SPA refreshes. `public/.nojekyll` is copied into `dist/` so GitHub Pages does not run Jekyll on the build output.

## Other scripts

- `npm run preview` — preview the production build locally
- `npm run lint` — ESLint
- `npm test` — Vitest
