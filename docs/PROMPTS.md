# Lookbook page prompts

Two reusable prompts for generating an individual A4 lookbook page for a menu item.

---

## 1. A4 page content & layout brief

Hand this to a designer or design tool. `{{…}}` are the per-item data fields.

```
Design a single-item menu page for a hospitality lookbook. Format: A4 portrait,
210 × 297 mm, print-ready, ~15 mm safe margins, white background.

The page presents ONE dish or drink. Content, in priority order:
1. Top bar — venue name "Hyde & Seek" (left); small badge (right) reading either
   "Food" or the beverage category: Cocktail / Spirit / Beer / Wine.
2. Hero image — {{photo}} full-bleed across the top third. If no photo, a deep navy
   panel showing the item's two-letter monogram.
3. Item name — large display heading: {{name}}.
4. Sub-line — {{outlet}} · {{category}}.
5. Description / tasting note — 1–3 sentences: {{description}}.
6. Stat strip (equal tiles, monospaced figures): Calories {{kcal}} kcal · Cost {{cost}}
   · Price {{price}} · GP {{gp}}% · (drinks only) Alcohol units {{units}}.
7. Two columns — left: Ingredients, each line "{{name}} … {{qty}} {{unit}}";
   right: Allergens as highlighted chips, or "No listed allergens".
8. Footer — "Adults need around 2000 kcal a day." (left); "Hyde & Seek · {{date}}" (right).

Every field is optional/toggleable so the same template works for a guest-facing
version (no cost or GP) and an internal version (all figures shown).

Aesthetic: refined modern-British, editorial, premium and calm — not busy. Generous
white space; one accent colour (a muted park green); a characterful display typeface
for the name paired with a clean sans for body; tabular monospaced numerals for all
figures. Clear hierarchy: photo → name → note → numbers → ingredients/allergens.
```

---

## 2. GPT visual-design prompt (outputs print-ready HTML/CSS)

Paste into ChatGPT/GPT.

```
You are a senior print and editorial designer. Produce a print-ready, self-contained
HTML file (inline CSS, no external dependencies except Google Fonts) for a SINGLE A4
portrait page (210 × 297 mm) that is one page of a restaurant/hotel "menu lookbook".
Use @page { size: A4; margin: 0 } and a fixed 210 × 297 mm page box so it prints and
"Save as PDF"s exactly to A4 with no overflow.

Brand: "Hyde & Seek", a modern-British London hotel with multiple F&B outlets. Tone:
premium, editorial, warm, uncluttered.

The page must lay out, top to bottom: a slim top bar (venue name left, a small Food /
Cocktail / Spirit / Beer / Wine badge right); a hero photo across the top third (use a
placeholder block with a monogram if no image); the item name as a large display
heading; an outlet · category sub-line; a 1–3 sentence description; a horizontal strip
of stat tiles (Calories kcal, Cost, Price, GP %, and Alcohol units for drinks) with
monospaced numerals; then two columns — Ingredients (name + quantity/unit per row) and
Allergens (highlighted chips, or "No listed allergens"); and a footer reading
"Adults need around 2000 kcal a day." on the left and "Hyde & Seek · [date]" on the right.

Design direction: choose a distinctive display/body type pairing (not generic), a single
restrained accent colour drawn from a leafy park green, deep navy for headings, generous
margins, and tabular figures for all numbers. Make every content block easy to remove so
the template supports a guest-facing variant (no Cost/GP) and an internal variant.

Fill it with this example item, then tell me which lines to edit to swap in another:
Name: Cod cheek nuggets | Outlet: FYND | Type: Food
Description: Crisp panko cod cheeks with lemon and tartare — a playful nod to fish & chips.
Calories: 612 kcal | Food cost: £2.74 | Price: £9.50 | GP: 65.4%
Ingredients: Cod fillet 140 g; Plain flour 30 g; Egg 0.5 ea; Panko breadcrumb 50 g;
Rapeseed oil 25 ml | Allergens: Fish, Cereals w/ gluten, Eggs

Output only the complete HTML file. Keep it under one page — nothing should overflow A4.
```
