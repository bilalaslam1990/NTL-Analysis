
# NTL_TX_FINAL

This repository contains a Jupyter Notebook for analyzing Nighttime Light (NTL) and cloud cover data over Texas counties using raster-based geospatial techniques.

## 🛰️ Purpose

To compute county-level statistics on NTL brightness and classify cloud cover using the decoded 16-bit Quality Flag (QF) bitmask from satellite observations.

## 🔍 Key Features

- Extracts cloud confidence using **bits 0–1** from the 16-bit QF flag:
  - `00` → Confident Clear
  - `01` → Probably Clear
  - `10` → Probably Cloudy
  - `11` → Confident Cloudy
- Performs **zonal statistics** on both NTL and cloud rasters
- Outputs a CSV with daily county-level summary:
  - Mean and Median NTL
  - % distribution of cloud classes

## 📁 Files

- `NTL_TX_FINAL_UPDATED.ipynb` — Main notebook with corrected QF cloud logic
- `README.md` — Project overview and instructions

## ▶️ How to Run

1. Place all `NTL` and `Cloud QF` raster files in a folder.
2. Load `counties_gdf` shapefile with a `CNTY_NM` field.
3. Update file paths and run the notebook to export `output_csv`.

## ✅ Output

A CSV file with the following columns:
- County
- Date
- Mean_NTL
- Median_NTL
- Total_Pixels
- Confident_Clear_%
- Probably_Clear_%
- Probably_Cloudy_%
- Confident_Cloudy_%

---

Created by **Bilal Aslam**. This project supports open science and reproducible remote sensing workflows.
