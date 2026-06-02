# Let's Go Out — Eindhoven

A single-page catalogue of curated things to do around Eindhoven / Veldhoven,
built for a night out, a team day, or a date.

**Four sections:**
- **Eat** — 25 restaurants, all under €100 pp
- **Do** — 20 activities for groups, teams & dates (no bowling, no escape rooms)
- **Day Trips** — 12 full-day escapes; the **Biesbosch Boat Day** leads with a full
  hour-by-hour plan (pickup → boat → BBQ lunch → dinner → drop-off)
- **This Summer** — once-a-year festivals & flower parades (Corso Zundert, WiSH
  Outdoor, Down the Rabbit Hole, Awakenings, Bloemencorso Bollenstreek, Carnival)

**Features**
- Sort each section by **price** (low→high / high→low) or **name**
- **Save** any place to *My list* (♥) — grouped by section in a side drawer
- **Add notes/comments** under every place
- **Copy plan** exports your saved picks + notes as text to share
- Every card links to **Google Maps**, the **website**, and **Instagram**
  (or a **Photos** link to Google Maps when there's no Instagram)
- No external images — fast, never-broken, fully self-contained

Saved picks and notes are stored **locally in your browser** (`localStorage`);
nothing is uploaded anywhere.

## Files
```
index.html   → the whole site (HTML + CSS + JS)
data.js      → all the places & events (edit here to change anything)
```

## Run locally
Open `index.html` in any browser. No build step, no dependencies.

## Publish free on GitHub Pages
1. Create a new repo, e.g. `lets-go-out-eindhoven`.
2. Upload `index.html`, `data.js`, `README.md` (drag-and-drop or `git push`).
3. Repo → **Settings** → **Pages** → Source: **Deploy from a branch** →
   Branch: **main** / **/ (root)** → **Save**.
4. After ~1 min it's live at `https://<your-username>.github.io/lets-go-out-eindhoven/`.

## Editing
Open `data.js`. Each place:
```js
{ name:"Takumi Ramen", area:"Nieuwstraat · Centrum", tier:1, cost:"€15–25 pp",
  vibe:"Ramen", desc:"…", placeId:"ChIJ…", q:"Takumi Ramen Eindhoven",
  web:"https://…", insta:"https://instagram.com/…" }   // insta optional
```
- `tier` = price bucket for sorting (1 = cheapest … 5).
- `cost` = label shown on the card (free text).
- `q` + `placeId` build the Google Maps link.
- Add `feat:true` to pin a Day Trip to the top.
- A Day Trip can include a `plan:[{t,h,d}, …]` timeline + `planmeta:"…"`.
- `vibe` doubles as the date badge in *This Summer* (e.g. `"Sep 6–7, 2026"`).

---
*Hours, prices and festival dates change — check before you go. Built with Claude.*
