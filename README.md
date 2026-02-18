# Immune Evasion in Lung Squamous Cell Carcinoma

## Single-cell transcriptomic identification of exhausted CD8⁺ T cells

---

## Project Overview

Tumors can evade immune destruction even when infiltrated by cytotoxic T lymphocytes.
One proposed mechanism is **T-cell exhaustion** — a dysfunctional differentiation state caused by chronic antigen stimulation inside the tumor microenvironment.

This project analyzes human lung tumor single-cell RNA-seq data to determine whether tumor-infiltrating CD8⁺ T cells exist in a transcriptionally exhausted state.

Using a reproducible Scanpy workflow, I:

• identified immune cell populations
• isolated CD8⁺ T cells
• quantified exhaustion signatures
• reconstructed differentiation trajectory (pseudotime)
• performed differential expression analysis

The analysis demonstrates that tumors may escape immune clearance not by excluding T cells, but by functionally disabling them.

---

## Dataset

Public dataset:

**GEO: GSE131907 — Human Lung Tumor Microenvironment scRNA-seq**

The repository does not contain raw data due to size limitations.

### To reproduce the analysis

1. Download the processed dataset (h5ad)
2. Place it into:

```
data/lusc.h5ad
```

All notebooks will run automatically once the file is present.

---

## Analysis Workflow

### 1. Preprocessing

* quality control filtering
* mitochondrial content filtering
* library size normalization
* log transformation
* highly variable gene selection

### 2. Dimensionality Reduction

* PCA
* nearest neighbor graph
* Leiden clustering
* UMAP visualization

### 3. Cell Type Annotation

Annotated using canonical immune markers:

| Cell Type   | Marker Genes |
| ----------- | ------------ |
| T cells     | CD3D, CD3E   |
| CD8 T cells | CD8A         |
| NK cells    | NKG7, GNLY   |
| B cells     | MS4A1        |
| Myeloid     | LST1         |

---

## Identification of Exhausted CD8⁺ T Cells

An exhaustion signature score was computed using checkpoint and regulatory genes:

**PDCD1, CTLA4, LAG3, TIGIT, HAVCR2, TOX**

CD8 T cells with the highest exhaustion scores formed a distinct transcriptional population on UMAP embedding.

---

## Pseudotime Trajectory Analysis

To model T-cell differentiation, diffusion pseudotime (DPT) was computed.

The trajectory revealed a progression:

**early effector CD8 T cells → intermediate state → terminally exhausted CD8 T cells**

Exhaustion marker expression increased along pseudotime, supporting a continuous differentiation process rather than discrete cell types.

---

## Differential Expression

Exhausted vs non-exhausted CD8 T cells were compared using the Wilcoxon rank-sum test.

Observed changes:

Upregulated:

* inhibitory receptors
* regulatory transcription factors

Downregulated:

* cytotoxic effector genes

Results available in:

```
results/tables/
```

---

## Repository Structure

```
data/               input data (ignored by git)
notebooks/          analysis notebooks
scripts/            helper scripts
results/figures/    visualizations
results/tables/     differential expression results
```

---

## Reproducibility

```
conda env create -f environment.yml
conda activate lusc_scRNA
jupyter lab
```

---

## Skills Demonstrated

* single-cell RNA-seq analysis (Scanpy)
* clustering & cell annotation
* gene signature scoring
* trajectory inference (pseudotime)
* differential expression
* biological interpretation
* reproducible research workflow

---

## Biological Interpretation

The data indicate that lung tumors contain infiltrating CD8⁺ T cells that are transcriptionally suppressed rather than absent.

Elevated TOX and immune checkpoint expression suggests chronic antigen exposure and terminal differentiation into an exhausted state.

This provides computational evidence supporting immune evasion via functional T-cell inactivation and explains the biological rationale for checkpoint inhibitor therapy.

---

## Author

**Agata Gabara**
