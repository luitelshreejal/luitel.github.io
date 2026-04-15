# Shreejal Luitel — Portfolio

Personal portfolio site (regulatory science, AI, and drug development), built with React and Vite.

**Live site:** [https://luitelshreejal.github.io/](https://luitelshreejal.github.io/) (after you connect the repo below).

## GitHub Pages setup

1. Create a **public** repository named **`luitelshreejal.github.io`** under the account **luitelshreejal** (exact name required for the default `https://luitelshreejal.github.io/` URL).
2. Push this project’s `main` branch to that repository.
3. In the repo on GitHub: **Settings → Pages → Build and deployment → Source**, choose **GitHub Actions** (not “Deploy from a branch”).
4. The included workflow (`.github/workflows/deploy-pages.yml`) builds with Vite and publishes the `dist/` output on every push to `main`.

If your local folder is still named `luitel.github.io`, you can rename the remote only: `git remote set-url origin https://github.com/luitelshreejal/luitelshreejal.github.io.git`.

## Development

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

Output is written to `dist/`. The deploy workflow copies `index.html` to `404.html` so SPA-style routes keep working on refresh.

## Other scripts

- `npm run preview` — preview the production build locally
- `npm run lint` — ESLint
- `npm test` — Vitest
