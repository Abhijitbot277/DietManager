# DietManager

A responsive, browser-based nutrition tracker built with plain HTML, CSS and JavaScript. No build step or external database is required.

## Features

- Body profile with age, height, weight, activity level, goal and optional body measurements.
- Estimated BMI, BMR, daily energy target and macro targets.
- Indian-food-focused starter database with common household serving estimates.
- Daily food log with calories, protein, carbohydrates, fat and fibre.
- Mixed-dish calculator that totals recipe ingredients and divides nutrition by servings.
- Water log, daily history and JSON export.
- Local browser storage and responsive mobile layout.

## Run locally

Open `index.html` in a modern browser. For deployment, enable GitHub Pages for the `main` branch and root (`/(root)`) in the repository's **Settings → Pages**.

## Important notes

- This is an initial working version, not a clinical nutrition product.
- Food values and portion sizes are approximations. Recipe, brand, cooking method and actual serving weight can materially change nutrition.
- Calorie and macro targets are estimates based on standard equations and assumptions, not a diagnosis or a medical plan.
- Profile and log data stay in the current browser's local storage. There is no login, server-side database or cloud sync in this version. Use **Export JSON** to keep a backup.
- Do not rely on this app as a substitute for qualified medical or dietetic advice.

## Next development steps

1. Expand and validate the food database against a reliable nutrition reference.
2. Add portion presets per food and editable recipe ingredient units.
3. Add optional authentication and secure cloud sync if a backend is introduced.
4. Add tests for nutrient calculations and profile edge cases.
