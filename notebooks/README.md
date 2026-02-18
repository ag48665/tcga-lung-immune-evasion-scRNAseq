# CD8 T Cell Trajectory and Exhaustion Analysis

This directory contains notebooks performing trajectory inference of CD8⁺ T cells in the lung tumor microenvironment using single-cell RNA-seq data.

The goal of this analysis is to reconstruct the **developmental progression from functional cytotoxic T cells to terminally exhausted T cells** and identify molecular programs associated with immune evasion in lung cancer.

---

## Biological Background

Tumor-infiltrating CD8⁺ T cells initially exhibit cytotoxic activity and anti-tumor function.
However, chronic antigen exposure in cancer leads to **T cell exhaustion**, a dysfunctional state characterized by:

* reduced effector function
* impaired proliferation
* sustained inhibitory receptor expression

Key exhaustion markers analyzed:

* **PDCD1 (PD-1)**
* **LAG3**
* **HAVCR2 (TIM-3)**
* **TOX**

Cytotoxic markers:

* **GZMB**
* **NKG7**
* **CD8A / CD8B**

---

## Main Notebook

### `02_CD8_Tcell_Trajectory_Analysis.ipynb`

Identifies and validates CD8⁺ T cell populations.

Performs:

* T cell marker validation (CD3D, TRAC)
* CD8⁺ cell identification
* visualization of cytotoxic vs exhausted phenotypes
* cluster annotation

---

### `cd8_tcell_exhaustion_pseudotime.ipynb`

Core trajectory analysis.

This notebook reconstructs T cell differentiation using diffusion pseudotime (DPT) implemented in **Scanpy**.

Analysis steps:

1. Selection of CD8⁺ T cells
2. Normalization and HVG selection
3. PCA and neighborhood graph construction
4. Diffusion maps
5. Root cell identification (early T cell state)
6. Pseudotime inference
7. Visualization of gene expression along trajectory

---

## Key Findings

* CD8⁺ T cells do not form discrete states but a **continuous differentiation trajectory**
* Cytotoxic genes are highest in early pseudotime
* Exhaustion markers increase toward late pseudotime
* TOX and PDCD1 expression track terminal exhaustion

This supports a progressive transition from effector T cells to terminally exhausted T cells in lung cancer.

---

## Requirements

Python ≥ 3.10

Required packages:

* scanpy
* anndata
* numpy
* pandas
* scipy
* matplotlib
* seaborn

Install:

```
pip install scanpy anndata pandas numpy scipy matplotlib seaborn
```

---

## Output

Generated outputs include:

* UMAP projections of CD8⁺ T cells
* marker gene expression maps
* pseudotime trajectory plots
* exhaustion score vs pseudotime analysis

Figures are saved in:

```
/figures
```

Processed AnnData object:

```
cd8_pseudotime_lusc.h5ad
```
