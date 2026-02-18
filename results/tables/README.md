# Differential Expression and Marker Gene Tables

This directory contains all tabular outputs generated during the single-cell RNA-seq analysis of the TCGA Lung Squamous Cell Carcinoma (LUSC) tumor microenvironment.

These tables provide the statistical evidence supporting the CD8 T-cell trajectory and exhaustion analysis presented in the figures.

---

## 1. Global Cell Clustering Markers

### `leiden_markers_wilcoxon.csv`

Marker genes identified for each Leiden cluster using the Wilcoxon rank-sum test.

Each row contains:

* gene name
* log fold change
* p-value
* adjusted p-value
* cluster identity

These markers were used to annotate major immune populations and to identify the T-cell compartment.

### `leiden_markers_wilcoxon_hvg30k.csv`

Marker detection performed using the highly variable gene (HVG) set after filtering and normalization.

This table improves robustness of cell-type annotation and reduces noise from low-expressed genes.

---

## 2. CD8 T-Cell Exhaustion Analysis

### `CD8_exhausted_marker_genes.csv`

List of genes associated with exhausted CD8 T cells derived from differential expression and literature-supported checkpoint signatures.

Includes key inhibitory receptors such as:

* **PDCD1 (PD-1)**
* **LAG3**
* **HAVCR2 (TIM-3)**
* **TOX**

These genes define the exhausted T-cell phenotype.

### `CD8_exhausted_markers.csv`

Cluster-specific marker genes distinguishing exhausted CD8 T cells from other CD8 T-cell states.

Used to biologically interpret the CD8 subclusters identified in UMAP and pseudotime analyses.

---

## 3. Differential Expression Testing

### `CD8_exhausted_DEG.csv`

Differentially expressed genes between exhausted and non-exhausted CD8 T cells.

Provides:

* log fold change
* p-value
* adjusted p-value (FDR)

These genes characterize functional differences between early effector and dysfunctional T-cell states.

### `CD8_exhausted_DE_all.csv`

Complete differential expression results prior to statistical filtering.

Contains all tested genes and is useful for reproducibility and downstream pathway enrichment analysis.

### `CD8_exhausted_DE_sig_up.csv`

Subset of significantly upregulated genes in exhausted CD8 T cells (adjusted p-value threshold applied).

These genes represent transcriptional programs associated with T-cell dysfunction and chronic antigen exposure.

### `CD8_exhausted10_DE_all.csv`

Expanded differential expression analysis using a stricter exhaustion cell definition (top exhaustion-score cells only).

Used to validate robustness of the exhausted T-cell signature.

---

## Biological Interpretation

Together, these tables demonstrate that CD8 T cells in the lung tumor microenvironment undergo transcriptional reprogramming consistent with progressive exhaustion.

Key findings supported by the data:

1. CD8 T cells express cytotoxic effector genes in early states
2. Inhibitory checkpoint receptors increase in later states
3. Exhausted cells show a distinct transcriptional program
4. The exhausted phenotype is statistically significant and reproducible

These tables provide the quantitative foundation for the trajectory and pseudotime analyses shown in the figures directory.
