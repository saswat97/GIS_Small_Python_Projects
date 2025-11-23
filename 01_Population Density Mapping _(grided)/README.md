# Population Density Mapping (Python + WorldPop + GIS Grid Analysis)

A complete geospatial workflow for extracting and visualizing population and density patterns using open data.


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


