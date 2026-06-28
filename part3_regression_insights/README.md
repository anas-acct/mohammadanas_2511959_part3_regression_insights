# Retail Chain Sales Regression Analysis

## 1. Business Problem Summary
[cite_start]As a business analyst for the retail chain, the objective of this project is to understand the key factors driving monthly sales performance across our stores[cite: 3, 4]. The leadership team is considering several business actions, including:
* [cite_start]Increasing marketing spend [cite: 5]
* [cite_start]Improving inventory availability [cite: 5]
* [cite_start]Changing discounting strategies [cite: 5]
* [cite_start]Reallocating staff [cite: 5]
* [cite_start]Prioritizing specific store types or regions [cite: 5]

[cite_start]This analysis uses regression modeling to identify which of these factors are most strongly associated with monthly sales to provide data-backed business recommendations[cite: 6].

## 2. Dataset Understanding (Task 1)
The data provided for this analysis includes a primary dataset (`store_performance.csv`) and a supporting dictionary (`data_dictionary.csv`). After reviewing the dataset, the variables have been categorized as follows:

### Dependent Variable
* [cite_start]**`monthly_sales`**: This is the target variable we are attempting to predict and understand[cite: 10, 41].

### Potential Independent Variables
[cite_start]These are the factors that may influence our sales performance[cite: 11]:
* [cite_start]**`marketing_spend`**: The amount of money invested in marketing per store[cite: 44].
* [cite_start]**`footfall`**: The volume of customer traffic at the store[cite: 45].
* [cite_start]**`avg_discount_pct`**: The average percentage of discounts applied to merchandise[cite: 46].
* [cite_start]**`inventory_availability_pct`**: The percentage of inventory consistently available on shelves[cite: 47].
* [cite_start]**`customer_rating`**: The average satisfaction score provided by customers[cite: 48].

### Variable Types in the Dataset
[cite_start]**Numerical Variables:** [cite: 12]
* `monthly_sales`
* `marketing_spend`
* `footfall`
* `avg_discount_pct`
* `inventory_availability_pct`
* `customer_rating`

**Categorical Variables:** [cite: 13]
* [cite_start]**`region`**: The geographic location of the store[cite: 33]. 
* [cite_start]**`store_type`**: The classification or format of the store[cite: 34].

### Data Preparation & Cleaning Strategy
[cite_start]**Variables Requiring Transformation:** [cite: 14]
* The categorical variables (`region` and `store_type`) cannot be used in their raw text format for regression analysis. 
* [cite_start]They will be converted into dummy variables (0 or 1)[cite: 31].
* [cite_start]To avoid multicollinearity (the "dummy variable trap" / redundancy), one category from each variable will be dropped and used as the reference category[cite: 37].

[cite_start]**Variables Not Useful for Regression:** [cite: 15]
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
