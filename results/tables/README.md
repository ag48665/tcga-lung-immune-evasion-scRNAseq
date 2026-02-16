# Differential Expression and Marker Gene Tables

This directory contains all tabular outputs generated during the single-cell RNA-seq analysis.

The tables summarize gene expression differences between cell populations and identify transcriptional signatures associated with T-cell exhaustion.

---

## CD8+ T-cell Exhaustion Analysis

### CD8_exhausted_DE_all.csv
Complete differential expression results comparing exhausted CD8+ T cells vs non-exhausted CD8+ T cells using the Wilcoxon rank-sum test.

Columns include:
- gene name
- log fold change (logFC)
- p-value
- adjusted p-value (FDR)
- expression fraction in each group

### CD8_exhausted_DE_sig_up.csv
Subset of significantly upregulated genes in exhausted CD8+ T cells (adjusted p-value < 0.05).

These genes represent the transcriptional exhaustion signature.

### CD8_exhausted_markers.csv
Top marker genes specifically enriched in exhausted CD8+ T cells.

Key observed markers include:
PDCD1 (PD-1), LAG3, TIGIT, HAVCR2, and TOX.

---

## Cluster Marker Identification

### leiden_markers_wilcoxon.csv
Marker genes for each Leiden cluster identified using Scanpy’s `rank_genes_groups` function (Wilcoxon test).

This table was used for cell type annotation.

### leiden_markers_wilcoxon_hvg30k.csv
Marker genes calculated using highly variable genes only (HVG-filtered dataset).

---

## Interpretation

The differential expression analysis confirms the presence of an exhausted CD8+ T-cell population in the tumor microenvironment.  
Upregulated immune checkpoint genes indicate chronic antigen stimulation and impaired cytotoxic function.

These results are consistent with known tumor immune evasion mechanisms in lung cancer.
