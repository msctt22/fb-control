# Changelog

## 0.2.0 — redesign + cloud sync
- Visual overhaul: liquid-glass interface — high-transparency panels with
  specular edges, heavy blur/saturation, animated organic blobs behind the UI,
  floating pill navigation, rounded corners throughout. Focus rings and
  reduced-motion support.
- Typography: Aqua Grotesque for headlines, Roboto Slab (thin weights) for
  body text; JetBrains Mono retained for figures.
- Cloud persistence on Supabase (project `goshumgotgrholkacrpa`): every change
  saves to a shared team database; open windows sync live via realtime.
- Team sign-in with emailed magic links (no passwords). Only emails added in
  the Supabase dashboard (Authentication → Users) can sign in.
- Hosted on GitHub Pages so the team opens a URL instead of passing a file
  around; the local file remains usable for development.
- JSON export/import backup retained as an offline escape hatch; if the cloud
  is unreachable the app keeps working in memory and warns that saves are off.
- Lookbook PDF pages redesigned to an editorial template: Playfair Display
  serif titles on cream, large photo left, right-hand rail of rounded cards
  (ingredients, allergens, price, cost, GP, calories, units) with navy SVG
  icon medallions, outlet tagline and ruled footer.

## 0.1.0 — initial
- Single-file app: dashboard, ingredients, menu items, waste log, sales & COGS,
  calorie menu, settings.
- Cost of sales (GP% on net of VAT), calorie/nutrition and allergen calculation,
  all derived from costed recipes.
- Food / Beverage top-level classification; beverage sub-categories
  (Cocktail / Spirit / Beer / Wine) with ABV and alcohol-units-per-serve.
- Photos on menu items (auto-resized) and a description / tasting-note field.
- Lookbook gallery + "Generate Lookbook (PDF)" with an include-options pop-up,
  producing a multi-page A4 PDF (one page per item).
- Local persistence with JSON export/import backup.
