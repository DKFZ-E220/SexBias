# HNSCatlas

**HNSCatlas** is an R package containing single-cell RNA-seq data from Head and Neck Squamous Cell Carcinoma (HNSCC) patients. The dataset includes metadata such as patient sex, HPV status, and cell type annotations, providing a unified atlas for studying HNSCC microenvironments.

---

## Features

- **Integrated Dataset**: Combines data from multiple publicly available GEO datasets:  
  - **GSE234933**  
  - **GSE182227**  
  - **GSE164690**  
  - **GSE181919**

- **Metadata Integration**: Includes key metadata fields such as:
  - `nCount_RNA`: Total RNA counts per cell
  - `nFeature_RNA`: Number of unique features (genes) detected per cell
  - `Patient`: Patient identifier
  - `Source`: Sample source (e.g., tumor or normal tissue)
  - `Sex`: Patient sex (Male/Female)
  - `HPV`: HPV status (Positive/Negative)
  - `scGate_multi`: Multi-gate classification results
  - `Cell_Labels`: Harmonized cell type annotations
  - `Dataset`: Origin dataset
  - `Original_Cell_Type`: Initial cell type annotations

- **Integration Tools**: Data harmonized and processed using `Seurat`, `scGate`, `STACAS`, and `Ikarus`.

---

## Installation

You can install the package directly from GitHub using `devtools`:

```R
# Install devtools if not already installed
install.packages("devtools")

# Install HNSCatlas from GitHub
devtools::install_github("DKFZ-E220/HNSCatlas")
