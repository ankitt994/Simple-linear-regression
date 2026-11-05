# Simple Linear Regression: Radio Promotion Budget vs. Sales

## Project Overview

This project uses **Simple Linear Regression** to examine the relationship between a company's radio promotion budget and the sales generated from its marketing campaigns.

The analysis focuses on one business question:

> Is there a statistically significant relationship between the amount spent on radio promotion and sales?

The goal is to understand the direction and strength of this relationship and assess whether radio promotion budget can be used as a predictor of sales.

## Business Context

The dataset contains information about marketing campaigns across different channels, including TV, radio, and social media. It also includes the type of influencer involved in a campaign and the resulting sales.

For this analysis, the **Radio** promotion budget is used as the independent variable (`X`), while **Sales** is the dependent variable (`Y`).

## Tools & Libraries

- Python
- Pandas – data loading and preparation
- Matplotlib – data visualization
- Seaborn – exploratory analysis and regression plots
- Statsmodels – Ordinary Least Squares (OLS) regression

## Project Workflow

1. **Data loading and exploration**
   - Loaded the marketing sales dataset using Pandas.
   - Reviewed the dataset structure and variables.
   - Checked for missing values and removed rows containing missing data.

2. **Exploratory Data Analysis**
   - Used pair plots to explore relationships between variables.
   - Examined the relationship between Radio promotion budget and Sales.
   - Observed a positive, approximately linear association.

3. **Model building**
   - Selected the `Radio` and `Sales` columns.
   - Defined the regression formula: `Sales ~ Radio`.
   - Built and fitted a Simple Linear Regression model using Statsmodels OLS.

4. **Model evaluation and assumption checks**
   - Reviewed the OLS regression summary.
   - Examined the regression line and scatter plot.
   - Checked residual normality using a histogram and Q-Q plot.
   - Examined residuals against fitted values to assess patterns and homoscedasticity.

## Key Results

The fitted regression model produced the following coefficients:

| Measure | Result |
|---|---:|
| Intercept | 41.5326 |
| Slope (Radio coefficient) | 8.1733 |
| 95% confidence interval for slope | 7.791 to 8.555 |
| p-value | 0.000 (rounded in the model output) |

### Regression Equation

```
Predicted Sales = 41.5326 + (8.1733 × Radio Promotion Budget)
```

### Interpretation

The positive slope indicates that Radio promotion budget and Sales move in the same direction in this dataset.

Based on the fitted model, a one-unit increase in Radio promotion budget is associated with an estimated **8.1733-unit increase in Sales**, on average.

The notebook interprets the budget and sales values in millions of dollars. Therefore, under that unit interpretation, an additional $1 million in radio promotion budget is associated with an estimated $8.1733 million increase in sales.

The reported p-value is rounded to 0.000, indicating a very small p-value (below 0.001 at the displayed precision). This provides evidence against the null hypothesis that the regression slope is zero. The 95% confidence interval for the slope (7.791 to 8.555) is also entirely positive.

## Linear Regression Assumptions

The notebook explores the following assumptions using visual diagnostics:

- **Linearity:** Pair plots and the regression plot are used to assess whether the relationship between Radio and Sales is approximately linear.
- **Normality of residuals:** A residual histogram and Q-Q plot are used to assess whether residuals are approximately normally distributed.
- **Homoscedasticity:** A residuals-versus-fitted-values plot is used to check whether residual spread is reasonably consistent.
- **Independence of observations:** The residual plot is inspected for visible patterns. A residual plot alone cannot conclusively establish independence; this also depends on how the data was collected.

Based on the visual checks documented in the notebook, the assumptions appear reasonably supported for this analysis.

## Repository Contents

- `Simple linear regression.ipynb` – Jupyter Notebook containing the analysis, code, visualizations, model output, and interpretation.
- `README.md` – Project overview, methodology, and key findings.

## How to Run the Notebook

1. Clone or download this repository.
2. Install the required Python libraries:

   ```bash
   pip install pandas matplotlib seaborn statsmodels jupyter
   ```

3. Make sure the dataset file, `marketing_sales_data.csv`, is available on your computer.
4. Update the CSV file path in the notebook to match its location.
5. Open and run the notebook in Jupyter Notebook or JupyterLab.

**Note:** The notebook currently references a local Windows file path. The dataset is not documented as part of this repository, so you will need access to the CSV file separately.

## Conclusion

This project demonstrates how Simple Linear Regression can be used to investigate a business relationship, estimate a regression equation, interpret coefficients, evaluate statistical significance, and check key model assumptions.

The analysis finds a statistically significant positive association between Radio promotion budget and Sales in the dataset. However, **association does not establish causation**. Other factors—such as TV and social media spending, influencer type, industry, and campaign characteristics—may also affect sales. Further analysis using multiple regression and additional data would be useful before making budget-allocation decisions.

## Learning Source

This project was completed as part of the **Google Advanced Data Analytics Professional Certificate** learning journey on Coursera, in a guided lab focused on Simple Linear Regression.
