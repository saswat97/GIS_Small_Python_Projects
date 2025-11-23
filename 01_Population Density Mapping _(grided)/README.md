# Population Density Mapping (Python + WorldPop + GIS Grid Analysis)

A complete geospatial workflow for extracting and visualizing population and density patterns using open data.

🎥 Related Content (Native GIS Youtube channel  / Live Session)

This project is demonstrated in a 2-hour live session on the Native GIS YouTube channel:

[https://youtu.be/rhyfa3VGzF0]
The session walks through:

  - Data download & AOI setup

  - Code explanation line-by-line

  - Live map interpretation and Q&A

  - How to turn this project into a portfolio asset
    

## 📌 1. What This Project Is About

#### This project builds a high-resolution population and density map for Indirapuram, Ghaziabad using:

* WorldPop R2025A population raster

- Python GIS libraries (GeoPandas, Rasterio, RasterStats)

* 500m × 500m fishnet grid analysis

#### The goal is to take a big raster dataset and convert it into easy-to-understand spatial insights such as:
* Where the most crowded areas are

* How population is distributed across neighborhoods

* Which grid cells contain high-density apartment clusters

* Which areas have lower population and more open space

#### This type of analysis is widely used in:

* Urban Planning

* Smart City Projects

* Infrastructure Load Assessment

* Utility Demand Modeling

* Emergency Response & Coverage Analysis

* Population Health & Service Delivery Optimization

## 📍 2. Area of Interest (AOI): Indirapuram, Ghaziabad

We selected Indirapuram as the AOI because:

It is one of NCR’s most dense residential regions

It has a mix of apartment clusters, parks, commercial areas, and open spaces

It is a perfect example to demonstrate population hotspot mapping

The exact bounding box used (in WGS84 Lat/Long):

* minx = 77.3380   # Left longitude  
* miny = 28.6100   # Bottom latitude  
* maxx = 77.4050   # Right longitude  
* maxy = 28.6580   # Top latitude  


## 🎯 3. Project Purpose / Why This Analysis Matters

Population density is one of the most important datasets in urban analytics. It directly influences:

* 🚑 Emergency service coverage (ambulances, police, fire)

* 🚰 Water supply & sanitation demand

* ⚡ Electricity load distribution

* 🚌 Public transport planning

* 🏫 Placement of schools, hospitals, parks

* 🏙️ Housing stress and real-estate pressures

Indirapuram is a high-density residential hub in NCR with rapid vertical growth.
Understanding where people actually live helps planners and researchers make data-driven decisions.

This project transforms raw geospatial raster pixels into actionable urban insights.


## ⚙️ 4. Technical Overview (What We Did in GIS Terms)

#### This project demonstrates a complete raster-to-vector analytical pipeline in Python:

Step 1 — Raster Preprocessing

- ✔ Load WorldPop (GeoTIFF) population raster
- ✔ Inspect CRS, resolution, extent
- ✔ Clip raster to Indirapuram AOI (reduces processing time)

Step 2 — Vector AOI & Projection

- ✔ Create AOI polygon from bounding box
- ✔ Reproject AOI to a projected CRS (EPSG:3857)
- ✔ Necessary for building grid in meters

Step 3 — Grid (Fishnet) Creation

- ✔ Generate 500m × 500m grid cells
- ✔ Clip grid to AOI (keeps only relevant cells)
- ✔ Reproject grid to raster CRS for zonal stats

Step 4 — Zonal Statistics

- ✔ Extract total population inside each grid cell
- ✔ Compute average population value per pixel
- ✔ Mask nodata values to avoid negative results

Step 5 — Statistical Analysis

- ✔ Compute:

Population per cell

Area (km²)

Population density (people/km²)

- ✔ Generate:

Summary statistics

Top 10 most populated cells

Step 6 — Visualization

- ✔ Static maps (Matplotlib + Contextily)
- ✔ Population (sum) choropleth
- ✔ Population density hotspots
- ✔ Interactive web map (Folium)
- ✔ Add tooltips with population values

Step 7 — Export

- ✔ Maps saved in /outputs/maps/
- ✔ CSV saved in /outputs/tables/
- ✔ Notebook saved for reproducibility

## 🧠 5. Technical Skills Demonstrated

This project highlights expertise in:

✔ Python GIS stack

- GeoPandas

- Rasterio

- RasterStats

- Shapely

- Matplotlib

- Folium

- Contextily

✔ GIS Workflows

- Raster clipping

- CRS handling & reprojection

- Grid generation

- Zonal statistics

- Choropleth mapping

- Density analysis

- Interactive geospatial dashboards

✔ Data Engineering

- Managing large raster files

- Handling nodata values

- Exporting summary tables

- Reproducible notebook workflow

## ⚙️ 6 . Technical Workflow (GIS + Python)

Below is the complete geospatial workflow used in this project.

### **STEP 1 — Data Loading & Inspection**
- Mount Google Drive in Colab
- Load the WorldPop raster  
- Inspect CRS, resolution, and bounds  
- Identify nodata values (e.g., -99999)

### **STEP 2 — Create AOI Polygon**
- Use bounding box for Indirapuram  
- Store as GeoDataFrame (EPSG:4326)  

### **STEP 3 — Clip Raster to AOI**
- Use `rasterio.mask.mask()`  
- Produce a clean raster only for Indirapuram  

### **STEP 4 — Reproject AOI to Meters CRS**
- Convert AOI to EPSG:3857  
- Required for grid creation in meters  
- Ensures accurate grid size (500m)

### **STEP 5 — Create a 500m Fishnet Grid**
- Use numpy range over AOI bounds  
- Build square polygons (500m × 500m)  
- Clip to AOI  
- Reproject grid → raster CRS

### **STEP 6 — Zonal Statistics**
- Use `zonal_stats()`  
- Compute:  
  - `pop_sum` (total people)  
  - `pop_mean`  
- Mask nodata to avoid negative values  

### **STEP 7 — Compute Population Density**
- Reproject grid to EPSG:3857  
- Compute area (km²)  
- Calculate density = pop_sum / area_km2  

### **STEP 8 — Mapping & Visualization**
- Static maps using Matplotlib & Contextily  
- Population grid (quantiles)  
- Density hotspot map  
- Interactive map using Folium (hover values)  

### **STEP 9 — Export Results**
- Save maps under `/outputs/maps/`  
- Save tables under `/outputs/tables/`  
- Save notebook for reproducibility  

---

## 📈 How to Adapt This Project to Another City

To rerun for any other city or AOI:

1. Obtain appropriate WorldPop population raster for that country/city.

2. Replace the AOI bounding box coordinates with your new area.

3. Optionally adjust:

  -Grid size (e.g., 250m, 1km)

  -CRS to a local projection (e.g., UTM zone)

4.Keep the rest of the workflow unchanged:

- Clip raster

- Build grid

- Run zonal stats

- Export and plot

This makes the notebook a reusable template for city-scale population mapping.

## 🙌 Credits & Acknowledgements

1. WorldPop – for open population data.

2. OpenStreetMap contributors – for basemap data.

3. Python open-source geospatial ecosystem:

  - geopandas, rasterio, rasterstats, folium, contextily, matplotlib.

