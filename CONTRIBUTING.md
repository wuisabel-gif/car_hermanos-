# Contributing to Car Hermonos

Thanks for wanting to help out. The whole point of this project is to be the honest older-brother for someone buying their first car in LA, so contributions that make the advice more accurate, the prices more current, or the experience clearer are all welcome.

> **Note:** Car Hermonos is released under the [MIT License](LICENSE). By submitting a contribution you agree to license it under the same terms. If you're planning something big, open an issue first so we can talk it through before you spend real time on it.

---

## Project setup

There's no build step, no package manager, no dependencies. The entire app lives in one file: **`index.html`** (markup, styles, and logic together).

To work on it:

```bash
git clone https://github.com/wuisabel-gif/<repo-name>.git
cd <repo-name>
# open the file in any modern browser
open index.html        # macOS
xdg-open index.html    # Linux
# or just double-click it
```

Edit, save, refresh the browser. That's the whole loop.

## How the code is organized

Inside the `<script>` tag, top to bottom:

- **`CARS`** — the array of car objects (the data you'll most likely touch).
- **`SAFE`** — a name → safety-rating map merged into cars that don't set `safe` directly.
- **`BRO`** — a name → "tu hermano's take" map; these one-liners override each car's `blurb`.
- **`state`** — all current UI selections (budget, filters, priorities, compare list, etc.).
- **Scoring + cost** — `fitScore()`, `buildCost()`, `insMonthly()`, `regYearly()`, `fuelMonthly()`.
- **Rendering** — `gaugeSVG()`, `cardHTML()`, `featuredHTML()`, `compareHTML()`, `render()`.
- **Events** — one delegated listener on `#results`, plus the console controls.

## Adding or editing a car

Most contributions are here. Each entry in `CARS` looks like this:

```js
{
  name:"Honda Civic",     // unique; used as the key for SAFE/BRO maps
  type:"Sedan",           // Sedan | Hatchback | Wagon | SUV | EV
  lo:9000, hi:22000,      // typical used price band (USD)
  mpg:33, miPerKwh:null,  // gas/hybrid use mpg; EVs use miPerKwh + range
  rel:5,                  // reliability 1–5
  space:3,                // interior/cargo room 1–5
  park:4,                 // how easy to park 1–5 (higher = easier)
  fuel:"gas",             // "gas" | "hybrid" | "ev"
  awd:false,              // true if AWD is standard or commonly available
  yrsOld:9,               // typical age of an example in this band (drives smog note)
  // range:240,           // EVs only: EPA-ish range in miles
  // safe:5,              // optional; otherwise pulled from the SAFE map
  blurb:"...",            // overridden by the BRO map if present
  notes:[["ok","..."],["warn","..."]]  // 1–3 LA-relevant bullet points
}
```

Guidelines:

- **Prices are estimates, not quotes.** Use current mid-market used ranges from a reputable source (Edmunds, CarGurus, KBB, Cox/Manheim). Cite your source in the PR.
- **Keep the LA lens.** Notes should be things an LA buyer actually cares about — gas, smog, parking, insurance, AWD for trips.
- **Add a hermano line.** Give the car an entry in the `BRO` map: one short, honest, protective sentence in the older-brother voice (~6–12 words). That's the personality of the project.
- **Set `safe`** directly for new luxury/AWD cars, or add the model to the `SAFE` map.

## Style & design conventions

The UI deliberately avoids generic "AI default" patterns. Please keep to these:

- **No glassmorphism** — surfaces are solid with a subtle top highlight, not `backdrop-filter` blur.
- **No left-border accent stripes** on cards or callouts.
- **Don't pair a 1px border with a big soft drop-shadow** on the same element; let borders carry structure.
- **Mind contrast** — body text and small labels must stay legible on the dark background.
- **Use the CSS variables** already defined (`--ice`, `--amber`, `--mint`, etc.) instead of hardcoding colors.
- **Respect `prefers-reduced-motion`** — any new animation must be covered by the existing reduced-motion block, and must never hide content if it doesn't run.
- Fonts stay **Chakra Petch** (display/data) and **Saira** (body).

Code style: vanilla JS, no frameworks, no new dependencies. Match the existing concise formatting.

## Before you open a PR

Please confirm:

- [ ] The page opens and works with no console errors.
- [ ] Filters (powertrain, AWD), priorities, budget, compare, and the cost panel all still work.
- [ ] It looks right at mobile width (~380px) and on desktop.
- [ ] Reduced-motion mode still shows everything.
- [ ] Any new price/spec data has a cited source in the PR description.

Then open a pull request describing **what** you changed and **why**, with a screenshot if it's visual.

## Reporting bugs or ideas

Open an issue with what you expected, what happened, your browser, and a screenshot if you can. Suggestions for new cars, better LA cost logic, or features (dad-mode vs. brother-mode, live pricing, more filters) are all fair game.

Gracias for helping someone find their first ride. 🚗
