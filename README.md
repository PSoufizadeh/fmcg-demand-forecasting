# Demand Forecasting for FMCG

A calendar-aware demand forecasting framework featuring direct SKU-level forecasting and hierarchical subcategory-to-SKU forecasting.

## Workflows

- **SKU-based:** preprocessing, Gregorian/Hijri calendar features, clustering and demand segmentation, normalization, statistical pre-estimation, feature engineering, and multi-model forecasting.
- **Subcategory-based:** hierarchy mapping, aggregation, share forecasting, multi-metric model selection, median ensemble, normalized SKU allocation and reconciliation checks.

## Repository structure

| Notebook | Purpose |
|---|---|
| `notebooks/01_sku_based_forecasting.ipynb` | Direct SKU-level forecasting |
| `notebooks/02_subcategory_based_forecasting.ipynb` | Hierarchical forecasting |

## Local setup

Install dependencies with `pip install -r requirements.txt`, then open one notebook in Jupyter. Run its setup cell first. Provide authorized local Excel inputs; the notebooks create their working directories under `workspace/`.

For the direct workflow, place `monthly_sales.xlsx` in `workspace/Input/` with columns `year`, `Month`, `Material Code`, `Sku Name`, `Vol (Kg)`. For the hierarchical workflow, place `monthly_sales.xlsx` and `SubCat.xlsx` in `workspace/SubCatStrategy/Input/`. The sales file additionally requires `Val($)`, `Box`, `RSP($)`; the hierarchy file requires `Code`, `SKU Name (English)`, `Sub Cat`. These are generic interface fields, not actual records. Optional manual clustering input may be supplied locally as required by the selected workflow.

The optional environment variable `FORECAST_TARGET_MONTH` selects a specific monthly forecast export. No historical business date is configured.

## Confidentiality and limitations

This repository contains selected original forecasting code adapted for public technical review. Proprietary commercial datasets, product-level records, forecasts, operational results and historical notebook outputs are intentionally excluded. The notebooks require local inputs; they have not been revalidated end to end after public-release cleanup. Configuration examples are not production recommendations. Original modeling logic is retained, including exploratory and legacy wrappers; this is not a production-ready package. Review forecast validation, calendar assumptions and reconciliation before operational use.

For technical inquiries or potential collaboration, contact **Parham Soufizadeh** through the contact information on the GitHub profile.

No license is granted by this repository.
