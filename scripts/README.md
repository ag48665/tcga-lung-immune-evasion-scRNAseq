# Helper Scripts

This directory contains supporting Python scripts used during preprocessing and data preparation for the Scanpy single-cell RNA-seq analysis.

The scripts were used to convert raw data formats and prepare the dataset for downstream analysis in the Jupyter notebooks.

---

## Available Scripts

### convert_to_h5ad.py
Converts gene expression matrices into AnnData (.h5ad) format required by Scanpy.

Functionality:
- reads raw expression matrix
- creates AnnData object
- assigns gene and cell barcodes
- saves dataset in .h5ad format

This step allows compatibility between raw sequencing output and the Scanpy analysis pipeline.

---

### convert_to_h5ad_mtx.py
Processes matrix files in MTX format (Matrix Market format) commonly provided by GEO datasets.

The script:
- loads matrix.mtx
- loads genes.tsv / features.tsv
- loads barcodes.tsv
- builds a complete AnnData object
- exports a ready-to-analyze dataset

---

## Role in the Pipeline

The helper scripts ensure that:
1. public raw data can be imported reproducibly
2. the project can be rerun from scratch
3. the workflow is not dependent on manual file manipulation

These scripts make the analysis fully reproducible and portable across environments.

