# East River Water Quality

Analysis of water-quality data my class collected on the East River on October 6, 2026, during *A Day in the Life of the Hudson & Harbor*, an annual field study organized by Columbia University's Lamont-Doherty Earth Observatory and partners.

## Why this project
On October 6, I waited for the precipitate in my sample bottle to settle before adding the third reagent to measure dissolved oxygen. The saturation chart assumes warmer water holds less oxygen, but the sun that warms the river also feeds algae that produce more. Which push moves the reading? Then the salinity meters disagreed: same spot, minutes apart. Before asking what drives dissolved oxygen, I had to know which readings to trust. This repository starts there.

## Questions
1. How much do salinity readings taken at the same site disagree, and why?
2. Relative to saturation, how much dissolved oxygen did the water hold once salinity is taken into account?

## Data
`data/ditl_2026-10-06_east_river.csv`: 18 measurements (6 groups × 3 trials) of salinity, water temperature, pH, turbidity, and dissolved oxygen, taken at one site between 10:34 and 12:30. Group names are replaced with letters A–F. Values are transcribed as recorded; only formats were standardized (units removed, times written as HH:MM).

## Findings
**Salinity** ([notebook](notebooks/01_salinity_by_group.ipynb)): Readings within a group mostly agree, but groups fall into two levels, about 26 ppt and 28–29 ppt. Groups B and F measured back to back yet differ by 2–3 ppt, which points to the meters or how they were read rather than the water itself. One reading (36 ppt) is saltier than the open ocean and was treated as an outlier.

**Dissolved oxygen** ([notebook](notebooks/02_dissolved_oxygen.ipynb)): The saturation values the groups reported match a freshwater saturation table. Correcting for salinity raises saturation by about 15 percentage points, to roughly 100–117%; given the test kit's whole-number resolution, the water was approximately saturated.

## Limitations
- One site on one day; some values appear to be shared across groups, so the 18 readings are not all independent.
- The salinity meters and DO kit read only whole numbers.
- With this data alone, measurement error cannot be separated from tidal change.

## Next steps
- Add year-round NYC DEP Harbor Water Quality data to test how dissolved oxygen depends on temperature and salinity.
- Share the salinity correction with my teacher so next year's saturation values account for it.

## References
- Weiss, R. F. (1970). The solubility of nitrogen, oxygen and argon in water and seawater. *Deep-Sea Research*, 17, 721–735.
- Lamont-Doherty Earth Observatory, *A Day in the Life of the Hudson & Harbor*.
