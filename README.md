# Fan Journey Analytics for Netflix House–Style Experiences

A Netflix-style **fan journey analytics** work sample that treats the **RetailRocket** public interaction logs as a *phygital* proxy (physical + digital) for the journey states that matter operationally: **discovery → intent → conversion → return**.

This repo is designed as a **reviewer-friendly work sample**: one notebook + one report + a curated set of figures, with clear metric definitions and an operational “decision loop” framing.

---

## What’s inside

- **Notebook (primary artifact):** `notebooks/N_Fan_Journey_WorkSample_Blueprint_RetailRocket.ipynb`
- **Report (recommended for reviewers):** `report/Fan_Journey_Analytics_Netflix_House_WorkSample.pdf`
- **Key figures (used in the report):** `figures/`
- **Data instructions (no raw data stored here):** `data/README.md`

> ⚠️ This repo intentionally does **not** include the raw RetailRocket CSVs (they are large). See `data/README.md` for download instructions.

---

## Key findings (high level)

1) **Demand is highly time-dependent** (near order-of-magnitude intraday swing), motivating daypart-aware staffing and routing.  
2) **Funnel bottleneck is upstream** (discovery → intent), suggesting discovery relevance + commitment friction are the highest-leverage levers.  
3) **Forecasting baseline** (Gradient Boosting) achieves planning-oriented accuracy (MAE/MAPE), but benefits materially from exogenous drivers (campaign calendar, seasonality, geo/timezone).  
4) **Recommendation baseline ladder:** item-to-item co-visitation outperforms popularity on offline ranking metrics (Precision/Recall/NDCG @ K=10).  
5) **Cold start is operational:** diversified slates + metadata similarity + launch observability (“Experience Health”).  
6) **Measurement rigor:** experiment feasibility is constrained by low base-rate conversion; quasi-experimentation is essential for venue rollouts.

(See the report PDF for full results and figures.)

---

## How to run

### Option A — Google Colab (recommended)
1. Open the notebook in Colab.
2. Mount Google Drive and set `BASE_DIR` to your dataset folder.
3. Run cells top-to-bottom.

> Tip: Add a Colab badge once you have a public notebook link.

### Option B — Local (Python 3.10+)
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
Open and run the notebook in Jupyter.

---

## Data

This project uses the **RetailRocket** dataset (events + item properties + category tree).  
Download instructions and expected filenames are in: `data/README.md`.

---

## Repository structure

```text
fan-journey-analytics-netflix-house/
  README.md
  notebooks/
  report/
  figures/
  data/
  requirements.txt
  .gitignore
  LICENSE
```

---

## License

MIT (see `LICENSE`).
