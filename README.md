# Coastal Flood Exposure

A workflow to assess coastal inundation exposure for a European
coastal city under IPCC AR6 sea-level rise scenarios up to 2100, with
Ostend (Belgium) as the case study.

## Files

- **coastal_flood_preproprecing_NJR_FINALVERSION.qmd** : data preparation
  pipeline. Downloads and assembles elevation, population, and SLR data,
  then saves all inputs needed.
- **coastal_flood_shiny_NJR_FINAL_VERSION.qmd** : interactive Shiny
  app that loads the preprocessed outputs and lets the user explore
  flood exposure.
- **coastal_flood_NJR_.html** : rendered HTML version of the preprocessing
  document.

## How to run

run all the chunk in the preprocessing qmd file.
