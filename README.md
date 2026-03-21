# Wine Quality Data Workflow

**Author:** Prof. Dr. Sc., Dr. Qeis Kamran  
**Dataset:** UCI Red Wine Quality — https://archive.ics.uci.edu/ml/datasets/wine+quality  
**Project:** Udacity MSc Artificial Intelligence — AI Programming Foundations Project

This project builds a complete, reproducible data workflow analyzing the physicochemical properties of red wines and their relationship to sommelier quality scores. The workflow covers data ingestion, cleaning, exploratory analysis, and visualization using Python, Pandas, Matplotlib, and Seaborn.

---

## What I Built

A Jupyter Notebook (`data_workflow.ipynb`) that:
- Loads and cleans the UCI Red Wine Quality dataset (400 rows × 12 columns)
- Applies two cleaning functions (duplicate removal, outlier clipping)
- Performs exploratory analysis including correlation analysis and quality group comparisons
- Produces three labeled visualizations (quality distribution, feature correlations, heatmap + scatter)

---

## Dataset

**Name:** UCI Red Wine Quality  
**Link:** https://archive.ics.uci.edu/ml/datasets/wine+quality  
**File:** `wine.csv` (semicolon-separated, 400 rows, 12 columns)  
**Key variables:** alcohol, volatile acidity, sulphates, citric acid, quality (score 3–8)

---

## How to Run the Project

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Open and run the notebook

```bash
jupyter notebook data_workflow.ipynb
```

Then: **Kernel → Restart & Run All**

### 3. Files required in the same folder
- `data_workflow.ipynb`
- `wine.csv`
- `requirements.txt`

---

## Future Integration

**ML workflow changes:** The cleaned dataset is ready for scikit-learn classification (predicting quality scores). The class imbalance (70% of wines score 5 or 6) would require SMOTE or class weighting before training.

**Neural network preparation:** The feature scaling applied in cleaning (z-score normalization) is the standard preprocessing step before feeding data into neural networks.

**Agentic automation potential:** An agentic system could automate the full pipeline — data ingestion, cleaning decisions, EDA, and report generation — using tool-calling to invoke each workflow step. This is demonstrated in the companion Project 6 (CEREBRA-CogAssess Agentic AI System).

---

## Bias and Data Quality

Poor data cleaning can introduce bias in wine quality analysis in two ways: (1) removing outliers by deletion rather than clipping can disproportionately remove wines from underrepresented quality classes (scores 3 and 8), worsening class imbalance; (2) if missing values were imputed with column means, they would artificially compress variance in the most important features (alcohol, volatile acidity). This project uses clipping rather than deletion, and there are no missing values in this dataset.
