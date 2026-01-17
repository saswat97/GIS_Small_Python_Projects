# Building Footprint Extraction using Edge Detection (GIS + Python)

## LiVE RECORDED VIDEO
A complete geospatial workflow for extracting and visualizing Builing Footprints patterns using open data.

🎥 Related Content (Native GIS Youtube channel / Live Session): 

This project is demonstrated in a 2-hour live session on the Native GIS YouTube channel:





## 📌 Overview
This project demonstrates a **baseline GIS + Computer Vision workflow** to extract
**candidate building footprints** from high-resolution aerial imagery using
classical image processing techniques (no AI / no training).

The workflow converts aerial imagery into:
- edge representations
- cleaned raster blobs
- vector building footprint candidates (GeoJSON)

Results are evaluated against **OpenStreetMap (OSM) building footprints**.

---

## 🎯 Why This Project Matters
Building footprints are critical for:
- urban planning
- disaster exposure analysis
- utility and telecom network design
- infrastructure inventory mapping

This project demonstrates how **pixels can be transformed into GIS-ready polygons**
using explainable, lightweight methods — ideal as a **baseline or preprocessing step**
before machine learning models.

---

## 📍 Study Area (AOI)
- Example AOI: **Gilbert, Arizona (USA)**
- Small suburban area (1–5 sq km) selected for:
  - fast processing
  - clear rooftop visibility
  - YouTube-friendly demonstration

AOI geometry is stored in `data/aoi/`.

---

## 🛰️ Data Sources
- **NAIP aerial imagery** (via Microsoft Planetary Computer STAC)
- **OpenStreetMap building footprints** (via OSMnx)

All data sources are open and publicly accessible.

---

## 🧠 Workflow Summary
1. Define Area of Interest (AOI)
2. Search & load NAIP imagery via STAC
3. Preprocess imagery (grayscale, blur, CLAHE, gamma)
4. Extract edges using Canny edge detection
5. Apply morphological operations to clean edges
6. Identify connected components (candidate buildings)
7. Convert raster blobs to vector polygons
8. Filter and simplify polygons
9. Compare against OSM buildings (IoU & overlap metrics)
10. Export maps, vectors, and evaluation tables

---

## 📊 Outputs
| Type | Location |
|----|----|
| Before/After panel | `outputs/maps/panel_before_after.png` |
| Candidate footprints | `outputs/vectors/candidate_footprints.geojson` |
| Evaluation metrics | `outputs/tables/evaluation_metrics.csv` |

---

## 📈 Evaluation Summary
- Candidate polygons extracted: **31**
- OSM building footprints: **1173**
- Intersection over Union (IoU): **0.0026**
- Overlap with OSM buildings: **~0.26%**

This low IoU is expected for a **pure edge-based baseline** and is discussed in detail
in the analysis section.

---

## ⚠️ Limitations
- Edge-based methods detect boundaries, not filled objects
- Sensitive to shadows, vegetation, and roof color variation
- Low recall in dense residential areas
- Not suitable as a production solution on its own

This workflow is intended as a **baseline and learning project**, not a final product.

---

## 🚀 Future Improvements
- Hole filling and better morphological reconstruction
- Shadow masking
- Tile-based evaluation instead of global IoU
- Deep learning segmentation (UNet, SAM, Esri DL models)
- Multi-temporal change detection

---

## 🧰 Tools & Libraries
- Python, Google Colab
- rasterio, geopandas, shapely, pyproj
- OpenCV (Canny, morphology)
- OSMnx
- matplotlib, folium

---


