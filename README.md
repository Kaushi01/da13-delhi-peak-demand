# When will Delhi's power demand peak this summer?

AccioJob Spin Build Pitch · Data Analytics · Project DA-13

**Stakeholder:** an AC brand planning inventory, or a power company planning supply.
**Decision:** how much stock or supply to plan for at each heat level (40 °C, 43 °C, 46 °C).

## Key findings

| Metric | Value |
|---|---|
| Extra demand per +1 °C of heat | 171 MW |
| Underlying growth per year (heat held constant) | 115 MW |
| Jul–Sep demand vs. other months | 1,203 MW higher |
| Model fit | R² = 0.57 |

## Planning table (daily peak demand, MW)

| Temp | Confidence | Expected | Typical-day low | Typical-day high |
|---|---|---|---|---|
| 40 °C | Medium | 5,924 | 4,770 | 7,079 |
| 43 °C | Medium | 6,437 | 5,282 | 7,593 |
| 46 °C | Low (no days at 46 °C in data) | 6,950 | 5,794 | 8,107 |

## Recommendation

Plan for the upper end of each range, not the middle: about 7,100 MW at 40 °C, 7,600 MW at 43 °C and 8,100 MW at 46 °C (2023 level), plus a reserve for growth since. Prepare for the peak in June to July.

## Limits

- Data ends April 2024.
- No humidity data.
- Temperature is from a weather-model grid (Open-Meteo), not the IMD station.
- R² = 0.57, so about 43% of variation is unexplained.
- 2020 lockdown period removed.
- 46 °C is a trend extension: there are no days at 46 °C in the data.

## Files

- Dashboard: `When_will_Delhi's_power_demand_peak_.pdf`
- Analysis notebook: `Delhi_Summer_Power_Demand_Analysis.ipynb`

## Sources

- Grid-India daily demand, via Hunt & Bloomfield: Zenodo, DOI 10.5281/zenodo.14983361 (https://doi.org/10.5281/zenodo.14983361)
- Open-Meteo historical weather API: https://open-meteo.com
