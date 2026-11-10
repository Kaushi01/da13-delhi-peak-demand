# When will Delhi's power demand peak this summer?

AccioJob Spin Build Pitch · Data Analytics · Project DA-13

**Stakeholder:** an AC brand planning inventory, or a power company planning supply.
**Decision:** how much stock or supply to plan for at each heat level (40 °C, 43 °C, 46 °C).

## Key findings (from the dashboard)

| Metric | Value |
|---|---|
| Extra demand per +1 °C of heat | 171 MW |
| Underlying growth per year (heat held constant) | 115 MW |
| Jul–Sep demand vs. other months | 1,203 MW higher |
| Model fit | R² = 0.57 |

**Planning table** (daily peak demand, MW)

| Temp | Confidence | Expected | Typical-day low | Typical-day high |
|---|---|---|---|---|
| 40 °C | Medium | 5,924 | 4,770 | 7,079 |
| 43 °C | Medium | 6,437 | 5,282 | 7,593 |
| 46 °C | Low (no days at 46 °C in data) | 6,950 | 5,794 | 8,107 |

**Recommendation:** plan for the upper end of each range (about 7,100 / 7,600 / 8,100 MW at 40 / 43 / 46 °C, 2023 level), add a reserve for growth since, and prepare for a June–July peak.

Full memo: [`memo/insight_memo.md`](memo/insight_memo.md)

## Repo structure

```
data/         raw data notes (large files not committed) + processed output
src/          analysis.py - data pull, cleaning, model
docs/         data_sources.md, cleaning_steps.md
memo/         one-page insight memo
dashboard/    dashboard PDF export (+ link)
notebook/     Delhi_Summer_Power_Demand_Analysis.ipynb
```

## Dashboard
- PDF: `dashboard/dashboard.pdf`
- Live link: TODO (paste Looker Studio link)

## Video
TODO (paste Loom / YouTube link)

## How to reproduce
```
pip install -r requirements.txt
python src/analysis.py
```
See `docs/data_sources.md` for where to get the raw files and `docs/cleaning_steps.md` for each cleaning step.

## Limits
- Data ends April 2024.
- No humidity data.
- Temperature is from a weather-model grid (Open-Meteo), not the IMD station.
- R² = 0.57, so about 43% of variation is unexplained.
- 2020 lockdown period removed.
- 46 °C is a trend extension: no days at 46 °C in the data.

## Sources
- Grid-India daily demand, via Hunt & Bloomfield: Zenodo, DOI 10.5281/zenodo.14983361
- Open-Meteo historical weather API: https://open-meteo.com
