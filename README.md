Tumor Immune Evasion in Lung Cancer
Identification of Exhausted CD8 T Cells using Single-Cell RNA-seq (Scanpy)
Project Overview

This project performs a single-cell RNA sequencing (scRNA-seq) analysis of lung cancer tumor samples to investigate T-cell exhaustion, a key mechanism of tumor immune evasion.

Using the Python Scanpy framework, I processed and analyzed a public lung cancer scRNA-seq dataset to identify immune cell populations and characterize a subset of CD8 T cells displaying an exhausted phenotype.

The project demonstrates a full bioinformatics workflow including preprocessing, clustering, cell-type annotation, gene-set scoring, and differential expression analysis.

Biological Background

Cytotoxic CD8 T cells normally recognize and destroy tumor cells.
However, in many cancers, continuous antigen exposure drives T cells into a dysfunctional state known as T-cell exhaustion.

Exhausted T cells:

lose cytotoxic activity

express inhibitory immune checkpoint receptors

allow tumors to escape immune destruction

These cells are the primary targets of modern immunotherapies such as PD-1/PD-L1 checkpoint inhibitors.

This project aims to computationally identify exhausted CD8 T cells within the tumor microenvironment.

Dataset

Public single-cell RNA-seq dataset:

GSE131907 — Lung Cancer Tumor Microenvironment scRNA-seq

The raw dataset is not stored in this repository due to GitHub size limitations.
To reproduce the analysis, download the dataset and place it in:
/data

Analysis Workflow

Loading AnnData object (.h5ad)

Quality control filtering

mitochondrial gene percentage

gene counts per cell

Library size normalization

Log-transformation

Highly variable gene (HVG) selection

PCA dimensionality reduction

Neighborhood graph construction

Leiden clustering

UMAP visualization

Cell type annotation

Exhaustion gene scoring

Identification of exhausted CD8 T cells

Differential gene expression (Wilcoxon test)

Cell Type Annotation

Major immune populations were identified using canonical marker genes:

Cell Type	Marker Genes
T cells	CD3D, CD3E
CD8 T cells	CD8A
NK cells	NKG7, GNLY
B cells	MS4A1
Myeloid/Monocytes	LST1, S100A8
T-Cell Exhaustion Analysis

An exhaustion score was calculated using known checkpoint and exhaustion markers:

PDCD1 (PD-1)

CTLA4

LAG3

TIGIT

HAVCR2 (TIM-3)

TOX

Cells in the top 25% of exhaustion scores were classified as:
Exhausted CD8 T cells

UMAP visualization shows a distinct CD8 T-cell subpopulation enriched for checkpoint receptor expression.

Differential Expression Results

Differential gene expression (Wilcoxon rank-sum test) between exhausted and non-exhausted CD8 T cells identified transcriptional differences associated with dysfunctional T-cell states.

Exhausted cells showed increased expression of immune checkpoint genes and transcriptional regulators of chronic stimulation.

Marker gene tables are provided in:
results/tables/

Key Findings

A distinct CD8 T-cell subpopulation with high checkpoint receptor expression was identified

These cells display a transcriptional profile consistent with T-cell exhaustion

Exhausted T cells localize to a specific region of the UMAP manifold

Differential expression analysis supports functional divergence from non-exhausted CD8 T cells

data/               raw input files (not tracked by git)
notebooks/          Jupyter notebooks
scripts/            helper scripts
results/figures/    UMAP plots and gene expression visualizations
results/tables/     differential expression marker tables

Technologies Used

Python

Scanpy

Anndata

NumPy

Pandas

Matplotlib

Single-cell RNA-seq analysis

Statistical testing (Wilcoxon rank-sum)

Skills Demonstrated

scRNA-seq preprocessing and QC

AnnData object manipulation

clustering and dimensionality reduction

gene signature scoring

differential expression analysis

biological interpretation of transcriptomic data

reproducible research workflows

Reproducibility

All package versions are documented in:
sessionInfo.txt

Author

Agata Gabara
Bioinformatics & Computational Biology
