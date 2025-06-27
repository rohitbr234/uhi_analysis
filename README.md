# Modeling Urban Heat Island Intensity Using Satellite Imagery and Machine Learning

This repository contains all code and scripts used in the study  
**"Modeling Urban Heat Island Intensity Using Satellite Imagery and Machine Learning"**  
by Rohit Ramesh (Tampa Preparatory School, June 2025).

The project explores the use of satellite-based remote sensing and machine learning to estimate Urban Heat Island (UHI) intensity across 20 urban-rural region pairs globally. Using Landsat 8 imagery, surface features were extracted and used to train Random Forest regression models that predict Land Surface Temperature (LST) and derive UHI intensity.

## Overview

- Satellite data was processed using Google Earth Engine.
- Key surface features extracted: NDVI, NDBI, Albedo, Built Surface, Slope, and Elevation.
- A Random Forest model was trained for each city to estimate LST.
- UHI intensity was computed as the difference between urban and rural LST.
- SHAP analysis was used to interpret model predictions.

## Requirements

To run the code, install the following Python libraries:

```
pip install earthengine-api geemap pandas numpy scikit-learn shap seaborn matplotlib
```

You must also authenticate with Google Earth Engine:

```python
import ee
ee.Authenticate()
ee.Initialize()
```

## Running the Code

1. Run the main Jupyter notebook (`uhi_modeling.ipynb`) or Python scripts.
2. Ensure GEE authentication and internet access for Earth Engine processing.
3. Code will:
   - Preprocess Landsat 8 and GHSL imagery
   - Sample and label urban and rural pixels
   - Train Random Forest models per city
   - Generate UHI intensity predictions and visualizations
   - Display SHAP-based feature importance

## Data Sources

- Landsat 8 Collection 2 Tier 1 Level 2 (USGS)
- Global Human Settlement Layer (GHSL Built Surface)
- SRTM Digital Elevation Model (NASA)
- ERA5-Land Hourly Temperature (ECMWF)

All data was accessed and processed using Google Earth Engine.

## Results

- Mean absolute error between predicted and observed UHI intensity was under 0.15°C across all cities.
- Cities like Singapore, Sydney, and Buenos Aires exhibited strong positive UHI effects.
- Negative UHI intensities in cities such as Cairo and Mexico City were linked to elevation and surrounding terrain.
- Feature importance and SHAP analysis highlighted Built Surface and NDBI as the most influential predictors.

## Citation

If you use this code or reference this work, please cite:

Rohit Ramesh. *Modeling Urban Heat Island Intensity Using Satellite Imagery and Machine Learning*. Preprint, June 2025.

## License

This project is made available for academic and research use only. Please contact the author for questions or reuse beyond educational purposes.
