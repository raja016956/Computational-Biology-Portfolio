# QSAR Modelling of EGFR Inhibitors

## Project Overview

This project implements a **Quantitative Structure–Activity Relationship (QSAR)** workflow to predict **pIC50 values of EGFR inhibitors** using publicly available bioactivity data from **ChEMBL**.

The objective is to build and validate a regression model that links **molecular structure** to **biological activity**, following standard practices used in computational drug discovery.

The analysis covers **data collection, curation, molecular representation, model training, validation, and external screening** using chemically meaningful descriptors.

---

## Project Notebook (Google Colab)

The complete workflow is provided as a Jupyter Notebook and can be run on Google Colab:

🔗 **Google Colab Notebook:**
👉 [https://colab.research.google.com/drive/1X0GuZ0wCAsVnuT-Sb4RedvsIqJbjnm5a?usp=sharing]

---

## Tools & Libraries Used

### Cheminformatics & Data Sources

* ChEMBL Web Resource Client
* RDKit

### Data Handling & Computation

* Pandas
* NumPy

### Machine Learning & Validation

* scikit-learn
* XGBoost

### Visualization

* Matplotlib
* Seaborn

### Deployment

* Streamlit
* joblib
* pyngrok

---

## Workflow Summary

### 1. Data Collection

* EGFR (human, single-protein) was selected as the biological target
* IC50 bioactivity data (binding assays only) was retrieved from ChEMBL
* Only measurements reported in **nM** with exact values (`=`) were retained

---

### 2. Data Cleaning & Processing

* Missing SMILES entries were removed
* Duplicate molecules were merged by averaging pIC50 values
* IC50 values were converted to **pIC50**
* Intermediate activity values were excluded for clearer modeling

Final curated dataset size: **~3,100 unique compounds**

---

### 3. Molecular Representation

Each molecule was represented using multiple complementary features:

* **Morgan fingerprints** (radius 3, 2048 bits)
* **Lipinski descriptors** (MW, LogP, H-bond donors/acceptors)
* **2D molecular descriptors** (TPSA, rotatable bonds, rings, CSP3, etc.)

All features were combined into a single numeric feature matrix.

---

### 4. Feature Engineering

* Low-variance features were removed
* PCA was applied to fingerprint features to reduce dimensionality
* Final feature set combined reduced fingerprints with physicochemical descriptors

---

### 5. Model Training

* An **XGBoost regression model** was trained to predict pIC50
* Data was split into training, validation, and test sets
* Early stopping and regularization were used to control overfitting

**Test performance (final model):**

* R² ≈ **0.68**
* RMSE ≈ **0.85**

---

### 6. Model Validation

Multiple validation steps were applied:

* **Train vs test comparison**
* **Feature importance analysis**
* **Reduced-feature model** (top 50 features)
* **Residual analysis**
* **Y-randomization (Y-scrambling)**
* **Applicability domain (distance-based)**

These checks confirmed that the model captures genuine structure–activity relationships rather than random correlations.

---

### 7. External Validation & Virtual Screening

* The trained model was applied to an **external compound set**
* Molecular features were generated using the same pipeline
* Predictions were filtered using the applicability domain
* Top-ranked compounds were identified based on predicted pIC50

Approximately **89% of external compounds** fell within the applicability domain.

---

### 8. Model Deployment

* The validated model and supporting files were saved using `joblib`
* A **Streamlit web application** was built to:

  * Predict pIC50 from single SMILES
  * Perform batch predictions from uploaded CSV files
  * Indicate applicability domain status
* The app was deployed via **ngrok** for remote access

---

## Outputs

* Curated EGFR bioactivity dataset
* QSAR regression model
* Performance metrics and validation plots
* External screening predictions
* Interactive Streamlit web app

---

## Conclusion

This project demonstrates a complete and well-validated QSAR workflow for predicting EGFR inhibitor activity using publicly available data. Through careful data curation, meaningful molecular representation, and rigorous validation, the model achieves reliable predictive performance within its defined chemical space.

The work reflects practical experience in cheminformatics, QSAR modeling, and model validation as commonly applied in computational drug discovery.



Just tell me 👍
