# 🌳 Heatwave Mitigation with Shade: A Data-Driven Approach to Urban Cooling
**CSE 475: Machine Learning — Fall 2025**  
Arizona State University  

---

## 📘 Overview
This repository contains the code and data workflow for our project  
**“Heatwave Mitigation with Shade: A Data-Driven Approach to Urban Cooling.”**  

The goal of this project is to develop a **data-driven machine learning model** that predicts and visualizes shaded areas across urban environments, starting with the Phoenix metropolitan region.  

By combining vegetation, elevation, temperature, and land-cover data, our model helps identify **heat-vulnerable zones** and supports **shade-focused urban planning**.

Key objectives:
- Build a unified geospatial dataset integrating NDVI, terrain, temperature, and land-cover data  
- Train interpretable models (Random Forest, Gradient Boosting) to predict shade index values (0–1)  
- Use clustering to reveal shade/heat spatial patterns  
- Visualize predictions interactively via **Folium maps**


---

## ⚙️ Setup & Usage

### Option 1 — Run on Google Colab
1. Open the notebook directly from GitHub:  
   **File ▸ Open Notebook ▸ GitHub ▸** paste the repo URL.  
2. Run the first cell to install dependencies:
   ```python
   !pip install geopandas rasterio rioxarray shapely scikit-learn folium matplotlib pandas numpy tqdm
   ```
3. Mount your Google Drive (optional) to access datasets:
   ```python
    from google.colab import drive
    drive.mount('/content/drive')

   ```
4. Place datasets in /content/drive/MyDrive/shade-ml/data/raw/ and run cells sequentially.

---

## Workflow Summary

1. **Preprocessing**: Harmonize coordinate systems (EPSG:32612), grid the study area, compute NDVI, slope, and aspect.
2. **Label Generation**: Overlay ArcGIS shade polygons to compute a continuous shade fraction per grid cell.
3. **Modeling**:
- Random Forest / Gradient Boosting Regressor
- Optional classification variant (shade_bin ≥ 0.5)
- Cross-validation using train/test split
4. **Evaluation**: R², RMSE, MAE (regression) or accuracy/F1 (classification).
5. **Visualization**: Folium maps of predicted shade and feature importance charts.
6. **Clustering (optional)**: K-Means for identifying shade/heat hotspots.

## Team

| Name | ASURITE Email |
|------|------|
| **Yaman Shqeirat** | yshqeira@asu.edu |
| **Lucia Li** | yuecongl@asu.edu |
| **Shiyuan Liu** | sliu268@asu.edu |
| **Zixuan Yang** | zyang228@asu.edu |


## Licensing

This project is licensed under the MIT License — see the LICENSE file for details.
You’re free to use, modify, and distribute the code with attribution.
