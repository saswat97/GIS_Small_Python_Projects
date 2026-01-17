## 📊 Project Analysis & Interpretation

This section presents a detailed evaluation of the **edge-based building footprint extraction workflow** and interprets the results using spatial accuracy metrics and visual inspection.

The goal of this analysis is **not to achieve production-grade accuracy**, but to:
- establish a classical computer vision baseline,
- understand its strengths and weaknesses,
- and create a reference point for more advanced GeoAI-based approaches.

---

### 🔍 Evaluation Summary

| Metric | Value |
|------|------|
| Candidate polygons extracted | 31 |
| OSM building footprints | 1,173 |
| Intersection area | 874.32 m² |
| Union area | 340,380.47 m² |
| Intersection over Union (IoU) | 0.0026 |
| Overlap with OSM buildings | ~0.26% |

---

### 🧠 Understanding the IoU Score

**Intersection over Union (IoU)** measures how much the extracted building footprint area overlaps with reference building footprints relative to their combined area.

An IoU value of approximately **0.0026 (0.26%)** indicates that only a **very small fraction** of the reference building area overlaps with the extracted candidate footprints.

This outcome is **expected** for a workflow based solely on edge detection and morphological reconstruction.

---

### 🗺️ Visual Interpretation vs Quantitative Metrics

Visual inspection of the footprint overlay reveals that:

- The study area contains a **dense suburban residential layout** with hundreds of buildings.
- OpenStreetMap provides **highly complete building coverage** in this region.
- The extracted candidate footprints represent only:
  - buildings with strong, continuous roof edges,
  - minimal vegetation and shadow interference,
  - simple and isolated roof geometries.

While these extracted footprints may appear reasonable in isolation, they represent a **small subset** of the total building stock, resulting in a low global IoU score.

---

### ⚙️ Why the IoU Score Is Low

Several technical factors contribute to the low IoU value:

1. **Edge-Based Detection Limitations**  
   Canny edge detection identifies boundaries, not filled building interiors.  
   Any break in roof edges caused by shadows, trees, or roof color variation prevents the formation of closed building shapes.

2. **Morphological Reconstruction Challenges**  
   Morphological closing and dilation attempt to reconnect edges but are sensitive to kernel size and iteration count.  
   In dense residential areas, this often results in fragmented or merged structures.

3. **Aggressive Filtering Reduces Recall**  
   Pixel-area and polygon-area filters intentionally remove noise, but also eliminate many small residential buildings, significantly reducing the number of detected footprints.

4. **Global IoU Penalizes Sparse Predictions**  
   IoU was computed using dissolved geometries.  
   When reference data is dense and predictions are sparse, even visually valid detections contribute minimally to the overall overlap.

---

### ⚠️ Methodological Limitations

This baseline approach has several inherent limitations:

- Roads, pavements, and parking areas generate strong edges similar to buildings.
- Vegetation and shadows disrupt roof boundary continuity.
- Complex or connected roof structures are difficult to separate.
- Results are highly sensitive to threshold and kernel parameter selection.

For these reasons, this method is **not suitable as a standalone production solution**.

---

### 🧩 Value of This Baseline Workflow

Despite its limitations, this workflow provides significant value:

- Demonstrates a complete **raster-to-vector GIS pipeline**
- Requires **no training data**
- Is fully explainable and reproducible
- Serves as a **candidate generation or preprocessing step** for machine learning models
- Establishes a transparent benchmark for evaluating GeoAI improvements

---

### 🚀 Future Improvements

Potential enhancements to this workflow include:

- Stronger morphological closing and hole-filling strategies
- Shadow masking prior to edge detection
- Tile-based or per-building evaluation instead of global IoU
- Integration of deep learning segmentation models (e.g., UNet, SAM)
- Multi-temporal analysis for building change detection

---

### ✅ Key Takeaway

The low IoU score is a **correct and meaningful result**, reflecting the inherent limitations of classical edge-based building extraction in dense urban environments.

This project successfully establishes a **baseline GIS + computer vision workflow**, providing a strong foundation for more advanced GeoAI techniques and future model-based improvements.
