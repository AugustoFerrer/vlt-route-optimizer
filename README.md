# 🚊 VLT João Pessoa - Urban Routing Simulator

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white)
![Mapbox/Folium](https://img.shields.io/badge/Folium-000000?style=for-the-badge&logo=map&logoColor=white)

## 📌 Overview
This project is a Data-Driven Proof of Concept (PoC) for a Light Rail Transit (VLT) system in João Pessoa, Paraíba, Brazil. Rather than a static architectural model, this repository hosts a live spatial simulator designed to calculate the viability of a new transit axis connecting the Mangabeira region to the City Center.

## 🚀 Core Engines & Features

*   **Multicriteria Graph Optimization:** Uses `OSMnx` to extract the real urban road network and calculates the mathematical path of least resistance between stations.
*   **Topographic & Environmental Guillotine:** Reads Digital Elevation Models (DEM) via `rasterio` to strictly eliminate routes with steep slopes (above 6%) and applies infinite costs to environmental preservation areas (ICMBio data).
*   **Socio-Demographic Heatmaps:** Cross-references the optimized route with population density and IBGE Census data using `GeoPandas` to justify the track layout based on actual travel demand.
*   **Interactive Visualization:** Outputs dynamic, interactive maps using `Folium`, complete with topological profiles and clickable station markers (e.g., UFPB, Torre Medical Hub).

## 📂 Project Structure

*   `01_v2_otimizador_multicriterio.ipynb`
    **Objective:** Calculate the route of least cost through the city's real road network, avoiding hills and residential expropriations.
*   `02_mapa_demanda_folium.ipynb`
    **Objective:** Overlay the optimized route with population density heatmaps to validate the chosen path.
*   `03_simulador_impacto.ipynb`
    **Objective:** Quantify the time saved for the average worker comparing the proposed VLT against current bus systems.

## 🛠️ How to Run

1. Clone this repository to your local machine.
2. Ensure you have Python installed, then install the required geospatial libraries using the requirements file:
   ```bash
   pip install -r requirements.txt
   ```
3. Open the notebooks in Jupyter or VS Code to run the simulations. 

*(Note: Raw `.tif` satellite imagery and heavy `.shp` files are kept locally and excluded from this repository via `.gitignore` to adhere to GitHub's storage limits).*

## 🗺️ Roadmap & Next Steps
*   **Phase 1 (Current):** OpenStreetMap graph extraction and preliminary topographical viability.
*   **Phase 2:** Replace OSM extraction with direct integration from the official GIS database of the João Pessoa City Hall (Semob/CBTU).
*   **Phase 3:** Advanced demographic cross-referencing with specific commercial and medical hubs.
