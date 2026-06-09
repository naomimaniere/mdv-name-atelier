# MDV — Name Atelier

A self-contained product-name generator for the Manière de Voir range. Anyone in the
business can open it, pick a category (WMN / MAN / UNX / ACC), ask for a quantity
(e.g. 100), and get names that are unique, easy to spell and French-leaning — checked
so none is 70%+ similar to a name already in the range.

It's **one file** (`index.html`) with all the data baked in. No build step, no server,
no API key, nothing to install.

## How the names are chosen
1. **Curated first** — real, easy-to-spell French names are used until they run out for the batch.
2. **Invented backup** — once curated names are exhausted, the tool builds new French-style names.
3. **Filter** — any name 70%+ similar to an existing range name (or to another name in the same batch) is rejected. Accents are ignored when comparing, so *Léa* and *Lea* count as the same.

Each result is tagged **curated** or **invented** so you can see at a glance which is which.
Click the names you're taking to tick them, then **Copy for CP** to put your selection on the
clipboard one per line — paste straight down a name column in the Critical Path. Tick nothing
and it copies the whole batch. **CSV** downloads the same selection as `Name, Category, Source`.

## Categories
| Button | SKU | Name style |
|---|---|---|
| Womens | WMN | female |
| Mens | MAN | male |
| Unisex | UNX | gender-neutral |
| Accessories | ACC | gender-neutral |

## Deploy it (drag-and-drop)
1. Create a new GitHub repo (e.g. `mdv-name-atelier`).
2. Click **Add file → Upload files**, drag in `index.html`, commit.
3. Either:
   - **GitHub Pages**: Settings → Pages → deploy from `main` / root. Done.
   - **Vercel**: New Project → import the repo → Deploy. No settings needed.
4. Share the URL with the team.

## Updating the existing-names list later
The list the tool avoids is the `EXISTING` array near the top of the `<script>` in
`index.html` (lowercased, accent-free). To refresh it from a new Shopify export, send the
export to Claude and ask for a regenerated `index.html` — the cleaning + folding is done
automatically.
