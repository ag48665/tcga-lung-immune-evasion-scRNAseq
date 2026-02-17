# Immune Evasion in Lung Squamous Cell Carcinoma

## Single-Cell Transcriptomic Evidence for Exhausted CD8⁺ T Cells in the TCGA Tumor Microenvironment

---

## Abstract

Lung squamous cell carcinoma (LUSC) frequently exhibits resistance to immune-mediated tumor clearance despite the presence of tumor-infiltrating lymphocytes. A major proposed mechanism is T-cell exhaustion, a dysfunctional differentiation state caused by chronic antigen stimulation within the tumor microenvironment.

In this project, I analyzed publicly available single-cell RNA sequencing data from human lung tumors to determine whether transcriptionally identifiable exhausted CD8⁺ T cells are present within the tumor immune compartment. Using an unsupervised Scanpy pipeline, I identified immune cell populations and detected a discrete CD8⁺ T-cell subset enriched for immune checkpoint receptors (PDCD1, LAG3, TIGIT, HAVCR2, CTLA4, TOX). Differential expression analysis demonstrated suppression of cytotoxic programs and enrichment of inhibitory signaling pathways.

These findings support a model in which lung tumors evade immune destruction not by excluding T cells but by functionally disabling them. The analysis illustrates how single-cell transcriptomics can be used to characterize anti-tumor immune dysfunction and to computationally identify cell populations relevant to checkpoint inhibitor therapies.

---
## Repository Structure

- `data/` – input data (excluded from git)
- `notebooks/` – analysis notebooks
- `scripts/` – processing and scoring scripts
- `results/figures/` – UMAP and expression plots
- `results/tables/` – differential expression results

## Research Hypothesis

Tumor-infiltrating CD8⁺ T cells in lung squamous cell carcinoma are present but transcriptionally reprogrammed into an exhausted state that prevents effective tumor killing.

---


## Biological Background

The immune system is capable of recognizing malignant cells through antigen presentation. Cytotoxic CD8⁺ T lymphocytes normally eliminate tumor cells via perforin and granzyme-mediated killing.

However, chronic antigen exposure in tumors induces **T-cell exhaustion**, characterized by:

* sustained checkpoint receptor expression
* reduced cytokine production
* impaired cytotoxicity
* inability to clear cancer cells

Checkpoint inhibitor therapies (anti-PD-1/PD-L1) partially restore T-cell function, but only a subset of patients respond. One explanation is that tumors contain terminally exhausted T cells that cannot be fully reactivated.

This project computationally investigates whether exhausted CD8⁺ T cells can be detected directly from tumor transcriptomic data.

---

## Dataset

Human lung tumor microenvironment scRNA-seq dataset
**GEO accession: GSE131907**

The dataset contains tumor-infiltrating immune cells isolated from lung cancer patients.

To reproduce:
Place downloaded files in:

`/data`

---

## Methods

### Quality Control

Cells were filtered based on:

* mitochondrial transcript percentage
* total UMI counts
* number of detected genes

Low-quality and dying cells were removed prior to analysis.

### Normalization and Feature Selection

* library size normalization
* log transformation
* highly variable gene selection

### Dimensionality Reduction and Clustering

* PCA
* nearest neighbor graph
* Leiden clustering
* UMAP visualization

Cell populations were identified using unsupervised transcriptomic similarity rather than predefined labels.

---

## Cell Type Identification

Clusters were annotated using canonical immune markers:

| Population    | Marker Genes |
| ------------- | ------------ |
| T cells       | CD3D, CD3E   |
| CD8⁺ T cells  | CD8A         |
| NK cells      | NKG7, GNLY   |
| B cells       | MS4A1        |
| Myeloid cells | LST1, S100A8 |

The tumor immune microenvironment consisted of multiple lymphoid and myeloid populations.

---

## Detection of Exhausted CD8⁺ T Cells

An exhaustion gene-signature score was calculated using established checkpoint and exhaustion markers:

PDCD1, CTLA4, LAG3, TIGIT, HAVCR2, TOX

CD8⁺ T cells within the top quartile of the exhaustion score were classified as **exhausted T cells**.

UMAP embedding revealed a distinct transcriptional cluster enriched for inhibitory receptor expression, indicating a stable immune cell state rather than temporary activation.

---

## Differential Expression Results

I compared exhausted and non-exhausted CD8⁺ T cells using the Wilcoxon rank-sum test.

The exhausted population showed:

* increased immune checkpoint expression
* decreased cytotoxic gene expression
* altered activation signaling pathways

Marker tables are located in:
`results/tables/`

---

## Biological Interpretation

The data indicate that lung tumors contain T cells that have infiltrated the tumor but are transcriptionally suppressed. Elevated TOX and inhibitory receptor expression suggests chronic antigen exposure leading to functional impairment.

This supports a mechanism of immune evasion based on **immune suppression rather than immune absence**.

Implication:
Tumors may progress even when recognized by the immune system because effector cells are present but inactive.

This aligns with clinical observations where tumors rich in lymphocytes still fail to regress without checkpoint inhibitor therapy.

---

## Limitations

* single dataset analysis
* no direct functional validation
* lack of patient treatment outcome data
* marker-based exhaustion classification

---

## Reproducibility

```bash
conda env create -f environment.yml
conda activate lusc_scRNA
jupyter lab


---

## Repository Structure

data/ – input data (excluded from git)
notebooks/ – analysis notebooks
scripts/ – processing and scoring scripts
results/figures/ – UMAP and gene expression plots
results/tables/ – differential expression results

---

## Skills Demonstrated

* single-cell RNA-seq analysis (Scanpy)
* unsupervised clustering
* immune cell annotation
* gene signature scoring
* differential expression analysis
* hypothesis-driven biological interpretation
* reproducible research workflow

---

## Author

Agata Gabara



