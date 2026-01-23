# Single-Cell Analysis of the Tumor Immune Microenvironment

## Project Overview

This project focuses on the analysis of **single-cell RNA-sequencing (scRNA-seq) data** to study the **tumor immune microenvironment (TIME)**. The aim is to explore immune cell diversity within tumor samples, identify key immune populations, and examine the expression of immunotherapy-related markers using standard single-cell bioinformatics approaches.

The work is based on **data preprocessing, unsupervised clustering, immune cell annotation, and expression-based immune state characterization**.

---

## Project Notebook (Google Colab)

The full analysis is implemented in a Jupyter Notebook and can be accessed through Google Colab:

🔗 **Google Colab Notebook:**
👉 [https://colab.research.google.com/drive/1Z9GKILCqolUjuu2_rPxb9j2DeeWlwcWh?usp=sharing]

---

## Tools & Libraries Used

### Core Single-Cell Analysis

* Scanpy
* AnnData
* NumPy
* Pandas

### Dimensionality Reduction & Visualization

* PCA
* UMAP
* Leiden clustering
* Matplotlib
* Seaborn
* Plotly

### Additional Libraries

* leidenalg
* python-igraph
* HarmonyPy *(optional batch correction)*

### Environment

* Python 3.10+
* Google Colab
* Google Drive

---

## Analysis Workflow

### 1. Data Preprocessing & Quality Control

* Cells with fewer than 200 genes or more than 6000 genes were removed
* Cells with mitochondrial gene content above 10% were excluded
* Genes expressed in fewer than 3 cells were filtered out
* Counts were normalized to 10,000 per cell
* Log1p transformation was applied

---

### 2. Feature Selection & Scaling

* Highly variable genes were selected
* Data was scaled to zero mean and unit variance
* Principal Component Analysis (PCA) was performed
* The first 10 principal components were retained

---

### 3. Unsupervised Clustering

* A k-nearest neighbor graph (k = 15) was constructed
* Leiden clustering was applied with a resolution of 0.6
* UMAP was used for low-dimensional visualization

---

### 4. Cell Type Annotation

Cell clusters were annotated based on known immune marker genes and differential expression analysis.

**Marker genes used:**

* T cells: CD3D, CD3E
* B cells: MS4A1
* NK cells: NKG7, GNLY
* Myeloid cells: LST1, C1QA
* Dendritic cells: FCER1A

---

### 5. Biomarker Expression Analysis

* PD-L1 (CD274) expression was examined across clusters
* Immune checkpoint markers (PDCD1, CTLA4, LAG3, TIGIT) were analyzed
* Cytotoxic and activation markers (IFNG, GZMB, PRF1) were evaluated
* Myeloid signature genes (C1QA, LST1, CXCL9) were assessed

---

### 6. Immune State Characterization

Immune states were defined using expression-based scoring:

* **Inflamed:** high T-cell-associated expression
* **Immune-desert:** low T-cell expression with minimal PD-L1
* **Immune-excluded:** intermediate T-cell expression with PD-L1 presence

Quantile-based thresholds were used to keep the classification data-driven.

---

### 7. Spatial & Functional Patterns

* Immune states were visualized on UMAP embeddings
* Cluster-wise immune composition was examined
* Observed patterns were interpreted in the context of tumor immunology

---

## Outputs

* Cell type distributions
* Differentially expressed gene lists
* PD-L1 expression profiles
* Immune state annotations
* UMAP plots with multiple overlays
* Violin plots and heatmaps for marker genes

---

## Validation

* Wilcoxon rank-sum test for differential expression
* False discovery rate (FDR) correction
* Consistency with established immune biology
* Reproducible results across multiple runs

---

## Conclusion

This project provides a clear and reproducible single-cell RNA-seq analysis workflow for studying the tumor immune microenvironment. By combining quality control, unsupervised clustering, immune cell annotation, and marker-based immune state analysis, the study reveals meaningful immune patterns within tumor samples.

The results offer biologically interpretable insights into immune activation, suppression, and exclusion, and demonstrate practical experience in single-cell transcriptomics and cancer immunology research.


