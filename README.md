# F&B Control

A single-file web app for hotel food & beverage operations that brings three jobs into
one tool: **cost of sales**, **calorie/nutrition**, and **food & beverage waste** — built
around a single source of truth (costed, structured recipes).

Built for the Hyde & Seek pre-opening, but generic enough for any multi-outlet operation.

## What it does

- **Food & Beverage split** — everything is classified as Food or Beverage. Beverages carry
  a sub-category (Cocktail / Spirit / Beer / Wine / Soft) and an optional ABV.
- **Ingredients** — define cost, calories and allergens once. Pack size in kg/L/each is
  normalised to a cost-per-gram/ml/each basis.
- **Menu items** — build from ingredients; food cost, GP% (on net of VAT), calories,
  allergens and (for drinks) alcohol units per serve calculate live. Each item supports a
  photo and a description / tasting note.
- **Waste log** — record spoilage, trim, overproduction etc.; value auto-fills from the
  linked ingredient's cost. Dashboard rolls it up by reason.
- **Sales & theoretical COGS** — paste sold quantities (or a CSV: `item, quantity`) and the
  tool matches them to recipes to give revenue, theoretical cost and cost-of-sales %.
  Works fully standalone; a POS/till is an optional CSV feed, not a dependency.
- **Calorie menu** — kcal per item for point-of-choice display, with food and beverage
  shown separately (drinks above 1.2% ABV are exempt from mandatory UK display).
- **Lookbook** — a visual gallery of dishes/drinks, plus a **Generate Lookbook (PDF)**
  flow: a pop-up lets you tick which fields to include, then produces a multi-page A4 PDF
  (one page per item) for sharing.

## Running it

No build step, no install. Open `index.html` in any modern browser
(Chrome/Edge recommended for the PDF export).

- Data is saved locally in the browser when supported; otherwise it persists for the
  session only. Use **Export backup** / **Import backup** (top right) to save or move data
  as a JSON file — photos are included in the backup.
- The PDF export uses jsPDF + html2canvas loaded from a CDN, so it needs an internet
  connection. If the libraries can't load it falls back to the browser's print dialog.

## Structure

```
.
├── index.html        # the entire application (HTML + CSS + vanilla JS)
├── docs/
│   └── PROMPTS.md     # A4 lookbook-page brief + GPT visual-design prompt
├── CHANGELOG.md
├── LICENSE
└── README.md
```

## Notes & limitations

- GP% is calculated on the **net** (ex-VAT) selling price — the standard UK hospitality
  method. VAT rate and target GP are set in Settings.
- Calorie and cost figures are only as accurate as your per-ingredient inputs and portioning.
  Verify before publishing a menu.
- This is a single-user planning tool, not a live multi-site inventory/depletion system.
  For real depletion-based COGS across outlets, pair it with a back-of-house platform
  (e.g. Apicbase, Fourth).
- Lookbook PDF pages are rasterised, so their text isn't selectable; for selectable text,
  use the GPT-generated HTML route in `docs/PROMPTS.md` and "Save as PDF" from the browser.

## Roadmap ideas

- Bottle/keg yield helpers (measures per bottle, pints per keg)
- Wine-by-the-glass margin view and batch-cocktail scaling
- POS export adapters (Oracle Simphony/Micros, Lightspeed, Square)
- Stock-count / depletion module for actual vs theoretical COGS
