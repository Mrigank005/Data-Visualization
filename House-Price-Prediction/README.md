# House Price Analysis

This directory contains an exploratory data analysis (EDA) of the Ames Housing dataset, focusing on house price insights through statistical summaries and visualizations. No machine learning models for prediction are implemented; the focus is on data understanding, feature correlations, and outlier identification.

## Files
- **House.ipynb**: Jupyter Notebook with the complete analysis.
- **House_prediction.csv**: Dataset file (Ames Housing data with features like lot area, living area, quality ratings, and sale prices).

## Dataset Overview
- Shape: 1460 rows, 81 columns.
- Target: `SalePrice` (house sale price in USD).
- Key features analyzed: `OverallQual`, `GrLivArea`, `GarageCars`, `GarageArea`, `TotalBsmtSF`, `LotArea`, neighborhoods, etc.

## Methods and Techniques Used
1. **Data Loading and Preparation**:
   - Load data using `pandas.read_csv()`.
   - Suppress warnings and set plotting styles with `matplotlib` and `seaborn`.

2. **Dataset Inspection**:
   - Display shape, memory usage, first rows (`df.head()`).
   - Column info (`df.info()`), descriptive stats (`df.describe()`).
   - Identify numerical and categorical columns.

3. **Missing Values Analysis**:
   - Calculate missing counts and percentages.
   - Display as a sorted DataFrame for columns with missing data (e.g., `PoolQC` at 99.5% missing).

4. **Statistical Analysis**:
   - Correlation matrix for numerical features using `df.corr()`.
   - Focus on correlations with `SalePrice` (e.g., `OverallQual`: 0.791).
   - Skewness and kurtosis using `scipy.stats.skew()` and `kurtosis()`.
   - Grouped statistics by neighborhood and overall quality using `groupby()` and aggregations (mean, median, etc.).

5. **Visualizations**:
   - Histogram and KDE for `SalePrice` distribution (`seaborn.histplot()`).
   - Boxplots for `SalePrice` by neighborhood and quality (`seaborn.boxplot()`).
   - Scatterplots for key correlations (e.g., `GrLivArea` vs. `SalePrice`) using `seaborn.scatterplot()`.
   - Correlation heatmap (`seaborn.heatmap()`).
   - Pairplot for selected features (`seaborn.pairplot()`).

6. **Outlier Detection**:
   - Use IQR method: Calculate Q1, Q3, and bounds (1.5 * IQR).
   - Applied to `SalePrice`, `GrLivArea`, `LotArea`, `TotalBsmtSF`.
   - Results summarized in a DataFrame (e.g., 4.2% outliers in `SalePrice`).

7. **Insights Summary**:
   - Printed key findings: averages, medians, top correlations, neighborhood insights, quality breakdowns, data quality notes, and modeling recommendations (e.g., log transform `SalePrice`, handle missing values).

## Key Insights
- Average sale price: $180,921.
- Strongest predictors: Overall quality and living area.
- Outliers: 61 in sale price (4.2%).
- Recommendations: Focus on key features for future modeling, engineer new ones like house age.

## Usage
Open `House.ipynb` in Jupyter and run cells sequentially. Ensure `House_prediction.csv` is in the same directory.

## Dependencies
- pandas, numpy, matplotlib, seaborn, scipy.
