# COVID-19 Tracker

Course project analyzing global COVID-19 data (Our World in Data format) with static visualizations and three interactive Dash dashboards.

## Requirements

- Python 3.10+
- `project_1_python.csv` in the project root (included in this repository)

## Setup

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

## Running the notebook

Open and run `covid_19_tracker.ipynb` in Jupyter or VS Code. Execute cells in order from top to bottom.

The notebook contains:

1. **Exploratory visualizations** — population bar chart, scatter plot, Czechia vs Germany trends, geo map
2. **Dashboard 1** (port 8050) — country picker with cumulative cases and deaths
3. **Dashboard 2** (port 8051) — continent + metric map using each country's latest reported values
4. **Dashboard 3** (port 8052) — top *n* countries by vaccinations and vaccination coverage

To start a dashboard, run its cell and open the URL printed in the notebook (e.g. `http://127.0.0.1:8050`). Only one Dash server can run per port at a time.

## Data notes

- The dataset is a time series with one row per country per day.
- Dashboards 2 and 3 use **the latest reporting date per country**, not a single global calendar date.
- Some metrics (especially `total_tests` on the latest row) have many missing values; the dashboards exclude countries without data for the selected metric and note how many were hidden.

## Project structure

```
covid_19_tracker.ipynb   # Main notebook (analysis + dashboards)
project_1_python.csv     # OWID-style COVID-19 dataset
requirements.txt         # Python dependencies
```
