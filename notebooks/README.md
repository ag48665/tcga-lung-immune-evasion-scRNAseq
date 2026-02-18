# Notebook 02 — CD8 T cell trajectory / pseudotime (Scanpy)

This notebook focuses on **CD8 T cells** and models a **trajectory from early/less exhausted states toward exhaustion** using **Diffusion Maps + Diffusion Pseudotime (DPT)** in Scanpy.

It is intended to be run **after** the initial scRNA-seq preprocessing/clustering notebook, or directly from an exported `.h5ad` object containing CD8 T cells.

---

## Goal

1. Build a CD8 T-cell manifold (HVGs → PCA → neighbors → UMAP → Leiden)
2. Compute an **exhaustion score** (checkpoint/exhaustion gene-set)
3. Choose a biologically plausible **start cluster** (lowest exhaustion score)
4. Run **Diffusion Maps** and **DPT pseudotime**
5. Visualize the trajectory and confirm that checkpoint markers increase along pseudotime
6. Save an output `.h5ad` with pseudotime and scores

---

## Inputs

Expected input file (relative to repo root):

- `data/lusc.h5ad` (not tracked in git)

If you are running from the `notebooks/` folder, ensure paths are correct (the notebook uses `Path("data") / "lusc.h5ad"` assuming the working directory is the repo root).

---

## Key methods

- **HVG selection** (robust flavor for log1p data)
- **PCA / neighbor graph**
- **UMAP** embedding
- **Leiden** clustering
- **Exhaustion scoring**
- **Diffusion map** and **Diffusion pseudotime (DPT)**
- Marker overlays: `PDCD1`, `LAG3`, `HAVCR2`, `TOX`, `GZMB`

---

## Outputs

This notebook produces:

### Figures (recommended to save into `results/figures/`)
- UMAP colored by **Leiden clusters**
- UMAP colored by **pseudotime**
- UMAP overlays of checkpoint/exhaustion markers (PDCD1/LAG3/HAVCR2/TOX)
- Scatter: **Exhaustion score vs pseudotime**

### Tables (optional)
- Mean exhaustion score per Leiden cluster (used to choose the start cluster)

### Saved AnnData
- Example output: `results/cd8_pseudotime_lusc.h5ad`
  - `obs["dpt_pseudotime"]`
  - `obs["exhaustion_score"]`
  - `obs["leiden"]`
  - embeddings and neighbors graph

---

## How to run

Open the notebook and run cells top-to-bottom.  
If UMAP is slow on your machine, run on a subset (e.g. 50k cells) and rerun on full data later.

---

## Notes / interpretation

- **Start cluster** should represent early/less exhausted CD8 T cells (lowest exhaustion score).
- If marker expression (PDCD1/LAG3/HAVCR2/TOX) increases with pseudotime, it supports a trajectory toward exhaustion.
- Pseudotime is a **relative ordering**, not real-time.

---

## Requirements

- Python 3.10+
- scanpy, anndata, numpy, pandas, scipy, matplotlib

Environment is provided in `environment.yml`.
