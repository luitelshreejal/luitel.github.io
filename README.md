# Shreejal Luitel — Portfolio

Personal portfolio site (regulatory science, AI, and drug development), built with React and Vite.

**Live site:** [https://luitelshreejal.github.io/luitelshreejal/](https://luitelshreejal.github.io/luitelshreejal/)

## GitHub Pages (required setup)

This app must be **built** (Vite → `dist/`). Serving the raw repo from **“Deploy from a branch”** + **`/(root)`** only publishes unbundled source, so the site looks **blank**.

1. In the repo: **Settings → Pages → Build and deployment**.
2. Set **Source** to **GitHub Actions** (not “Deploy from a branch”).
3. Push to **`main`**. The workflow `.github/workflows/deploy-pages.yml` runs `npm run build` and publishes **`dist/`**.

First time: open the **Actions** tab and approve the workflow if GitHub asks.

### Repo name and `base` URL

This project is configured for a **project** site: repo name **`luitelshreejal`** → site at `/luitelshreejal/`.  
`vite.config.ts` uses `base: "/luitelshreejal/"`. If you **rename** the repo, update `base` to `"/NEW-REPO-NAME/"`.

To use the **root** URL `https://luitelshreejal.github.io/` instead, rename the repository to **`luitelshreejal.github.io`** and change `base` to `"/"` in `vite.config.ts`.

## Development

Open **`http://localhost:8080/luitelshreejal/`** (Vite uses the same `base` as production).

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

Output is written to `dist/`. The deploy workflow copies `index.html` to `404.html` so client-side routes work on refresh.

## Other scripts

- `npm run preview` — preview the production build locally
- `npm run lint` — ESLint
- `npm test` — Vitest
