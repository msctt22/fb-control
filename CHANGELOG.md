# Changelog

## 0.2.0 — redesign + cloud sync
- Visual overhaul: abstract gradient backdrop, frosted-glass panels and floating
  pill navigation, rounded corners throughout, gradient buttons, dark header
  with glow accents. Focus rings and reduced-motion support.
- Cloud persistence on Supabase (project `goshumgotgrholkacrpa`): every change
  saves to a shared team database; open windows sync live via realtime.
- Team sign-in with email + 6-digit code (no passwords). Only emails added in
  the Supabase dashboard (Authentication → Users) can sign in.
- JSON export/import backup retained as an offline escape hatch; if the cloud
  is unreachable the app keeps working in memory and warns that saves are off.

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
