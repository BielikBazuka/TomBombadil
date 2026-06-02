# Eindhoven After Dark — A Curated Catalogue

A single-page catalogue of curated **restaurants, activities and day trips** around
Eindhoven / Veldhoven — built for a fun night out, a team day, or a date.

- **25 restaurants** (all under €100 pp), **20 activities**, **10 day-trip experiences**
- Sort each category by **price** (low→high / high→low) or name
- **Save** any place to *My list* (♥) and **add notes/comments** under each place
- **Copy plan** exports your saved picks + notes as text to share
- Live photos + working **Google Maps** links for every place

Everything you save (and every note) is stored **locally in your browser**
(`localStorage`) — nothing is uploaded anywhere.

## Files
```
index.html   → the whole site (HTML + CSS + JS)
data.js      → all 55 places (edit here to add/remove/change anything)
```

## Run locally
Just open `index.html` in a browser. (No build step, no dependencies.)

## Publish free on GitHub Pages
1. Create a new repo on GitHub, e.g. `eindhoven-after-dark`.
2. Upload `index.html`, `data.js` and this `README.md` (drag-and-drop in the web UI,
   or `git add . && git commit -m "init" && git push`).
3. Repo → **Settings** → **Pages** → *Build and deployment* →
   **Source: Deploy from a branch** → Branch: **main** / **/ (root)** → **Save**.
4. Wait ~1 min. Your site is live at
   `https://<your-username>.github.io/eindhoven-after-dark/`.

## Editing places
Open `data.js`. Each place looks like this:
```js
{ name:"Takumi Ramen", area:"Nieuwstraat · Centrum", tier:1, cost:"€15–25 pp",
  vibe:"Ramen", desc:"…", placeId:"ChIJ…", q:"Takumi Ramen Eindhoven",
  web:"https://…", insta:null, img:"https://lh3.googleusercontent.com/…" }
```
- `tier` = price bucket used for sorting (1 = cheapest … 5).
- `cost` = the label shown on the card (free text).
- `q` + `placeId` build the Google Maps link.
- `img` = photo URL. If a photo ever fails to load, the card falls back to a
  styled placeholder with the place name, so it always looks intentional.

## Note on photos
Images come from Google Maps place photos. They load fine in normal browsers; if
Google ever rotates a URL, swap the `img` value in `data.js` for any image URL you
like (or leave it — the gradient fallback handles it).

---
*Prices and opening hours change — double-check before you go. Built with Claude.*
