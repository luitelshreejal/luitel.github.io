# Shreejal Luitel — Portfolio

Personal portfolio site (regulatory science, AI, and drug development), built with React and Vite.

**Live site:** [https://luitelshreejal.github.io/luitelshreejal/](https://luitelshreejal.github.io/luitelshreejal/)

## GitHub Pages — fix a blank site

The live site must be the **Vite build** (`dist/`), not the repo root. A dev `index.html` that loads `/src/main.tsx` will always look **blank** on Pages.

### Settings (do this once)

1. **Settings → Pages → Build and deployment**
2. Set **Source** to **GitHub Actions** (not “Deploy from a branch”).
3. Push **`main`**. The workflow **Deploy to GitHub Pages** runs `npm run build` and publishes only **`dist/`**.

The old **`static.yml`** workflow uploaded the **whole repository** (including dev `index.html`). That file is removed so the correct workflow can deploy the build.

### Repo name and `base` URL

Repo **`luitelshreejal`** → URL path **`/luitelshreejal/`**. `vite.config.ts` uses `base: "/luitelshreejal/"`. If you rename the repo, update `base` to `"/NEW-NAME/"`.

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
