---------------------------------------------------------------------

# CRPC WGCNA Metastasis Pipeline  
**Transcriptomic network analysis of metastatic CRPC (GSE74685)**

[![R](https://img.shields.io/badge/R-4.2.0+-276DC3.svg?style=for-the-badge)]()  
[![WGCNA](https://img.shields.io/badge/WGCNA-1.72--1-4f8bc9?style=for-the-badge)]()  
[![limma](https://img.shields.io/badge/limma-3.58.1-0096d1?style=for-the-badge)]()  
[![License: MIT](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)]()  
[![DOI](https://img.shields.io/badge/DOI-10.1016%2Fj.adcanc.2025.100132-purple?style=for-the-badge)]()  
[![Zenodo](https://img.shields.io/badge/Zenodo-17830034-blue?style=for-the-badge)]()

---

## 🔬 Overview

This repository contains a fully reproducible **R‑based transcriptomic pipeline** for:

• Differential gene expression (**Bone vs Visceral metastases**)  
• **Weighted Gene Co‑expression Network Analysis (WGCNA)**  
• Module–trait correlation  
• lncRNA biomarker discovery in metastatic CRPC  
• Export of reproducible tables + figures used in the manuscript

**Dataset:** GSE74685  
**Study:** Adv Cancer Biol – Metastasis (2025)  
**Key lncRNAs identified:** *TP53TG1*, *RFPL1S*, *DLEU1*

---

## 🧬 Workflow Snapshot

```
      ┌─────────────────┐
      │  GEOquery       │
      │ Download GSE    │
      └───── ──┬────────┘
               │
      ┌────────▼────────┐
      │ Preprocessing   │
      │  QC + Filtering │
      └────────┬────────┘
               │
      ┌────────▼────────┐
      │  limma DEGs     │
      │ Bone vs Visceral│
      └────────┬────────┘
               │
      ┌────────▼────────┐
      │     WGCNA       │
      │ Modules + MEs   │
      └────────┬────────┘
               │
      ┌────────▼────────┐
      │ Module–Trait    │
      │ Correlations    │
      └────────┬────────┘
               │
      ┌────────▼────────────┐
      │ lncRNA Candidates   │
      │ TP53TG1, RFPL1S,... │
      └─────────────────────┘
```

---

## 📁 Repository Structure

**scripts/**  
• 01_load_packages.R  
• 02_download_preprocess_GSE74685.R  
• 03_DE_analysis_Bone_vs_Visceral.R  
• 04_WGCNA_network_and_modules.R  
• 05_extract_module_genes_lncRNA_candidates.R  

**data/**  
• Processed matrices + WGCNA objects (auto-generated)

**results/**  
• DEGs  
• module–trait correlations  
• gene–module assignments  
• lncRNA candidate lists  

**figures/**  
• dendrograms  
• TOM heatmaps  
• module–trait heatmaps  
• scale‑free topology plots  

---

## 🖥 Software & Package Versions (Exact)


**R version**  
• R 4.2.3 (2023-03-15)

**CRAN/Bioconductor packages**  
• GEOquery 2.70.0  
• Biobase 2.62.0  
• limma 3.58.1  
• WGCNA 1.72-1  
• dynamicTreeCut 1.63-1  
• tidyverse 2.0.0  

---

## ▶️ Running the Pipeline

1. Clone:

```
git clone https://github.com/heidarzadehroozbeh-cmyk/crpc-wgcna-metastasis-2025
```

2. Open RStudio project:

```
crpc-wgcna-metastasis-2025.Rproj
```

3. Run scripts in order:

```
01_load_packages.R
02_download_preprocess_GSE74685.R
03_DE_analysis_Bone_vs_Visceral.R
04_WGCNA_network_and_modules.R
05_extract_module_genes_lncRNA_candidates.R
```

4. Outputs appear in:  
`data/`, `results/`, `figures/`

---

## 📊 Data Availability

Public transcriptomic dataset:

GSE74685  
https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE74685

---

## ✨ Citation

**Primary publication:**  
Mehrabi T, Heidarzadeh R, et al.  
Advances in Cancer Biology – Metastasis (2025)  
https://doi.org/10.1016/j.adcanc.2025.100132

**Software release:**  
Heidarzadeh R (2025).  
Zenodo: https://doi.org/10.5281/zenodo.17830034

---

## 👤 Author

Dr. Roozbeh Heidarzadehpilehrood  
Human Geneticist – Transcriptomics & ncRNA Biomarkers  
Email: heidarzadeh.roozbeh@gmail.com

---

## 📄 License

MIT License  
(Underlying GEO data subject to original terms)

---------------------------------------------------------------------
