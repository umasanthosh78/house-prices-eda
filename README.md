# Exploratory Data Analysis of House Prices

## Project Overview

This project performs exploratory data analysis (EDA) on the **Ames
Housing Dataset**, from the Kaggle competition *House Prices: Advanced
Regression Techniques*.

-   **Dataset file:** `train.csv`
-   **Approximate size:** 1,460 rows and 81 columns
-   **Objective:** Explore the factors associated with house sale prices
    using EDA only. This project does not build a machine-learning
    model.

## Guiding Questions

1.  How is `SalePrice` distributed? Is it skewed?
2.  Which numerical features correlate most strongly with `SalePrice`?
3.  Does `OverallQual` show a clear relationship with sale price?
4.  Do some neighborhoods consistently have higher house prices?
5.  Are there outliers, and do they represent errors or unusual but
    valid sales?
6.  Which columns contain missing values, and which missing values
    actually indicate that a feature is absent?

## Tools and Libraries

-   Python
-   Pandas
-   NumPy
-   Matplotlib
-   Seaborn
-   SciPy
-   Jupyter Notebook

## Project Workflow

The notebook follows these stages:

1.  **Introduction** --- State the objective, describe the dataset, and
    list the guiding questions.
2.  **Data loading** --- Load `train.csv`; inspect its shape, first
    rows, data types, and missing values.
3.  **Data understanding** --- Classify numerical, categorical, and
    ordinal variables; calculate descriptive statistics.
4.  **Data cleaning** --- Check duplicates, inconsistent category
    labels, missing values, and impossible values.
5.  **Univariate analysis** --- Examine distributions with histograms,
    KDE plots, boxplots, and countplots.
6.  **Bivariate and multivariate analysis** --- Explore correlations,
    scatter plots, and pair plots.
7.  **Correlation heatmap** --- Visualize relationships among the ten
    features most correlated with `SalePrice`.
8.  **Outlier analysis** --- Compare IQR and z-score methods and inspect
    flagged observations.
9.  **Dashboard** --- Combine key findings into a four-panel
    visualization.
10. **Conclusions** --- Summarize observed patterns and limitations.

## Key Analysis Details

### Variable types

Examples used in the analysis:

-   Continuous numerical: `SalePrice`, `GrLivArea`, `LotArea`,
    `TotalBsmtSF`, `GarageArea`
-   Discrete numerical: `YearBuilt`, `YrSold`, `FullBath`,
    `BedroomAbvGr`
-   Categorical: `Neighborhood`, `HouseStyle`, `SaleCondition`,
    `MSZoning`
-   Ordinal: `OverallQual`, `ExterQual`, `KitchenQual`

`OverallQual` is stored numerically but represents an ordered quality
scale. The quality levels for `ExterQual` and `KitchenQual` are ordered
as `Po < Fa < TA < Gd < Ex`.

### Descriptive statistics

Calculate mean, median, mode, standard deviation, variance, range,
interquartile range, skewness, and kurtosis for key numerical columns,
including `SalePrice`, `GrLivArea`, and `LotArea`.

### Visualizations

The project includes:

-   `SalePrice` histogram with KDE, boxplot, and log-transformed
    histogram
-   Sale-price boxplots grouped by `OverallQual` and `Neighborhood`
-   Countplots for `OverallQual` and `HouseStyle`
-   Scatter plots for `GrLivArea`, `TotalBsmtSF`, and `YearBuilt`
    against `SalePrice`
-   Pair plot of selected numerical features
-   Correlation heatmap
-   Outlier-focused boxplot and scatter plot
-   Final four-panel dashboard

### Data quality and missing values

Some missing values in this dataset mean that a feature is absent rather
than unknown. The project specifically checks `PoolQC`, `Alley`,
`Fence`, `FireplaceQu`, and `GarageType` for this situation. For
numerical columns with missing values, such as `LotFrontage`, consider
median imputation overall or grouped by `Neighborhood`.

Outliers should be inspected before deciding whether to remove them.
Keep unusual but valid sales and document any cleaning decisions.

## Expected Insights to Verify

These are hypotheses to investigate, not conclusions to assume:

-   `SalePrice` may be right-skewed; a log transformation may make its
    distribution closer to normal.
-   `OverallQual` and `GrLivArea` may be among the strongest correlates
    of sale price.
-   Sale price may rise with overall quality, with greater spread among
    higher-quality homes.
-   Some neighborhoods may have notably higher median prices.
-   Very large homes with low sale prices may be unusual sales that
    influence trends.
-   Many apparent missing values may indicate an absent feature and
    should not automatically be dropped.

## Running the Project

1.  Download the Ames Housing `train.csv` dataset from Kaggle's *House
    Prices: Advanced Regression Techniques* competition.
2.  Place `train.csv` in the project directory (or update the notebook's
    data path).
3.  Install the packages listed in `requirement.text`.
4.  Open the Jupyter Notebook and run the analysis cells in order.

## Notebook Practice

Use a Markdown cell before each code cell to explain what the code will
do, and a Markdown cell after it to record what was learned.

The final dashboard is saved as `eda_dashboard.png`.
