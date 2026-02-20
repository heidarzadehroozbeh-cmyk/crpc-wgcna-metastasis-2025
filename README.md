# CRPC WGCNA Metastasis 2025

This repository contains the reproducible R code used in the manuscript:

(https://doi.org/10.1016/j.adcanc.2025.100132)

The project aims to:

* Download and preprocess the public microarray dataset **GSE74685** (castration-resistant prostate cancer metastases).
* Perform differential expression analysis (**Bone vs Visceral** metastatic sites).
* Build a WGCNA network and detect co-expression modules.
* Correlate modules with metastatic site traits.
* Extract long non-coding RNA (lncRNA) candidates (*TP53TG1*, *RFPL1S*, *DLEU1*).
* Export gene–module assignments, module–trait correlations, candidate lists, and example figures.

All analyses are implemented in R and organized as a small, self-contained pipeline.

---

## Directory Structure

**`crpc-wgcna-metastasis-2025.Rproj`** – RStudio project file (recommended entry point).

### `scripts/`

Main analysis scripts:

* **Script 01_load_packages.R** – Installs and loads packages (*GEOquery*, *Biobase*, *limma*, *WGCNA*, *dynamicTreeCut*, *tidyverse*), sets global options.
* **Script 02 - download & preprocess GSE74685.R** – Downloads GSE74685, filters, and saves processed data.
* **Script 03 - DE analysis (Bone vs Visceral).R** – Performs differential expression analysis with limma.
* **Script 04 - WGCNA network and modules (GSE74685).R** – Builds WGCNA network, detects modules, correlates with traits, exports results.
* **Script 05 - Extract module genes & lncRNA candidates (GSE74685).R** – Generates candidate gene and lncRNA lists combining DE and WGCNA results.
* **Optional GPL annotation helper script** – Builds clean annotation tables and identifies lncRNA biotypes.

### `data/`

Processed expression matrices, phenotype tables, and WGCNA objects. Files are regenerable and excluded from version control.

### `results/`

CSV outputs from DE and WGCNA analyses:

* DEG tables
* Module–trait correlation tables
* Gene/module/lncRNA candidate lists

### `figures/`

Key plots from the pipeline:

* Sample clustering dendrograms
* Scale-free topology plots
* Gene dendrogram with module colours
* TOM and module–trait heatmaps

### `docs/`

Lightweight documentation, such as platform/GPL annotation files.

---

## Requirements

* R ≥ 4.2
* Packages: `GEOquery`, `Biobase`, `limma`, `WGCNA`, `dynamicTreeCut`, `tidyverse`

All required packages are loaded (and installed if missing) by `scripts/Script 01_load_packages.R`.

---

## Running the Pipeline

1. Clone or download the repository.
2. Open `crpc-wgcna-metastasis-2025.Rproj` in RStudio.
3. Run scripts in order:

   1. `01_load_packages.R`
   2. `02 - download & preprocess GSE74685.R`
   3. `03 - DE analysis (Bone vs Visceral).R`
   4. `04 - WGCNA network and modules (GSE74685).R`
   5. `05 - Extract module genes & lncRNA candidates (GSE74685).R`
4. Outputs will appear in `data/`, `results/`, and `figures/`.
5. Figures can be directly used in manuscripts or adapted for new analyses.

---

## License

Code is released under the **MIT License**.
Underlying expression data (**GSE74685**) remain subject to original GEO/authors’ terms.

---

## Author

**Dr. Roozbeh Heidarzadehpilehrood**
Human Geneticist – Transcriptomics & ncRNA biomarkers
**Email:** [heidarzadeh.roozbeh@gmail.com](mailto:heidarzadeh.roozbeh@gmail.com)

---

## Citation

If using this code or parts of the pipeline, cite both:

1. Mehrabi T, Heidarzadeh R, et al.
   Dysregulated key long non-coding RNAs *TP53TG1*, *RFPL1S*, *DLEU1* in prostate cancer.
   *Advances in Cancer Biology – Metastasis*. [https://doi.org/10.1016/j.adcanc.2025.100132](https://doi.org/10.1016/j.adcanc.2025.100132)

2. Heidarzadeh R. (2025).
   heidarzadehroozbeh-cmyk/crpc-wgcna-metastasis-2025: First public release – CRPC WGCNA metastasis pipeline (v1.0.0).
   [https://doi.org/10.5281/zenodo.17830034](https://doi.org/10.5281/zenodo.17830034)

---

