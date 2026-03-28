# Molecular Subtype Prediction of Brain Lower-Grade Gliomas (LGG)

This repository evaluates whether a **Multinomial Logistic Regression** model outperforms a **Random Assignment baseline** in predicting the molecular subtypes of Brain Lower-Grade Gliomas (LGG) using transcriptomic data.

## 🔬 Research Question
> **"Does a Multinomial Logistic Regression model outperform Random Assignment in the molecular subtype prediction of Brain Lower-Grade Gliomas based on mRNA expression profiles?"**

## 📂 Project Structure
The project is organized to maintain a clean separation between data cleaning, statistical modeling, and exploratory analysis:

* **`notebooks/`**: 
    * `LGG_EDA_Preprocessing.ipynb`: Initial data acquisition, quality checks, cleaning, and preliminary Exploratory Data Analysis (EDA) using Python.
* **`analysis/`**: 
    * `LGG_gene_expression_analysis.Rmd`: Core R workflow including log transformation, low-variance gene filtering, standardization, PCA, and Multinomial Logistic Regression.
    * `LGG_DataVisualization.Rproj`: RStudio project configuration.
* **`docs/`**: 
    * `LGG_gene_expression_analysis.html`: The final compiled report containing code, statistical outputs, and visualizations.
* **`data/`**: (Local Only) Directory for raw TCGA-LGG datasets. *Note: Data files are excluded via `.gitignore` to maintain repository efficiency.*

## 🛠️ Tech Stack & Data Source
- **Python**: `pandas`, `numpy`, `seaborn`, `matplotlib` (Data cleaning & EDA).
- **R**: `nnet` (Multinomial modeling), `ggplot2`, `factoextra`, `stats` (Bioinformatics pipeline).
- **Data Source**: [TCGA Pan-Cancer Atlas 2018 (LGG)](https://www.cbioportal.org/study/summary?id=lgg_tcga_pan_can_atlas_2018)
    *Includes genomic and clinical profiles for 514 patients with Brain Lower-Grade Glioma.*

## 🔄 Methodology & Workflow
The project follows a rigorous bioinformatics pipeline divided into four primary phases:

1.  **Acquisition & Cleaning (Python)**:
    * Loading clinical and genomic datasets.
    * Handling missing values and performing initial quality control checks.
2.  **Bioinformatics Processing (R)**:
    * **Filtering**: Removing low-variance genes to focus on biologically informative features.
    * **Transformation**: Applying Log2 transformation to stabilize variance across the expression matrix.
3.  **Dimensionality Reduction (R)**:
    * Executing **Principal Component Analysis (PCA)** to reduce the high-dimensional mRNA data into manageable components while retaining maximum variance.
4.  **Statistical Modeling & Evaluation (R)**:
    * Training a **Multinomial Logistic Regression** model using PCA-derived features.
    * Comparing model accuracy against a **Random Assignment** baseline to assess predictive significance.

## 📊 Key Findings
* The Multinomial Logistic Regression model demonstrated significant predictive power, substantially outperforming the random baseline.
* PCA effectively captured the transcriptomic signatures that distinguish major LGG molecular subclusters, as evidenced by the separation in the leading principal components.
* *Further details can be found in the compiled report located in the `docs/` folder.*

## 🚀 How to Reproduce
1.  **Clone the repository**:
    ```bash
    git clone [https://github.com/gracelin1718/Data-Visualization-Project.git](https://github.com/gracelin1718/Data-Visualization-Project.git)
    ```
2.  **Initial Cleaning**: Review the Python notebook in `notebooks/` for data preparation steps.
3.  **Run Statistical Analysis**: Open `analysis/LGG_gene_expression_analysis.Rmd` in RStudio to execute the filtering, PCA, and modeling.
4.  **View Report**: Open `docs/LGG_gene_expression_analysis.html` in any browser for the full annotated results.

---
**Author**: Yuhe(Grace) Lin  
**Course**: STAT-3660 Data Visualization and Mining | University of Prince Edward Island
