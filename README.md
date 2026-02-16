# Tumor Immune Evasion in Lung Cancer

### Identification of Exhausted CD8⁺ T Cells using Single-Cell RNA-seq (Scanpy)

---

## Project Summary

This project performs an end-to-end single-cell RNA sequencing (scRNA-seq) analysis of lung cancer tumor samples to investigate **T-cell exhaustion**, a central mechanism of tumor immune evasion.

Using the Python **Scanpy** framework, I processed and analyzed a public lung cancer dataset to identify immune cell populations and characterize a subpopulation of **exhausted CD8⁺ T cells**.
The workflow includes preprocessing, clustering, cell-type annotation, gene-signature scoring, statistical testing, and biological interpretation.

The goal of the project is to computationally detect dysfunctional anti-tumor immune responses inside the tumor microenvironment.

---

## Biological Background

Cytotoxic CD8⁺ T cells normally recognize and eliminate tumor cells.
However, in many cancers, chronic antigen stimulation causes T cells to enter a dysfunctional state known as **T-cell exhaustion**.

Exhausted T cells:

* lose cytotoxic activity
* express inhibitory immune checkpoint receptors
* fail to eliminate tumor cells

These cells are the primary targets of modern immunotherapies such as **PD-1/PD-L1 checkpoint blockade**.

This project aims to identify exhausted CD8 T cells directly from transcriptomic data.

---

## Dataset

Public single-cell RNA-seq dataset:

**GSE131907 — Lung Cancer Tumor Microenvironment scRNA-seq**

The raw dataset is not included in the repository due to GitHub size limits.
To reproduce the analysis, download the dataset from GEO and place it in:

```
/data
```

---

## Analysis Workflow

1. Loading AnnData object (.h5ad)
2. Quality control filtering

   * mitochondrial gene percentage
   * gene counts per cell
3. Library size normalization
4. Log-transformation
5. Highly variable gene (HVG) selection
6. PCA dimensionality reduction
7. Nearest-neighbor graph construction
8. Leiden clustering
9. UMAP visualization
10. Cell type annotation
11. Exhaustion gene scoring
12. Identification of exhausted CD8 T cells
13. Differential gene expression (Wilcoxon test)

---

## Cell Type Annotation

Major immune populations were annotated using canonical markers:

| Cell Type         | Marker Genes |
| ----------------- | ------------ |
| T cells           | CD3D, CD3E   |
| CD8 T cells       | CD8A         |
| NK cells          | NKG7, GNLY   |
| B cells           | MS4A1        |
| Myeloid/Monocytes | LST1, S100A8 |

---

## T-Cell Exhaustion Analysis

An exhaustion score was calculated using immune checkpoint and exhaustion markers:

* PDCD1 (PD-1)
* CTLA4
* LAG3
* TIGIT
* HAVCR2 (TIM-3)
* TOX

Cells in the **top 25% of exhaustion score** were classified as:

> **Exhausted CD8 T cells**

UMAP visualization reveals a distinct subpopulation enriched for checkpoint receptor expression.

---

## Differential Expression

Differential gene expression (Wilcoxon rank-sum test) was performed between:

**Exhausted CD8 T cells vs Non-exhausted CD8 T cells**

Results identified transcriptional differences associated with chronic stimulation and immune dysfunction.

Marker tables are available in:

```
results/tables/
```

---

## Key Findings

* A distinct CD8 T-cell subpopulation with high checkpoint receptor expression was detected
* These cells display a transcriptional profile consistent with T-cell exhaustion
* Exhausted cells occupy a specific region of the UMAP manifold
* Differential expression confirms functional divergence from non-exhausted CD8 T cells

---

## Repository Structure

```
data/               raw input files (not tracked by git)
notebooks/          analysis notebooks
scripts/            helper scripts
results/figures/    UMAP and gene expression plots
results/tables/     differential expression tables
```

---

## Technologies

* Python
* Scanpy
* AnnData
* NumPy
* Pandas
* Matplotlib
* Statistical testing (Wilcoxon rank-sum)

---

## Skills Demonstrated

* single-cell RNA-seq preprocessing and QC
* clustering and dimensionality reduction
* gene signature scoring
* differential gene expression analysis
* biological interpretation of transcriptomic data
* reproducible computational research workflows

---

## Reproducibility

Package versions and environment information are documented in:

```
sessionInfo.txt
```

---

## Author
**Agata Gabara**


