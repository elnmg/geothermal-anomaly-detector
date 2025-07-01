
# Geothermal Anomaly Detection using Unsupervised Learning (NDVI, LST, InSAR)

## Overview

This project explores geothermal prospecting in remote areas by applying **unsupervised anomaly detection** techniques on remote sensing datasets—specifically NDVI (Normalized Difference Vegetation Index), LST (Land Surface Temperature), and InSAR (surface deformation). By utilizing **Isolation Forest**, the system identifies thermal and deformation anomalies that may indicate geothermal activity, bypassing the need for costly and logistically challenging field surveys.

Indonesia, located on the Pacific Ring of Fire, holds 40% of the world’s geothermal reserves. However, conventional exploration methods are expensive and disruptive. This project leverages freely available satellite data and machine learning to offer a scalable and sustainable alternative.

## Key Features

- ✅ **Unsupervised ML (Isolation Forest)** to detect anomalies without ground truth labels
- 🛰️ Uses satellite-derived **NDVI, LST, and InSAR** datasets
- 🌋 Designed for **remote areas** with limited accessibility
- 🌍 Focus area: **Solok–Alahan Panjang, West Sumatra, Indonesia**
- 📈 Outputs: Interactive anomaly maps, time-series plots, and shapefile-compatible CSVs

## Methodology

1. **Data Collection**
   - NDVI from Sentinel-2 (Google Earth Engine)
   - LST from MODIS/MYD21A1D
   - InSAR surface deformation from Sentinel-1 (GEE-based InSAR processors)

2. **Preprocessing**
   - Normalization and merging of multi-temporal datasets
   - Conversion into a geospatial tabular format

3. **Modeling**
   - Isolation Forest trained on NDVI, LST, and InSAR values
   - Anomalies scored and filtered using quantile thresholding

4. **Visualization**
   - Interactive map using `folium`
   - Comparison with known geothermal locations and hot springs

## Results

- Successfully detected several zones aligning with known geothermal sites
- Anomalous regions highlighted around **Mt. Talang** and **Alahan Panjang**
- Demonstrated robustness without requiring labeled training data

## Installation

```bash
git clone https://github.com/yourusername/geothermal-anomaly-detector.git
cd geothermal-anomaly-detector
pip install -r requirements.txt
```

## Usage

```python
python main.py
```

You can customize the study region, input data, or model parameters in `config.py`.

## Live Demo

> 🚀 Coming Soon: [Hugging Face Spaces App](https://huggingface.co/spaces/elnmg/geothermal-anomaly)

## Folder Structure

```
.
├── data/               # Preprocessed CSV datasets
├── src/                # Core code (modeling, visualization, etc.)
├── notebooks/          # Jupyter notebooks for EDA and testing
├── output/             # Anomaly maps and result logs
├── README.md
└── requirements.txt
```

## Benefits

- 🌱 **Eco-friendly**: Reduces field intervention
- 🧠 **Unsupervised**: No dependency on labeled data
- 🔍 **Scalable**: Easily applicable to other geothermal regions globally

## Future Work

- Integrate DEM and geological layers for higher precision
- Train additional models (e.g., One-Class SVM, Autoencoders)
- Validate predictions through limited field surveys

## References

- Li et al. (2023). Remote Sensing in Geothermal Exploration.
- Yuhendra et al. (2020). Anomaly Detection Using InSAR and Thermal Data.
- Cumming, W. (2009). Geothermal Resource Conceptual Models Using Surface Exploration Data.
- Fialko, Y. (2004). Probing the mechanical properties of seismically active crust with InSAR. Nature.
- Bignall, G., & Browne, P. R. L. (2000). Geology of the Rotokawa geothermal field, Taupo Volcanic Zone, New Zealand
- Jensen, J. R. (2007). Remote sensing of the environment: An earth resource perspective (2nd ed.)


## License

MIT License © 2025 [elnmg]
