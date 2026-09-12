# Flat Chores

A one-page chore rota for the flat. Each flatmate gets a box with their jobs for
the week, and the chores rotate by one person every Monday.

Everything lives in `index.html` — no build step, no dependencies.

## Changing the names or the chores

Open `index.html` and scroll to the block marked **EDIT THIS BIT** near the
bottom.

```js
const FLATMATES = [
  "Aran",
  "Ali"
];

const CHORES = [
  { emoji: "🚿", name: "Bagno 1", detail: "WC, doccia, lavandino, specchio" },
  { emoji: "🍳", name: "Cucina",  detail: "Piano cottura, lavello, superfici" }
];

const WEEK_OFF = { emoji: "😎", text: "Week off" };

const START_MONDAY = [2026, 1, 5];
```

- **FLATMATES** — one line per person, in rota order.
- **CHORES** — one line per chore. `emoji` and `detail` are both optional; use
  `""` to leave either out.
  - More chores than people? Some people get more than one that week.
  - Fewer chores than people? Some people get a week off. With 6 flatmates and
    5 chores that's one person per week, and it rotates too — over 6 weeks
    everyone does every chore once and gets one week off.
- **WEEK_OFF** — what the card shows for whoever has nothing that week.
- **START_MONDAY** — `[year, month, day]` of the Monday the rota counts from.
  Change it if you want to shift who starts on which chore.

Save, commit, push — GitHub Pages picks it up within a minute or so.

## Publishing on GitHub Pages

1. Create a new **public** repo on GitHub (no README, no .gitignore).
2. Push this folder to it:

   ```
   git remote add origin https://github.com/USERNAME/REPO.git
   git branch -M main
   git push -u origin main
   ```

3. In the repo: **Settings → Pages → Build and deployment**.
   Set *Source* to **Deploy from a branch**, branch **main**, folder **/ (root)**.
   Save.

The site appears at `https://USERNAME.github.io/REPO/` after a minute or two.
