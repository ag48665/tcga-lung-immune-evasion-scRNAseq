# Generated Figures

This directory contains all visualization outputs produced during the single-cell RNA-seq analysis of the lung tumor microenvironment.

The figures document identification of CD8⁺ T cells, validation of their phenotype, and evidence of progressive T-cell exhaustion.

---

## Global Cell Structure

### `umap_celltypes.png`

UMAP embedding of all cells after preprocessing and clustering.

Cells are annotated into major immune populations, including:

* CD8⁺ T cells
* CD4⁺ T cells
* B cells
* NK cells
* myeloid cells

This plot establishes the cellular composition of the tumor microenvironment and identifies the T-cell compartment used for downstream analysis.

---

### `umap_leiden_30k.png`

Unsupervised Leiden clustering of all cells.

Each color represents a transcriptionally distinct cluster inferred purely from gene expression similarity.
Clusters containing T-cell markers were selected for detailed CD8 T-cell trajectory analysis.

---

## T-cell Identity Validation

### `tcell_markers.png`

UMAP showing expression of canonical T-cell lineage genes:

* **CD3D**
* **TRAC**
* **CD8A**
* **CD4**
* **FOXP3**

This confirms that selected clusters correspond to T-cell populations and allows separation of CD8⁺ cytotoxic T cells from other lymphocytes.

---

## Immune Checkpoint and Exhaustion Signature

### `checkpoint_markers.png`

UMAP visualization of inhibitory receptor and exhaustion-associated genes:

* **PDCD1 (PD-1)**
* **LAG3**
* **TIGIT**
* **HAVCR2 (TIM-3)**
* **TOX**

High co-expression of these genes identifies exhausted CD8⁺ T cells.
The spatial concentration of these markers indicates a dysfunctional T-cell population within the tumor microenvironment.

---

## Differential Gene Expression

### `volcano_plot.png`

Volcano plot of differential expression analysis.

Shows genes significantly up- or down-regulated between immune cell populations.
Immune activation genes (e.g., cytotoxic effectors) are enriched in T cells, while epithelial/tumor markers are enriched in tumor cells.

---

## Biological Interpretation

Together, these figures demonstrate:

1. Presence of tumor-infiltrating CD8⁺ T cells
2. Separation of functional and dysfunctional T-cell states
3. Upregulation of inhibitory checkpoint receptors
4. Evidence of progressive T-cell exhaustion in lung cancer

These observations motivated the downstream pseudotime trajectory analysis performed in the trajectory notebooks.
