# The night's tab

**Live: https://valiice.github.io/night-tab/**

Same buzz, different bill — an interactive comparison of what a night of drinking costs in calories, drink by drink. Pick any two drinks, set the pace and the hours, and watch the receipt, the BAC curve, and the calorie gap update live.

## Features

- **Any two drinks side by side** — spirits (vodka / white or brown rum, spiced rum) with a mixer (zero soda, coke, orange juice), wines (sweet pink, brut, dry white/red, moscato) with an adjustable residual-sugar slider, or beers (1664 Blanc, 1664 Fruits Rouges).
- **Two comparison modes** — "same buzz" (10 g ethanol per drink for both) or "same servings" (a 4 cl shot vs a 150 ml pour vs a 25 cl bottle).
- **Receipt summary, estimated BAC curve** (simple Widmark model) with the French 0.05% / 0.02% driving limits, cumulative calorie chart, and a "what that looks like at home" bottle-equivalence table.
- **Settings persist** in localStorage; the ↺ reset button restores defaults.

## The model

- Calories: ethanol grams × 7 + sugar/carbs grams × 4. Runs somewhat under printed labels because glycerol and organic acids aren't modeled — a few percent for sweet or sparkling wines, up to ~15% for dry wines. Beer numbers land close to the official per-100 ml labels (1664 Blanc: 40 kcal exactly, Fruits Rouges: ~41 vs 43 printed).
- BAC: Widmark estimate — each drink lands instantly, the liver clears ~0.015%/hour (≈8 g of ethanol per hour for an 80 kg man). Real absorption is slower on a full stomach and faster on an empty one or with diet mixers.

This is a rough educational toy, not medical advice. Don't use it to decide whether you can drive.

## Development

A single `index.html`, no build step. Chart.js comes from the cdnjs CDN. Open the file locally or serve the folder with any static server.
