# Iris Flower Analysis

This directory contains an exploratory data analysis (EDA) of the Iris flower dataset, focusing on species differentiation through statistical summaries and visualizations. No machine learning models for classification are implemented; the focus is on data understanding, feature correlations, and variability across species.

## Files
- **iris-flower.ipynb**: Jupyter Notebook with the complete analysis.
- **IRIS.csv**: Dataset file (Iris data with sepal/petal measurements and species).

## Dataset Overview
- Shape: 150 rows, 5 columns (after dropping ID if present).
- Target: `species` (Iris-setosa, Iris-versicolor, Iris-virginica; 50 samples each).
- Key features: `sepal_length`, `sepal_width`, `petal_length`, `petal_width`.

## Methods and Techniques Used
1. **Data Loading and Preparation**:
   - Load data using `pandas.read_csv("Iris.csv")`.
   - Remove ID column (if present) to focus on features.
   - Suppress warnings and set plotting styles with `matplotlib` and `seaborn`.

2. **Dataset Inspection**:
   - Display first rows (`df.head()`).
   - Info: Rows, columns, missing values (`df.isnull().sum()`), duplicates (`df.duplicated().sum()`).

3. **Statistical Analysis**:
   - Descriptive stats (`df.describe()`).
   - Correlation matrix using `df.corr()`.
   - Grouped stats by species using `groupby()` (mean, std, etc.).
   - Coefficient of Variation (CV): `(std / mean) * 100` per feature and species.

4. **Visualizations**:
   - Species distribution countplot (`seaborn.countplot()`).
   - Pairplot with hue by species (`seaborn.pairplot()`).
   - Correlation heatmap (`seaborn.heatmap()`).
   - Boxplots and violin plots per feature by species (`seaborn.boxplot()`, `seaborn.violinplot()`).
   - Scatterplots (e.g., petal length vs. width) with hue (`seaborn.scatterplot()`).
   - Bar plot for CV by species and feature.

5. **Insights Summary**:
   - Printed key findings: balanced classes, no missing/duplicates, strong petal correlations, species separation (e.g., Setosa distinct in petals).

## Key Insights
- Equal distribution: 50 samples per species.
- Strong correlation: Petal length and width (overall ~0.96).
- Variability: Highest in petal width for Virginica (CV ~18%).
- Clear separation: Setosa has smaller petals; Versicolor and Virginica overlap more in sepals.

## Usage
Open `iris-flower.ipynb` in Jupyter and run cells sequentially. Ensure `IRIS.csv` is in the same directory.

## Dependencies
- pandas, numpy, matplotlib, seaborn.
