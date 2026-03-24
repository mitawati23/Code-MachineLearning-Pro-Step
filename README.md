# Code-MachineLearning-Pro-Step

# Kidney Cancer Subtype Classification Using miRNA Expression Data

## 1. Project Title

**Machine Learning-Based Classification of Kidney Cancer Subtypes Using miRNA Expression Data**

This repository contains the implementation used in the study for classifying kidney cancer subtypes based on miRNA expression profiles obtained from The Cancer Genome Atlas (TCGA).

---

## 2. Dataset Source

The dataset used in this study was obtained from the **Genomic Data Commons (GDC) TCGA portal**.

### Kidney Cancer Subtypes
- **KICH** – Kidney Chromophobe
- **KIRC** – Kidney Renal Clear Cell Carcinoma
- **KIRP** – Kidney Renal Papillary Cell Carcinoma

### Data Types
- miRNA Expression Data
- Clinical / Phenotype Data

Dataset source:
https://portal.gdc.cancer.gov/

---

## 3. Dataset Summary

| Kidney Cancer Subtype | Number of miRNAs | Number of Samples |
|----------------------|------------------|------------------|
| KICH (Chromophobe RCC) | 1881 | 91 |
| KIRC (Clear Cell RCC) | 1881 | 592 |
| KIRP (Papillary RCC) | 1881 | 326 |

---

## 4. Repository Structure


---

## 5. Code Description

| File Name | Description |
|-----------|-------------|
| preprocessing.ipynb | Performs data preprocessing including data cleaning, feature harmonization, and dataset integration |
| feature_selection_lasso.ipynb | Applies LASSO-based feature selection to identify informative miRNA biomarkers |
| model_training.py | Trains the classification model using selected miRNA features |
| cross_validation.py | Performs 5-fold cross-validation to evaluate model performance |
| evaluation_metrics.py | Calculates Accuracy, Precision, Recall, F1-score, and MCC |
| tsne_visualization.ipynb | Generates t-SNE visualization to analyze subtype clustering |

---

## 6. Data Preprocessing

The preprocessing stage includes:

1. Data transposition to ensure each row represents a patient sample.
2. miRNA feature harmonization across KICH, KIRC, and KIRP datasets.
3. Integration of miRNA expression data with clinical subtype labels.
4. Removal of duplicated samples and missing labels.
5. Label encoding:
   - KICH = 0  
   - KIRC = 1  
   - KIRP = 2  

---

## 7. Feature Selection

Feature selection is performed using **LASSO (Least Absolute Shrinkage and Selection Operator)** to reduce the dimensionality of high-dimensional miRNA data while retaining informative features.

Three different feature subsets were evaluated:

- **20 selected miRNAs**
- **35 selected miRNAs**
- **50 selected miRNAs**

---

## 8. Model Training and Evaluation

The classification model was evaluated using **5-fold cross-validation**.

### Cross-Validation Results (35 Selected miRNAs)

| Fold | Accuracy | MCC |
|-----|---------|------|
| 1 | 0.9356 | 0.8824 |
| 2 | 0.9406 | 0.8934 |
| 3 | 0.9604 | 0.9299 |
| 4 | 0.9109 | 0.8374 |
| 5 | 0.9403 | 0.8898 |
| **Average** | **0.9376** | **0.8866** |

Evaluation metrics used:

- Accuracy
- Precision
- Recall
- F1-score
- Matthews Correlation Coefficient (MCC)

---

## 9. Visualization

To further analyze model performance and data separability, the following visualizations were generated:

- Confusion Matrix
- Learning Curve
- t-SNE Visualization

These visualizations help illustrate classification behavior and clustering patterns among kidney cancer subtypes.

---

## 10. Requirements

Install the required dependencies using:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
