# Generated Figures

This directory contains the visualization outputs produced by the Scanpy single-cell RNA-seq analysis.

The figures illustrate cell populations in the lung tumor microenvironment and highlight exhausted CD8+ T cell signatures.

---

## UMAP Visualizations

### umap_celltypes.png
UMAP projection showing annotated immune cell populations (B cells, CD8 T cells, myeloid cells, NK cells, and others).

### umap_leiden_30k.png
Unsupervised Leiden clustering of all cells based on transcriptomic similarity.

---

## Marker Gene Expression

### tcell_markers.png
Expression of canonical T-cell markers (CD3D, CD8A, CD4, FOXP3) across the UMAP embedding, validating cell identity.

### checkpoint_markers.png
Expression of immune checkpoint and exhaustion genes:
PDCD1 (PD-1), LAG3, TIGIT, HAVCR2, and TOX.
High expression indicates exhausted T-cell states.

---

## Differential Expression

### volcano_Tcells_vs_tumor.png
Volcano plot showing genes differentially expressed between T cells and tumor epithelial cells.

Upregulated immune genes confirm cytotoxic T-cell activity, while epithelial markers identify tumor cells.

---

These visualizations support the presence of exhausted CD8+ T cells within the tumor microenvironment.
