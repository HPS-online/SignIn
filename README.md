# Highbury Sign In / Out — Demo

A single-page, self-contained demo of a visitor & staff sign in/out kiosk, styled with Highbury's
navy (#242b63) / gold (#f5ac1c) / Montserrat branding — modelled on the current SignIt kiosk flow
(Home → Visitor/Staff/Admin → sign in/out).

**This is a demo only.** There's no backend — all data is stored in the browser's `localStorage`
on whatever device it's opened on, so it's perfect for showing staff the concept and flow, but it
won't sync between devices and will reset if someone clears their browser data or hits
"Clear demo data" in Admin.

## What's included

- **Home** — Visitor mode / Staff mode / Admin
- **Visitor mode** — Sign In (full form + Quick Sign In by mobile for returning visitors) and Sign Out (tap your name from the on-site list)
- **Staff mode** — Searchable staff dropdown (sample list included — swap in the real staff list any time) with Sign In / Sign Out
- **Admin** — Passcode-gated (demo passcode: `0000`) dashboard showing who's on site, full log, CSV export, and a "clear demo data" reset

## Deploy to GitHub Pages (5 minutes)

**Option A — new repo just for this demo**
1. Create a new repository on GitHub, e.g. `highbury-signin-demo`.
2. Upload `index.html` (and this README) to the root of the repo — either drag-and-drop via
   "Add file → Upload files" on github.com, or via git:
   ```
   git init
   git add index.html README.md
   git commit -m "Highbury sign in/out demo"
   git branch -M main
   git remote add origin https://github.com/<your-username>/highbury-signin-demo.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to "Deploy from a branch", branch `main`, folder `/ (root)`.
5. Save — GitHub will give you a URL like `https://<your-username>.github.io/highbury-signin-demo/`
   within a minute or two.

**Option B — add it into your existing `hps-online` GitHub Pages site**
1. In your `hps-online` repo, create a new folder, e.g. `/signin-demo/`.
2. Add `index.html` inside that folder.
3. Push — it'll be live at `https://hps-online.github.io/signin-demo/` alongside House Points and
   the Student Parliament site, with no extra Pages setup needed.

## Swapping in the real staff list

Open `index.html`, search for `SAMPLE_STAFF`, and replace the array with the full staff list in
`"Last, First"` format — the dropdown sorts/filters exactly as-is, no other changes needed.

## Turning this into the real thing later

When you're ready to move past the demo, the natural next step is wiring the same UI up to
Firebase (or another backend) so records sync across devices/kiosks in real time, persist
properly, and admin can see live site occupancy — happy to build that out once staff have seen
the flow and you're happy with it.
