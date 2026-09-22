# RS Nexus — Global Trade CRM & Business Intelligence

Prototype for RS Holding Company. Single-file static app (`index.html`) — no build step, no backend required to run. All data shown is **DEMO / SAMPLE** data stored in the browser's `localStorage`.

## Run locally
Just open `index.html` in a browser, or serve it:
```bash
npx serve .
```

## Deploy — GitHub
```bash
cd rs-nexus
git init
git add .
git commit -m "Initial commit — RS Nexus prototype"
git branch -M main
git remote add origin https://github.com/<your-username>/rs-nexus.git
git push -u origin main
```

## Deploy — Vercel
**Option A — Vercel dashboard (recommended)**
1. Go to https://vercel.com/new
2. Import the GitHub repo you just pushed
3. Framework preset: **Other** (or "Static") — no build command, no output directory needed
4. Click **Deploy**

**Option B — Vercel CLI**
```bash
npm i -g vercel
cd rs-nexus
vercel
vercel --prod
```

`vercel.json` is already set up for a static site with security headers — no configuration needed on Vercel's side.

## Notes
- This is a working prototype (HTML/CSS/vanilla JS), not the final Next.js/Supabase build described in the original spec. The data layer (`Repo`, `Q` in the source) is written so it can be swapped for real Supabase calls later without touching the UI.
- `rs-nexus-schema.sql` (delivered separately) has the normalized PostgreSQL/Supabase schema this prototype's data model maps to.
- Data persists per-browser in `localStorage` — it is not shared between visitors and resets if the user clears site data. There's a "Reset demo data" / reseed path in `freshDB()` for a real backend migration.
- Demo login: pick any role on the sign-in screen. Role permissions and branch scoping are enforced client-side for the demo.
