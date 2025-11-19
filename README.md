
# PRISM County-Level Daily Weather Dataset (1990–2024)

This repository contains a complete, reproducible pipeline for generating **daily, county-level PRISM weather data** for the contiguous United States (48 states).  
The workflow includes automated downloading, GPU-accelerated raster aggregation, and efficient parallel processing for long historical periods (1990–2024).

The final dataset provides **daily precipitation, minimum temperature, and maximum temperature** for each U.S. county (FIPS), derived from **PRISM 4km daily raster data**.

---

## ⚡ Key Features

### **1. Full PRISM Automation**
- Automatically downloads PRISM 4km daily TIF files
- Organized by element (`ppt`, `tmin`, `tmax`) and year structure

### **2. GPU-Accelerated County Aggregation**
- CuPy-based pixel processing (NVIDIA GPU compatible)
- Raster → County aggregation based on precomputed pixel-to-county masks
- Handles 4km × 4km resolution efficiently

### **3. Optimized for Scale**
- Processes 48 states × 3143 counties × 35 years of daily data
- Multithreaded + GPU hybrid pipeline
- Year-by-year export to keep memory usage small

### **4. Clean, Analysis-Ready Outputs**
Each row corresponds to one county-day:

| Column | Description |
|--------|-------------|
| `date` | Date in `YYYY-MM-DD` format |
| `fips` | 5-digit county FIPS code |
| `ppt`  | Daily precipitation (mm/day) |
| `tmin` | Minimum temperature (°C) |
| `tmax` | Maximum temperature (°C) |

### **5. Contact

For questions, feel free to open an issue or contact:
Zhangchi (Bruce) Cai
UW–Madison, Agricultural & Applied Economics
zcai98@wisc.edu



### **6. Data Sources (Attribution)

This project uses original climate data from:

PRISM Climate Group, Oregon State University
https://prism.oregonstate.edu

You must cite PRISM when using data derived from PRISM.

If you use the county-level processed dataset created by this repository, please cite:

Cai (2025). PRISM County-Level Weather Dataset (1990–2024). GitHub Repository.
URL: https://github.com/YOUR_USERNAME/prism-county-weather
---



