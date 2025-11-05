#  ICP Identification for B2B Benefits — Undergraduate Thesis

> **Author:** Félix Miranda  
> **Program:** Computational Engineering — Federal University of Juiz de Fora (UFJF)  
> **Advisor:** Prof. Flávia Rodrigues  
> **Year:** 2025

---

## Overview

This project investigates how to identify an **Ideal Customer Profile (ICP)** for companies that provide **corporate benefits** (e.g., TotalPass, Gympass, Swile, Unimed, Psicologia Viva).  
We combine **machine learning** with **firmographic data** to score and rank companies by their proximity to the ICP, supporting **B2B lead qualification** and **commercial prioritization**.

---

## Methodology

We use a **hybrid modeling** approach:

1. **One-Class Classification (OCC)**  
   Models the distribution of “ideal” companies using only positive examples.  
   - Primary algorithm: **Isolation Forest** (Sklearn).

2. **Distance-Based Scoring (DBS)**  
   Ranks candidates by **average distance to k-NN centroids** of known ICP companies.  
   - Provides intuitive **explainability** via feature-level distances.

**Why hybrid?**  
OCC provides robust anomaly detection around the ICP region; DBS adds an interpretable ranking signal. Together, they improve recall on promising leads and make results easier to explain to non-technical stakeholders.

---

##  Tech Stack

###  Core Languages
- **Python 3.10+** — main environment for data processing and modeling  
- **LaTeX (TeX Live / Overleaf)** — academic writing, UFJF ABNT-compliant template

---

###  Main Libraries

#### Data Handling
- `pandas` — tabular data manipulation and cleaning  
- `numpy` — vectorized operations and numerical arrays  
- `openpyxl` / `xlrd` — Excel I/O for firmographic data  
- `json`, `os`, `glob` — file system and structured data management

#### Machine Learning & Modeling
- `scikit-learn` — core ML framework (Isolation Forest, k-NN, preprocessing)  
- `scipy` — distance metrics, clustering utilities  
- `statsmodels` — complementary statistical tests and diagnostics  
- `matplotlib` / `seaborn` — visualization and diagnostics

#### Geospatial Analysis
- `geopandas` — mapping firmographic data by region  
- `shapely` / `contextily` — geospatial geometry and base maps  
- `folium` — interactive company distribution maps (when used)

#### Experimental Analytics
- `numba` — fast scoring loops (distance calculations)  
- `tqdm` — progress bars for k-NN and model iterations  
- `joblib` — parallel model execution and serialization  
- `mlxtend` — visualizing decision regions and nearest neighbors

---

###  Notebook & Experiment Management
- **JupyterLab / Google Colab** — interactive environment for experiments  
- **nbformat / nbconvert** — version control and notebook export  
- **Git + GitHub** — version tracking, CI/CD integration with LaTeX  
- **VS Code** — local IDE for both Python and TeX

---

### Data Storage & Sources
- **Local firmographic datasets** (TotalPass, Gympass, Swile, Unimed, Psicologia Viva)  
- **Backup Excel sheets & JSON exports** — raw scraping outputs and lead metadata  
- **CNPJ & LinkedIn data** — used for corporate identification and enrichment

---

###  Document Production
- **ABNT UFJF LaTeX class** (`abntbibufjf.cls`)  
- **BibTeX / JabRef** — citation management  
- **PDFLaTeX** — compilation  
- **Overleaf or VS Code LaTeX Workshop** — IDE support for writing and figures

---

###  Reproducibility
- Deterministic random seeds (`numpy.random.seed`)  
- Configurable number of neighbors and isolation depth  
- Reusable parameter configuration via YAML or notebook cells

---
