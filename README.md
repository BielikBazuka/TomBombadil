# Let's Go Out — Eindhoven

A single-page catalogue of things to do around Eindhoven / Veldhoven — for a night
out, a team day, or a date — plus a simple group **availability planner**.

**Sections**
- **Eat** — 25 restaurants in Eindhoven, all under €100 pp
- **Do** — 20 activities for groups, teams & dates (no bowling, no escape rooms)
- **Day Trips** — 12 full-day escapes; the **Biesbosch Boat Day** leads with a full
  hour-by-hour plan
- **Worth the Drive** — 12 atmospheric spots within ~30 km (castles, forests, a
  church, waterside fine dining)
- **This Summer** — once-a-year festivals & flower parades

**Features**
- Sort each section by **price** or **name**
- **Save** places to *My list* (♥), **add notes**, and **Copy plan** to share
- Every card links to **Google Maps** and the **website** (and **Instagram** where it exists)
- **Plan a night** — a shared calendar: add your name, tap the dates you're free,
  and the day **everyone** can make turns green

Saved picks, notes and your own availability are stored **locally in your browser**.

## Files
```
index.html          → the whole site (HTML + CSS + JS)
data.js             → all places & events (edit here to change anything)
availability.json   → shared group availability for the planner
README.md
```

## Run locally
Open `index.html` in a browser. No build step, no dependencies.
(The planner reads `availability.json` from the same folder.)

## Publish free on GitHub Pages
1. Create a repo, e.g. `lets-go-out-eindhoven`.
2. Upload `index.html`, `data.js`, `availability.json`, `README.md`.
3. Repo → **Settings** → **Pages** → Source: **Deploy from a branch** →
   Branch **main** / **/(root)** → **Save**.
4. Live after ~1 min at `https://<your-username>.github.io/lets-go-out-eindhoven/`.

## How the shared planner works
GitHub Pages is a static site, so there's no live shared database. Availability is
kept in **`availability.json`** in the repo, and everyone updates it via GitHub:

1. On the site, type your name and tap the dates you're free.
2. Click **Download availability.json** (it already merges in everyone currently
   listed) — or **Copy my line** to grab just your own entry.
3. Commit the updated `availability.json` to the repo (upload the file, or edit it
   on GitHub and paste your copied line into the `people` array), e.g.:
   ```json
   {
     "updated": "2026-06-02",
     "people": [
       { "name": "Rafał", "dates": ["2026-06-13", "2026-06-20"] },
       { "name": "Anna",  "dates": ["2026-06-20"] }
     ]
   }
   ```
4. Once committed, the site shows everyone's availability, and days where **all**
   listed people are free are highlighted green.

Tip: easiest flow is for one person to collect everyone's **Copy my line** entries
and commit them together, or let each person edit the file via a quick GitHub PR.

## Editing places
Open `data.js`. Each entry:
```js
{ name:"Takumi Ramen", area:"Nieuwstraat · Centrum", tier:1, cost:"€15–25 pp",
  vibe:"Ramen", desc:"…", placeId:"ChIJ…", q:"Takumi Ramen Eindhoven",
  web:"https://…", insta:"https://instagram.com/…" }   // insta optional
```
- `tier` = price bucket for sorting (1 cheapest … 5).
- `feat:true` pins a Day Trip to the top; a trip can carry a `plan:[{t,h,d}]` timeline.
- In *This Summer*, `vibe` doubles as the date badge.

---
*Hours, prices and festival dates change — check before you go.*
