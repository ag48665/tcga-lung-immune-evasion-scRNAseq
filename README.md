# Immune Evasion in Lung Squamous Cell Carcinoma

## Single-cell RNA-seq reconstruction of CD8⁺ T-cell exhaustion

---

## Biological Question

Cytotoxic CD8⁺ T cells infiltrate many tumors, yet cancers frequently survive.
Why?

One major hypothesis is **T-cell exhaustion** — a dysfunctional differentiation state caused by chronic antigen stimulation within the tumor microenvironment.

This project investigates whether tumor-infiltrating CD8⁺ T cells in human lung squamous cell carcinoma undergo a progressive transition into an exhausted state.

---

## Key Result

Using single-cell RNA-seq trajectory analysis, I show:

**Tumor CD8 T cells are not absent — they are progressively disabled.**

They follow a continuous differentiation path:

**Cytotoxic effector → transitional → terminally exhausted T cell**

Exhaustion markers increase along the trajectory, demonstrating functional inactivation rather than immune exclusion.

---
## Potential Clinical Relevance

The analysis suggests that tumor-infiltrating CD8⁺ T cells in LUSC are present but progressively acquire exhaustion-associated transcriptional programs.

Potential implications include:

- understanding response to immune checkpoint inhibitors
- identification of exhaustion-associated biomarkers
- characterization of immune dysfunction within tumors
- support for future immunotherapy research

This project is intended for research and educational purposes only and is not designed for clinical decision-making.

---
## Main Findings

### CD8 T cells remain present within tumors

The analysis suggests that immune evasion occurs through functional suppression rather than complete immune exclusion.

### Exhaustion increases continuously along pseudotime

Checkpoint receptor expression progressively increases during differentiation.

### Cytotoxic programs are replaced by exhaustion-associated states

Late-stage cells show elevated PDCD1, TOX, LAG3, and HAVCR2 expression.

### Tumor immune dysfunction can be reconstructed at single-cell resolution

Trajectory analysis reveals a continuous transition from effector to terminally exhausted T-cell states.

---

## Overview of Analysis

### Tumor Immune Landscape

![Immune UMAP](results/figures/umap_leiden_30k.png)

All cells were clustered using Leiden clustering, revealing multiple immune populations including T cells, NK cells, B cells and myeloid cells.

---

### Identification of CD8 T Cells

![T cell markers](results/figures/T_cell_Marker_Expression_UMAP.png)

Canonical markers (CD3D, CD8A, CD8B, NKG7, GZMB) were used to identify cytotoxic T lymphocytes.


### Exhaustion Phenotype

![Exhaustion score](results/figures/Exhaustion_Score_Across_CD8_T_Cells.png)

An exhaustion gene signature (PDCD1, LAG3, HAVCR2, TOX) identifies a dysfunctional subset of tumor-infiltrating T cells.

---

### Differentiation Trajectory (Pseudotime)

![Pseudotime](results/figures/CD8_T_cell_Pseudotime_Trajectory.png)

Diffusion pseudotime reconstructs T-cell differentiation within the tumor.

---

### Functional Inactivation Along Trajectory

![Exhaustion vs pseudotime](results/figures/Exhaustion_vs_Pseudotime_in_CD8_T_Cells.png)

Exhaustion increases with pseudotime, indicating progressive acquisition of dysfunction.

---

### Gene Programs Driving Exhaustion

![Gene dynamics](results/figures/Gene_Expression_Dynamics_Along_Pseudotime.png)

Early cells express cytotoxic genes (GZMB, NKG7), while late cells upregulate checkpoint and regulatory genes (PDCD1, TOX, HAVCR2, LAG3).

---
## Project Highlights

✔ Single-cell RNA-seq analysis

✔ CD8 T-cell exhaustion modeling

✔ Diffusion pseudotime trajectory inference

✔ Immune evasion characterization

✔ Exhaustion signature scoring

✔ Differential expression analysis

✔ Tumor microenvironment profiling

✔ Reproducible Scanpy workflow

---

## Dataset

**GEO: GSE131907 — Human Lung Tumor Microenvironment scRNA-seq**

The repository excludes raw data due to size limitations.

To reproduce:

```
Place downloaded dataset at:
data/lusc.h5ad
```

---

## Methods

**Software:** Python, Scanpy, AnnData
**Analysis steps:**

1. Quality control and filtering
2. Normalization and highly variable gene detection
3. PCA and UMAP embedding
4. Leiden clustering
5. CD8 T-cell subsetting
6. Exhaustion signature scoring
7. Diffusion pseudotime trajectory inference
8. Differential expression analysis

---

## Repository Structure

```text
tcga-lung-immune-evasion-scRNAseq/
│
├── data/
│
├── notebooks/
│
├── scripts/
│
├── results/
│   ├── figures/
│   └── tables/
│
├── environment.yml
│
└── README.md
```

---

## Reproducibility

```
conda env create -f environment.yml
conda activate lusc_scRNA
jupyter lab
```

---

## Biological Interpretation

The analysis supports a model of **immune evasion via functional T-cell inactivation**:

* T cells infiltrate the tumor
* chronic antigen exposure occurs
* inhibitory checkpoint receptors accumulate
* cytotoxic function is suppressed

This provides a computational explanation for the effectiveness of immune checkpoint inhibitor therapy in lung cancer.

---

## Skills Demonstrated

* single-cell RNA-seq analysis (Scanpy)
* cell type annotation
* gene signature scoring
* trajectory inference
* differential expression
* biological interpretation
* reproducible research workflows

---
## Author

**Agata Gabara**

Incoming MSc Bioinformatics Student

Research Interests:

- Cancer Genomics
- Single-Cell Transcriptomics
- Tumor Immunology
- Computational Oncology
- Multi-Omics Integration

GitHub: https://github.com/ag48665

LinkedIn: https://www.linkedin.com/in/agatha-gabara-06494a37/
