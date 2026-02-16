# Analysis Notebooks (Scanpy Workflow)

This directory contains the Jupyter notebooks used to perform the single-cell RNA-seq analysis of lung cancer samples.

The analysis identifies exhausted CD8+ T cells and investigates immune evasion signatures in the tumor microenvironment.

---

## Notebook Order

Run the notebooks in the following order:

### 1. 01_CD8_Tcell_Exhaustion_Analysis.ipynb
Main analysis notebook.  
Performs:

- data loading (GSE131907)
- quality control filtering
- normalization and log transformation
- highly variable gene selection
- PCA and UMAP dimensionality reduction
- Leiden clustering
- cell type annotation
- CD8 T cell extraction
- exhaustion score calculation
- differential gene expression analysis

This notebook generates the figures and tables stored in the `/results` directory.

---

## Requirements

Python 3.10+

Required packages:

- scanpy
- anndata
- pandas
- numpy
- matplotlib
- seaborn
- scipy

You can install dependencies using:
pip install scanpy anndata pandas numpy matplotlib seaborn scipy


---

## Output

The notebooks produce:

- UMAP visualizations
- marker gene expression plots
- exhaustion score analysis
- differential expression tables

All outputs are saved in the `results/` directory.

