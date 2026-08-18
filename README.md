# Daily Trade Coordination — Reusable Template

A single-file web app for running a daily trade coordination meeting, built to mirror the AEX meeting app. It's a **blank, reusable template** — set your project name, contractor, and buildings once in the **Setup** tab, and reuse the same app on every job.

Everything lives in one `index.html` — no build step, no server, no dependencies. It runs straight from GitHub Pages.

---

## First-time setup (per project)

On a fresh copy the app opens on the **⚙ Setup** tab. Enter:

1. **Project Info** — Project Name / abbreviation (e.g. `CCJC`) and CM / GC (e.g. `Yates–Metcon`). These fill the header automatically.
2. **Buildings / Areas** — add each building or area on the job (e.g. Courthouse, Detention Center, Sheriff's Office). **Sitewide** is always present and first, so site-wide coordination is built in. Buildings drive the Trade Coord sub-tabs and the Building dropdowns in Conflicts and Inspections.
3. **Trades** — add the trades/companies on site. They appear in every dropdown across the app.

That's it — the header now reads e.g. *"CCJC · Daily Trade Coordination"* with your buildings in the subtitle.

### Changing jobs

When you move to a new project, go to **Setup → New Project** and click **🧹 Start New Project**. It wipes all data and drops you back on a blank Setup so you can enter the next job. (Click **↧ Export** in the header first if you want to keep a record of the finished job.)

---

## Tabs

- **📋 Summary** — live overview (manpower, attendance, open tasks/conflicts/inspections), manpower-by-trade rollup, open conflicts, and **Export PDF Summary**.
- **🦺 Safety & 5S** — safety topic, Toolbox Talk / JHA sign-off per trade, 5S checklist, and observations / near-miss log.
- **👥 Attendance** — add people; click the status dot to cycle **Here → Remote/Teams → Absent**.
- **💪 Manpower** — head counts by trade (Supv / Journ / Labor / App / Safety) with live totals.
- **🏗 Trade Coord** — building sub-tabs (Sitewide first, then your buildings). Add tasks under any trade block with a status (Planned / Active / Blocked / Complete).
- **⚠️ Conflicts** — log conflicts/issues with Building, trade, type, blocking flag, and target resolution.
- **🔍 Inspections** — log inspections with Building, type, and status.
- **⚙ Setup** — project info, buildings, trades, and New Project (described above).
- **⏱ Man Hours** — set default hrs/worker/day, click **📌 Log Today** to snapshot the day's manpower as man hours, and **Export PDF**.

Header carries **Date / Facilitator / Safety Topic**, a meeting **elapsed timer**, a save indicator, and **New Day / Export / Import**.

---

## Daily workflow

1. Fill in **Date**, **Facilitator**, **Safety Topic**; hit **▶** on the timer.
2. Mark **Attendance**, set **Manpower**, run **Safety & 5S**.
3. Walk **Trade Coord** building by building; log **Conflicts** and **Inspections** as they come up.
4. Before closing, hit **📌 Log Today** on the Man Hours tab.
5. Next morning, click **🗓 New Day** and choose what to carry forward (open tasks, conflicts, inspections, roster, etc.). Your project name, buildings, trades, and the Man Hours log always persist.

Everything saves automatically to the browser's local storage on the device you're using.

### Keeping a record

Local storage is per-browser, per-device. Click **↧ Export** to download a dated JSON file (`ccjc-coordination-YYYY-MM-DD.json`); **↥ Import** loads one back. Commit exports into the repo (e.g. a `/records` folder) for a running history.

---

## Deploy to GitHub Pages

1. Create a repo (e.g. `trade-coordination` — reuse it for every job, or one repo per job).
2. Add this `index.html` at the repo root.
3. **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Live at `https://<your-username>.github.io/<repo>/`. Open it, fill in Setup, and go.

**Update later:** edit `index.html`, commit to `main`, Pages redeploys in about a minute.

---

## Notes

- This mirrors the AEX app's full feature set from its live page. The AEX repo's raw source isn't reachable from here, so the styling is a clean template (navy / steel / brass) rather than a pixel copy. Paste the AEX `index.html` source if you want the look matched exactly.
- Buildings and trades are fully editable in the Setup tab — nothing is hardcoded to any one project.
- Works fully offline once loaded. The only external request is Google Fonts; if blocked, it falls back to system fonts with no loss of function.
