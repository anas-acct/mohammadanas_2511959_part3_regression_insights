# Retail Chain Sales Regression Analysis

## 1. Business Problem Summary
As a business analyst for the retail chain, the objective of this project is to understand the key factors driving monthly sales performance across our stores. The leadership team is considering several business actions, including:
* Increasing marketing spend
* Improving inventory availability
* Changing discounting strategies
* Reallocating staff
* Prioritizing specific store types or regions

This analysis uses regression modeling to identify which of these factors are most strongly associated with monthly sales to provide data-backed business recommendations.

## 2. Dataset Understanding (Task 1)
The data provided for this analysis includes a primary dataset (`store_performance.csv`) and a supporting dictionary (`data_dictionary.csv`). After reviewing the dataset, the variables have been categorized as follows:

### Dependent Variable
* **`monthly_sales`**: This is the target variable we are attempting to predict and understand.

### Potential Independent Variables
These are the factors that may influence our sales performance:
* **`marketing_spend`**: The amount of money invested in marketing per store.
* **`footfall`**: The volume of customer traffic at the store.
* **`avg_discount_pct`**: The average percentage of discounts applied to merchandise.
* **`inventory_availability_pct`**: The percentage of inventory consistently available on shelves.
* **`customer_rating`**: The average satisfaction score provided by customers.

### Variable Types in the Dataset
**Numerical Variables:**
* `monthly_sales`
* `marketing_spend`
* `footfall`
* `avg_discount_pct`
* `inventory_availability_pct`
* `customer_rating`

**Categorical Variables:**
* **`region`**: The geographic location of the store.
* **`store_type`**: The classification or format of the store.

### Data Preparation & Cleaning Strategy
**Variables Requiring Transformation:**
* The categorical variables (`region` and `store_type`) cannot be used in their raw text format for regression analysis.
* They will be converted into dummy variables (0 or 1).
* To avoid multicollinearity (the "dummy variable trap" / redundancy), one category from each variable will be dropped and used as the reference category.

**Variables Not Useful for Regression:**
* **`store_id`** (or equivalent identifier): Unique identifiers hold no predictive mathematical value and will be excluded from the regression models.

---
*Note: The sections below will be completed as the analysis progresses through the final tasks.*

## 3. Regression Approach & Dummy Variable Strategy
[To be completed]

## 4. Model Comparison & Final Model Selection
[To be completed]

## 5. Assumptions, Limitations, & Residual Analysis
[To be completed]

## 6. Business Recommendation
[To be completed]
