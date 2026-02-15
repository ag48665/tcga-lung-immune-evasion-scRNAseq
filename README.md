# Tumor Immune Evasion in Lung Cancer (scRNA-seq Analysis)

## Project Overview
This project investigates tumor immune evasion mechanisms in lung cancer using single-cell RNA sequencing (scRNA-seq) data.  
The analysis focuses on identifying transcriptional differences between cytotoxic T cells and tumor epithelial cells.

The study was performed using the Seurat package in R.

---

## Biological Question
Tumors often escape immune destruction by suppressing cytotoxic T-cell activity.  
This project explores:

- whether tumor epithelial cells show immune evasion signatures
- whether cytotoxic T cells show exhaustion markers
- which genes distinguish immune cells from tumor cells

---

## Dataset
Public single-cell RNA-seq dataset from GEO:

**GSE131907 — Lung Cancer scRNA-seq**

The raw dataset is not included in the repository due to GitHub file size limits.  
It can be downloaded from GEO and placed in the `/data` folder.

---

## Analysis Workflow

1. Data loading and preprocessing
2. Quality control filtering
3. Normalization and scaling
4. PCA and UMAP dimensionality reduction
5. Cell type identification
6. Marker gene validation
7. Differential gene expression analysis
8. Visualization (UMAP & volcano plot)

---

## Key Markers Investigated

### T cell identity
CD3D, CD3E, CD8A

### Cytotoxic activity
GZMB, GNLY, PRF1

### Immune exhaustion
PDCD1 (PD-1), LAG3, TIGIT, HAVCR2, ENTPD1

### Tumor epithelial markers
EPCAM, HLA-A

---

## Main Results
- Cytotoxic T cells express high levels of **GZMB** and **GNLY**
- Tumor epithelial cells strongly express **EPCAM**
- Immune exhaustion signatures are detectable in subsets of T cells
- Differential expression analysis identifies immune-related genes distinguishing tumor and immune populations
---

## Tools and Technologies
- R (v4.5)
- Seurat
- ggplot2
- Single-cell RNA-seq analysis
- Differential gene expression
- Data visualization

---

## Reproducibility
The R session information is provided in `sessionInfo.txt`.

---

## Author
Agata Gabara
