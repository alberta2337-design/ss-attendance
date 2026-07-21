# Sunday School Roll Book

A Sunday school attendance app: take the roll for classes and volunteers, track
history and stats by date, and print reports.

> **Note on data storage:** this standalone version saves data in your
> browser's `localStorage`. That means attendance data lives on *that one
> browser/device only* — it is **not** synced across devices. If you need
> real multi-device sync, you'll need to connect it to a backend (Firebase,
> Supabase, a small API of your own, etc.) — see the comment above
> `useStorage()` in `src/App.jsx` for where to plug that in.

## Run it locally

```bash
npm install
npm run dev
```

Then open the URL Vite prints (usually http://localhost:5173).

## Build for production

```bash
npm run build
```

This outputs a static site to `dist/`.

## Host it on GitHub

### Option A: GitHub Pages via GitHub Actions (recommended, automatic)

1. Create a new GitHub repository and push this project to it:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
2. In your GitHub repo, go to **Settings → Pages**, and under "Build and
   deployment" set **Source** to **GitHub Actions**.
3. The included workflow at `.github/workflows/deploy.yml` will automatically
   build and deploy the site every time you push to `main`.
4. Your site will be live at `https://<your-username>.github.io/<your-repo>/`.

### Option B: GitHub Pages via the `gh-pages` package (manual)

```bash
npm install
npm run build
npm run deploy
```

This pushes the contents of `dist/` to a `gh-pages` branch. Then in
**Settings → Pages**, set the source branch to `gh-pages`.

## Project structure

```
├── index.html            Vite entry HTML
├── src/
│   ├── main.jsx           React entry point
│   ├── App.jsx             The entire app (all components)
│   └── index.css          Tailwind CSS entry
├── vite.config.js         Vite config (relative base path for GH Pages)
├── tailwind.config.js
├── postcss.config.js
└── .github/workflows/deploy.yml   Auto-deploy to GitHub Pages
```
