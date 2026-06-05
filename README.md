# Coastal Flood Exposure

A workflow to assess coastal inundation exposure for a European coastal city under IPCC AR6 sea-level rise scenarios up to 2100, with Ostend (Belgium) as the case study.

## Files
 
- **coastal_flood_preproprecing_NJR_FINALVERSION.qmd** : data preparation pipeline. Downloads and assembles elevation, population, and SLR data, then saves all inputs needed.
- **coastal_flood_shiny_NJR_FINAL_VERSION.qmd** : interactive Shiny app that loads the preprocessed outputs and lets the user explore flood exposure.
- **coastal_flood_NJR_.html** : rendered HTML version of the preprocessing document.

## How to run

Run all the chunk in the preprocessing qmd file.

## Changes since the last version

New methodological element : Extreme sea-level events layered on top of the IPCC AR6 mean sea-level rise. The previous version represented only the average future water level, which underestimates flood risk because most actual coastal flooding is driven by shortduration extreme events (storm surges and wind setup) rather than by slow rise of the mean. To address this, the workflow now computes a 100 year storm-surge return level from a Generalized Pareto Distribution fitted at eight reference European tide gauges (Oostende, Hoek van Holland, Cuxhaven, Brest, Marseille, Barcelona, Venezia, Helsinki), following the methodology of Hermans et al. (2023). For any selected city, the value from the nearest gauge is used as a regional proxy (with a warning when the nearest gauge lies further than 200 km away). The surge component is treated as stationary, consistent with the IPCC AR6 consensus that future coastal flood hazard will be dominated by sea-level rise rather than by changes in storm characteristics. 

New user functionality : A second checkbox has been added to the dashboard, in addition to the pre-existing ocean-connectivity filter. The new toggle lets the user switch between :

OFF : exposure under mean SLR alone (typical day in the chosen year and scenario);

ON : exposure during a 100-year storm event (mean SLR + stationary surge height).

Replicable for European cities : Firstly, the previous version was hard-coded for Ostend at several places. All city-specific parameters have now been centralised in a single block at the top of the preprocessing file, and the rest of the script reads from these variables. Secondly, improving the cartographic elements adding to the Leaflet map a north arrow. Thirdly, The codebase is now fully commented inline, with every helper function preceded by a short explanation of its purpose, inputs and side-effects. Finaly, all the code is available on GitHub. 
