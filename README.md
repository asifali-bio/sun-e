<p align="center">
  <img src="assets/sun_moji.svg" width="220">
</p>

# SUN Engine
**Single-Cell Visualization with Unreal Engine**

SUN Engine is a prototype pipeline for transforming large-scale single-cell RNA-seq data into interactive 3D visualizations using Unreal Engine. It aggregates biological features (Pfam domains or Gene Ontology terms) and renders them as vertical “cell towers” in 3D space.

---

## 🧬 Overview

SUN Engine bridges computational biology and real-time rendering:

- **Input:** scRNA-seq count matrices
- **Processing:** aggregation of gene expression into functional units (Pfam / GO)
- **Output:** 3D point cloud with:
  - X/Y → dimensional reduction (PCA or UMAP)
  - Z → indexed biological feature (domain / GO term)
  - Size → expression magnitude

The result is a spatial representation of cellular composition that can be explored interactively in Unreal Engine.

---

## 🚀 Features

- 🔬 Supports **Pfam domain aggregation**
- 🧠 Supports **Gene Ontology (GO) aggregation**
- 📊 Integrates with Seurat for clustering and embeddings
- 🧱 Generates “cell tower” structures in 3D
- ⚡ Designed for export into real-time engines (Unreal Engine)

---

## 📦 Pipeline

### 1. Data Preparation
- Load scRNA-seq data (e.g., 10x Genomics PBMC dataset)
- Create Seurat object
- Normalize and cluster cells (SCTransform + PCA/UMAP)

### 2. Feature Mapping
- Map proteins → genes using UniProt + Ensembl
- Build:
  - Pfam domain mappings
  - OR GO term mappings

### 3. Aggregation
- Sum gene expression per:
  - domain (Pfam)
  - or GO term

### 4. 3D Encoding
- X/Y → PCA or UMAP coordinates
- Z → numeric index of feature (alphabetically ordered)
- Point size → aggregated expression (magnitude)

### 5. Visualization
- Export geometry data for Unreal Engine integration (Arrow / Feather / Parquet)
- GPU rendering using Niagara particle system

---

*Banner emoji designed by OpenMoji.*