# Diamond Prices Analysis (2022)

## Overview

This project explores and models the pricing of diamonds using the
**Diamonds Prices 2022** dataset. The analysis applies exploratory data
analysis (EDA), correlation checks, and multiple linear regression to
understand how characteristics such as **carat, cut, color, clarity, and
physical dimensions** affect diamond prices.

The main goal is to build predictive models for diamond prices, validate
assumptions of linear regression, and interpret the influence of
different predictors on price.

------------------------------------------------------------------------

## Dataset

-   **Source**: Diamonds Prices 2022 (`Diamonds Prices2022.csv`)
-   **Size**: \~53,000 observations, 10+ variables
-   **Variables include**:
    -   **Carat**: Weight of the diamond\
    -   **Cut**: Quality of the cut (Fair, Good, Very Good, Premium,
        Ideal)
    -   **Color**: Diamond color grading (D--J)
    -   **Clarity**: Purity levels (I1 to IF)
    -   **Depth, Table**: Proportions (%)
    -   **x, y, z**: Physical dimensions (mm)
    -   **Price**: Price in USD

------------------------------------------------------------------------

## Methods

1.  **Data Sampling**: Selected a random sample of 1,000 diamonds.
2.  **Exploratory Data Analysis**:
    -   Histograms for continuous variables (carat, depth, table, price,
        dimensions).
    -   Bar plots for categorical variables (cut, color, clarity).
    -   Correlation analysis among continuous variables.
3.  **Modeling**:
    -   Simple Linear Regression (price \~ carat).
    -   Log-transformed regression to correct heteroskedasticity.
    -   Multiple Linear Regression including cut, color, clarity, and
        dimensions.
    -   Stepwise model selection using **AIC**.
    -   Variance Inflation Factor (VIF) to detect multicollinearity.
4.  **Validation**:
    -   Checked regression assumptions (normality, linearity,
        homoscedasticity).
    -   Generated prediction and confidence intervals.

------------------------------------------------------------------------

## Key Findings

-   **Carat weight** is the strongest driver of price, with an
    exponential (power-law) relationship.
-   **Cut, color, and clarity** add meaningful premiums; clarity can add
    \~\$4,800 from lowest to highest grade.
-   **Size dimensions (x, y, z)** are highly correlated and add little
    once carat is included.
-   Best-performing model (log--log regression with categorical
    predictors) achieved:
    -   **Adjusted R² ≈ 0.983**
    -   Low residual error
    -   Minimal multicollinearity

------------------------------------------------------------------------

## Installation & Requirements

The project is written in **R**. To run the analysis, install the
following packages:

``` r
install.packages(c("tidyverse", "car"))
```

Clone/download this repo, then open and run `Final Project.Rmd` in
RStudio.

------------------------------------------------------------------------

## Usage

1.  Place `Diamonds Prices2022.csv` in your working directory.
2.  Open `Final Project.Rmd` in RStudio.
3.  Run all chunks to reproduce:
    -   Data exploration
    -   Model building
    -   Results and visualizations

------------------------------------------------------------------------

## Example Result

Prediction for a diamond with:
- **Carat = 0.81**
- **Cut = Very Good**
- **Color = J**
- **Clarity = VVS2**
- **x ≈ 5.76 mm**

→ **Estimated Price: \$2,220 -- \$3,740 (95% PI)**

------------------------------------------------------------------------

## Deliverables

-   `Final Project.Rmd` --- reproducible R Markdown with code &
    interpretations
-   `Final-Project.pdf` --- formatted final report
-   `Diamonds Prices2022.csv` --- dataset

------------------------------------------------------------------------

## License

This project is for educational purposes. No commercial license is
attached.
