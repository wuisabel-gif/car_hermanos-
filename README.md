# 🚗 Car Hermonos

*Like having a car-obsessed older brother — or dad — help you pick your first car. Honest, protective, and fluent in LA.*

An interactive, single-page tool that helps first-time buyers in **Los Angeles** choose a car. Set a budget, dial in what matters, filter by powertrain, and compare any two cars head-to-head — all scored for the realities of driving in LA: California fuel prices, smog rules, sky-high first-year registration, young-driver insurance, and whether you'll ever find parking for it.

Styled as a futuristic EV instrument cluster, with a glowing **LA Fit** gauge on every car.

---

## ✨ Features

- **Budget speedometer** — a digital readout + slider from $4K to $80K, spanning economy used cars to loaded luxury.
- **LA Fit score** — each car gets a 0–100 score shown on an animated tachometer-style gauge, weighted by your priorities.
- **Best-match spotlight** — the top result is promoted into its own detailed panel.
- **Powertrain filter** — All / EV / Hybrid / Gas.
- **AWD filter** — show only all-wheel-drive cars (handy for canyon, ski, and rain trips).
- **Priorities** — toggle what matters: cheap to run, reliable, top safety, easy parking, room/cargo, lowest price.
- **Compare mode** — pin any two cars for a side-by-side, metric-by-metric breakdown with a winner marked per row.
- **True cost telemetry** — expand any car for an estimated monthly cost: loan payment, fuel/charging at CA rates, young-driver insurance, California registration, smog, and upkeep.
- **Finance controls** — cash vs. finance, with down payment, APR, term, and driver age.
- **22 cars** from economy to luxury, including Volvo, Lexus, Tesla, Subaru, Toyota, Honda, and more.

## 🌴 What makes it LA-specific

- **Fuel costs** use an adjustable California gas price, so efficient cars and EVs pull ahead on long commutes.
- **Smog rules** flag whether a car is likely exempt (8 model years or newer, or any EV) vs. needing a check every 2 years.
- **Registration** approximates California's value-based Vehicle License Fee (~0.65% of value).
- **Insurance** gives a rough young-driver LA estimate that scales with car value, type, and age.
- **Parking footprint** and **safety** both factor into the score.
- **EV notes** reflect current reality — the federal EV tax credit ended in late 2025, and the solo-driver carpool decal depends on state reauthorization.

## 🛠️ Tech

- Plain **HTML + CSS + vanilla JavaScript** — no framework, no build step.
- **SVG** gauges drawn and animated in-browser.
- Fonts: **Chakra Petch** (display/data) + **Saira** (body), loaded from Google Fonts.
- Fully **responsive** and respects **`prefers-reduced-motion`**.

No dependencies to install. The only external request is the Google Fonts stylesheet.

## ▶️ Running it

It's a single file — just open it:

```bash
# clone, then open in any modern browser
open index.html      # macOS
# or double-click the file
```

Or host it for free on **GitHub Pages**: push the file to a repo, enable Pages, and point it at the branch. Since it's named `index.html`, it loads automatically as the site root.

## 📁 Files

| File | Purpose |
|------|---------|
| `index.html` | The entire app — markup, styles, and logic in one file. |
| `README.md` | This file. |
| `CONTRIBUTING.md` | How to contribute. |
| `LICENSE` | MIT license. |

## ⚠️ Disclaimer

Every dollar figure is an **illustrative estimate for comparison, not a quote.** Price bands reflect typical mid-2026 U.S. used-market asking ranges (drawn from Edmunds, CarGurus, Cox/Manheim, and KBB) and still vary with mileage, condition, trim, and the local LA market. Insurance for a young LA driver varies enormously by record and ZIP. Always verify current numbers with the **CA DMV** and a **licensed insurer** before making any decision.

## 📜 License

Released under the [MIT License](LICENSE) © 2026 **wuisabel-gif**. Free to use, modify, and distribute — just keep the copyright notice.

Made for first-time drivers navigating Los Angeles. 🌇
