# CD8 T-Cell Exhaustion Trajectory in Lung Squamous Cell Carcinoma (scRNA-seq)

## Generated Figures

This directory contains the key visualizations produced during single-cell RNA-seq analysis of the lung tumor microenvironment (TCGA-LUSC).
The goal of the analysis was to identify tumor-infiltrating CD8⁺ T cells and reconstruct their functional state transition inside the tumor.

The figures collectively demonstrate that CD8 T cells follow a differentiation trajectory from **cytotoxic effector cells → transitional cells → terminally exhausted T cells**.

---

## 1. Tumor Immune Landscape

### `umap_leiden_30k.png`

UMAP projection of all single cells after preprocessing, normalization, and Leiden clustering.

Each point represents one cell and each color represents a transcriptionally distinct cluster inferred from gene-expression similarity.
This plot establishes the global cellular composition of the tumor microenvironment and identifies lymphocyte populations for downstream analysis.

---

## 2. Identification of T Cells

### `T_cell_Marker_Expression_UMAP.png`

Feature plots of canonical T-cell lineage genes:

* **CD3D** – pan-T-cell marker
* **CD8A / CD8B** – cytotoxic CD8 T cells
* **NKG7 / GZMB** – cytotoxic effector function

These markers confirm the presence of tumor-infiltrating cytotoxic T lymphocytes and allow selection of the CD8 T-cell compartment for focused analysis.

---

## 3. CD8 T-Cell Heterogeneity

### `CD8_T_cell_Subcluster_UMAP.png`

Reclustering of the CD8 T-cell subset reveals three transcriptionally distinct populations.
The separation suggests functional specialization within tumor-infiltrating CD8 T cells rather than a single homogeneous population.

---

## 4. Exhaustion Phenotype

### `Exhaustion_Score_Across_CD8_T_Cells.png`

Cells were scored using an exhaustion gene signature.
Higher scores localize to specific CD8 T-cell subpopulations, indicating functional impairment in a subset of tumor-infiltrating lymphocytes.

### `Cytotoxic_and_Exhaustion_Marker_Expression.png`

Expression of exhaustion-associated immune checkpoint genes:

* **PDCD1 (PD-1)**
* **LAG3**
* **HAVCR2 (TIM-3)**
* **TOX**

Their co-expression identifies terminally dysfunctional T cells within the tumor.

---

## 5. Pseudotime Trajectory Reconstruction

### `CD8_T_cell_Pseudotime_Trajectory.png`

Diffusion pseudotime (DPT) analysis orders CD8 T cells along a developmental trajectory.
Cells at early pseudotime represent effector-like states, while late pseudotime corresponds to dysfunctional/exhausted states.

### `Exhaustion_vs_Pseudotime_in_CD8_T_Cells.png`

Exhaustion score increases with pseudotime, demonstrating that T-cell dysfunction is progressively acquired rather than representing a separate lineage.

---

## 6. Gene Regulation Along the Trajectory

### `Gene_Expression_Dynamics_Along_Pseudotime.png`

Binned pseudotime analysis shows dynamic gene regulation:

* Early cells: cytotoxic genes (**GZMB**, **NKG7**)
* Late cells: checkpoint and exhaustion genes (**PDCD1**, **TOX**, **HAVCR2**, **LAG3**)

### `Cluster_Marker_Gen_Identification.png`

Differential expression identifies cluster-specific transcriptional programs corresponding to functional CD8 T-cell states.

---

## Biological Conclusion

This analysis reconstructs a continuous differentiation process of tumor-infiltrating CD8 T cells:

**Cytotoxic effector → transitional → terminally exhausted**

Key observations:

1. CD8 T cells infiltrate the lung tumor microenvironment
2. Multiple functional states exist within the CD8 population
3. Immune checkpoint genes accumulate over pseudotime
4. Exhaustion is a progressive developmental process

These findings are consistent with immune evasion in cancer, where chronic antigen exposure drives T-cell dysfunction and limits anti-tumor immunity.
