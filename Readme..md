#  DevelopersHub Corporation — AI/ML Engineering Internship Tasks

This repository contains my completed tasks for the **AI/ML Engineering Internship** at DevelopersHub Corporation.

---

# Task 1: Exploring and Visualizing the Iris Dataset

# Objective
Load, inspect, and visualize the famous Iris Dataset to understand data trends, distributions, and relationships between features — building the foundation for any data science workflow.

# Dataset
- **Name:** Iris Dataset
- **Source:** `sklearn.datasets` (same data as the standard CSV)
- **Size:** 150 samples × 4 features + 1 target label
- **Classes:** Iris Setosa, Iris Versicolor, Iris Virginica

# Libraries Used
| Library | Purpose |
|---|---|
| `pandas` | Data loading, inspection, manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Base plotting |
| `seaborn` | Statistical visualizations |
| `sklearn` | Loading the Iris dataset |

# Models / Techniques Applied
This task is focused on **Exploratory Data Analysis (EDA)** — no predictive model is trained.

Techniques used:
- `.head()`, `.info()`, `.describe()` for data inspection
- Pairplot (scatter matrix) for feature relationships
- Histograms for value distributions
- Box plots for outlier detection
- Correlation Heatmap for feature relationships

# Key Results & Findings

| Finding | Detail |
|---|---|
| Missing values | None — dataset is perfectly clean |
| Class balance | Balanced — 50 samples per species |
| Best separating features | **Petal Length & Petal Width** |
| Weakest feature | Sepal Width (overlaps heavily across classes) |
| Most distinct species | **Iris Setosa** — clearly separable |
| Most similar species | Versicolor & Virginica — some overlap |
| Highest correlation | Petal Length ↔ Petal Width (r = 0.96) |
| Outliers found | Very few; mainly in Setosa Sepal Width |

# Insights
1. Petal measurements are far more discriminative than sepal measurements.
2. Iris Setosa is trivially separable; the challenge lies in Versicolor vs Virginica.
3. The high correlation between petal features is worth considering for future dimensionality reduction (e.g., PCA).
4. The dataset is clean, balanced, and ideal for classification model training.

# Files
```
Task1_Iris_Dataset_EDA.ipynb   ← Colab Notebook (all code + visualizations)
README.md                      ← This file
```

# How to Run
```bash
# Install required libraries (if not already installed)
pip install pandas numpy matplotlib seaborn scikit-learn

```

---

*More tasks will be added as the internship progresses.*
