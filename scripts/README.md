# Preprocessing and Data Preparation Scripts

This directory contains helper Python scripts used to prepare raw single-cell RNA-seq data for downstream analysis in Scanpy.

The purpose of these scripts is to convert raw expression matrices into a standardized AnnData (`.h5ad`) object that can be analyzed in the Jupyter notebooks.

The notebooks perform clustering, trajectory inference, and exhaustion analysis, while the scripts handle data ingestion and formatting.

---

## Analysis Workflow

The complete workflow of the project is:

1. Download raw expression matrices
2. Convert matrices to AnnData format
3. Load dataset in Scanpy
4. Perform quality control and filtering
5. Normalize and identify highly variable genes
6. Dimensionality reduction (PCA, UMAP)
7. Clustering (Leiden)
8. CD8 T-cell subsetting
9. Pseudotime trajectory reconstruction
10. Differential expression and exhaustion analysis

This folder covers **Step 2 (data conversion)**.

---

## Available Script

### `convert_to_h5ad.py`

Converts gene expression matrices into an AnnData (`.h5ad`) object required by Scanpy.

### What the script does

* reads raw expression matrix
* loads gene names and cell barcodes
* constructs AnnData object
* stores metadata
* saves dataset as `.h5ad`

The generated `.h5ad` file is then used as the input for the analysis notebooks located in the `notebooks/` directory.

---

## How to Run

Example usage:

```bash
python scripts/convert_to_h5ad.py \
    --matrix data/raw/matrix.mtx \
    --genes data/raw/genes.tsv \
    --barcodes data/raw/barcodes.tsv \
    --output data/processed/lusc_scRNAseq.h5ad
```

---

## Dependencies

The scripts require the same environment used for the notebooks.

Create the environment using:

```bash
conda env create -f environment.yml
conda activate scrna-lusc
```

Required Python packages include:

* scanpy
* anndata
* pandas
* numpy
* scipy

---

## Reproducibility

By combining:

* raw data (data/)
* preprocessing scripts (scripts/)
* analysis notebooks (notebooks/)
* results (results/)

the full analysis can be reproduced from raw sequencing matrix to biological interpretation.
