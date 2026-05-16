# SAMOS2026-Core3CS-ASAYIKO

## Visualizing Remote-Sensed Ocean Colour Data

**Course:** SAMOS2026 Core 3CS  
**Group:** ASAYIKO  
**Contributors:** Koketso, Asanda, Yibanathi  
**Date:** May 2026  

---

## Project Overview
This project analyzes and visualizes oceanographic data for the St Helena Bay and 
Cape Columbine region, South Africa, using ESA-CCI Ocean Colour satellite climatology. 
We combine chlorophyll-a concentration maps, bathymetry data, and time series analysis 
to investigate seasonal cycles and spatial variability in phytoplankton biomass along 
the Benguela Current upwelling system. St Helena Bay and Cape Columbine were selected 
due to their position within one of the world's most productive eastern boundary 
upwelling systems, making this an ideal region to observe strong seasonal chlorophyll 
signals driven by wind-forced nutrient upwelling from depth.

---

## Repository Structure

```
SAMOS2026-Core3CS-ASAYIKO/
├── E5/
│   └── Exercise5.ipynb          # Main project notebook
├── README.md                    # This file
├── .gitignore                   # Git configuration
└── data/                        # Data files (not tracked due to size)
```

---

## Datasets

### 1. ESA-CCI Ocean Colour Climatology
- **Source:** [ESA Ocean Colour CCI](https://www.oceancolour.org/)
- **File:** `ESACCI-OC-MAPPED-CLIMATOLOGY-1M_MONTHLY_4km_PML_CHL-fv5.0.nc`
- **Variable:** `chlor_a` — chlorophyll-a concentration (mg m⁻³)
- **Temporal coverage:** Monthly climatology derived from 1998–2020
- **Spatial resolution:** 4 km nominal at equator
- **Dimensions:** 12 months × 4320 lat × 8640 lon
- **Institution:** Plymouth Marine Laboratory
- **Sensors:** SeaWiFS, MODIS, MERIS, VIIRS, OLCI

### 2. Bathymetry
- **Source:** [GMRT — Global Multi-Resolution Topography](https://www.gmrt.org/)
- **Format:** NetCDF (CF Convention)
- **Region:** St Helena Bay, South Africa (17.5°–19.0°E, 33.5°–32.0°S)

---

## Quick Start

1. **Obtain data files:**
   - Download `ESACCI-OC-MAPPED-CLIMATOLOGY-1M_MONTHLY_4km_PML_CHL-fv5.0.nc` from the SAMOS2026 course portal
   - Download bathymetry from [GMRT MapTool](https://www.gmrt.org/services/mapserver/)
   - Place both files in the `E5/` directory

2. **Run the notebook:**
   ```bash
   cd E5
   jupyter lab Exercise5.ipynb
   ```

---

## Notebook Contents

The notebook `Exercise5.ipynb` is structured as follows:

1. **Introduction** — Overview of the study region and scientific motivation
2. **Dataset Metadata** — NetCDF info for both bathymetry and chlorophyll files
3. **Bathymetry Map** — Spatial map of seafloor depth using an appropriate colormap
4. **Chlorophyll Maps**
   - Mean annual chlorophyll map (log scale)
   - Faceted figure: 12 monthly chlorophyll maps showing seasonal variation
5. **Time Series Analysis** — Seasonal cycle comparing the St Helena Bay regional 
   mean with a single grid point (32.6°S, 17.7°E)
6. **Conclusion** — Summary of seasonal cycles and spatial variability

---

## Study Region

| Parameter        | Value                        |
|------------------|------------------------------|
| Region           | St Helena Bay, South Africa  |
| Latitude bounds  | 33.5°S – 32.0°S              |
| Longitude bounds | 17.5°E – 19.0°E              |
| Single grid point| 32.6°S, 17.7°E               |
| Upwelling system | Benguela Current             |

---

## Key Results

- Chlorophyll-a peaks in **March–April** (austral autumn), consistent with enhanced 
  Benguela upwelling bringing nutrient-rich waters to the surface
- A clear **summer minimum** is observed in July–August when stratification suppresses 
  upwelling intensity
- The single grid point follows the regional seasonal pattern but shows lower absolute 
  values, reflecting offshore positioning away from the most productive coastal waters

---

## Requirements

The following Python packages are required to run the notebook:

- xarray
- numpy
- matplotlib
- cartopy (for map projections)
- netCDF4 (for reading .nc files)

To install all dependencies:

```bash
pip install xarray numpy matplotlib cartopy netCDF4
```

Or if using conda (recommended for this project):

```bash
conda install xarray numpy matplotlib cartopy netCDF4
```

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/koketso18232/SAMOS2026-Core3CS-ASAYIKO.git
   cd SAMOS2026-Core3CS-ASAYIKO
   ```

2. Download the ESA-CCI dataset from the course portal and place it in the 
   same folder as `Exercise5.ipynb`

3. Launch JupyterLab:
   ```bash
   jupyter lab
   ```

4. Open and run `Exercise5.ipynb` from top to bottom

> **Note:** The NetCDF dataset (~1.7 GB) is not tracked in this repository due to 
> file size limits. It must be downloaded separately from the course portal.

---

## Methodology

- **Data Processing:** xarray for NetCDF handling and spatial subsetting
- **Visualization:** Cartopy for map projections, matplotlib for figures
- **Temporal Analysis:** Monthly climatology computed from 1998–2020 satellite records
- **Spatial Mapping:** 4 km resolution regridded to PlateCarree projection
- **Log-scale visualization** applied to chlorophyll due to wide dynamic range

---

## Attribution & Acknowledgments

- **Course:** SAMOS2026 Core 3CS, University of Cape Town
- **Instructors/Mentors:** Prof. Vichi / Mr Magata
- **ESA Data:** Ocean Colour Climate Change Initiative v5.0
- **Bathymetry:** Global Multi-Resolution Topography v4.1
- **Colormaps:** `cmocean` package (Thyng et al., 2016)

---

## References

Thyng, K. M., Greene, C. A., Hetland, R. D., Zimmerle, H. M., & DiMarco, S. F. (2016). True colors of oceanography: Guidelines for effective and accurate colormap selection. *Oceanography*, 29(3), 9–13.

Ocean Colour Climate Change Initiative (2023). Version 5.0. Retrieved from http://www.esa-oceancolour-cci.org

---

## License

This project was completed as part of the SAMOS2026 course at the University of Cape Town. 
All analysis code is available for educational use.
