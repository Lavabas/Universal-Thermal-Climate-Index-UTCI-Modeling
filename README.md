# Universal Thermal Climate Index (UTCI) Modeling over a Custom South Asian Region using FLDAS & Python
## Overview

The Universal Thermal Climate Index (UTCI) is a widely used measure for assessing human thermal comfort under varying climatic conditions. It integrates air temperature, wind speed, humidity, and mean radiant temperature into a single, physiologically relevant index, making it especially valuable for monitoring heat stress and climate risk.

This project computes spatio-temporal UTCI values for a custom Region of Interest (ROI) covering Sri Lanka, India, and surrounding South Asian countries for the year 2020. The workflow integrates NASA FLDAS climate reanalysis data, Google Earth Engine, and open-source Python tools to extract meteorological variables, compute UTCI, and visualize thermal comfort patterns across the region.

The analysis demonstrates how global reanalysis datasets can be combined with climate indices to produce actionable geospatial insights, supporting research in climate adaptation, public health, early warning, and environmental monitoring.

## Data Sources
### NASA FLDAS – Famine Early Warning Systems Network Land Data Assimilation System
Dataset: NASA/FLDAS/NOAH01/C/GL/M/V001
Variables used:
1. Tair_f_tavg → Air Temperature
2. Wind_f_tavg → Wind Speed
3. Qair_f_tavg → Specific Humidity
4. RadT_tavg → Mean Radiant Temperature

## Tools & Libraries Used
1. Google Earth Engine (GEE) – Data extraction and preprocessing
2. geemap – Interactive ROI selection & GEE-Python integration
3. xarray – Multidimensional climate data handling
4. xclim – Climate indices, including UTCI
5. NumPy – Array operations
6. Matplotlib – Visualization

### Monthly Air Temperature Maps (tas) — 2020
<img width="1695" height="590" alt="image" src="https://github.com/user-attachments/assets/a7cce718-dcca-4253-ac22-29fbc2b8473c" />

### Monthly UTCI Maps (°C)
<img width="1711" height="590" alt="image" src="https://github.com/user-attachments/assets/5d73f48d-af8a-4676-b5ab-eb7c74d0b2de" />

## Notes
- FLDAS provides 0.1° (~11 km) spatial resolution; UTCI results reflect this resolution.
- Temperature conversion from Kelvin → Celsius was applied before computing UTCI.
- Relative humidity derived from FLDAS is unitless and compatible with the xclim function.
- Values of UTCI below –50°C or above 50°C may indicate unstable atmospheric conditions or missing data artifacts.
