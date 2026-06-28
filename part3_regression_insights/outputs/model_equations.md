# Dummy Variable Approach (Task 3)
To include categorical data in the regression models, we converted categorical variables into binary dummy variables (1 or 0). 

For this analysis, we focused on the **`store_type`** variable. 

To avoid multicollinearity (the dummy variable trap), we cannot include all categories in the model simultaneously. Therefore, one category must be omitted to serve as the baseline comparison. 
* **Variables created:** `type_Mall`, `type_HighStreet`, and `type_Airport`
* **Reference Category:** `residential`

Because `residential` is the reference category, its value is implicitly captured when all other dummy variables are set to 0. Any regression coefficients for the created store types will be interpreted as the expected difference in monthly sales compared directly to a `residential` store.

---
*Note: Regression equations and coefficient interpretations will be added below as the modeling phases are completed.*

# Simple Regression Models (Task 4)

## Model 1: Marketing Spend
* **Dependent Variable:** `monthly_sales`
* **Independent Variable:** `marketing_spend`

**1. Regression Equation:**
Monthly Sales = 51240.23 + (15.66 * marketing_spend)

**2. R-squared:** 0.6681
*(This means that 66.81% of the variance in monthly sales is explained by marketing spend).*

**3. Coefficient:** 15.66

**4. P-value:** 2.15E-240 (Effectively 0.000)

**5. Business Interpretation:**
For every additional unit ($1) spent on marketing, monthly sales are expected to increase by $15.66, assuming all other factors remain constant. 

**6. Is the variable useful?**
Yes, this variable appears highly useful because the p-value is practically zero, which is well below the standard 0.05 threshold of statistical significance.

---

## Model 2: Footfall
* **Dependent Variable:** `monthly_sales`
* **Independent Variable:** `footfall`

**1. Regression Equation:**
Monthly Sales = 11520.15 + (21.06 * footfall)

**2. R-squared:** 0.7548
*(This means that 75.48% of the variance in monthly sales is explained by footfall).*

**3. Coefficient:** 21.06

**4. P-value:** 1.13E-306 (Effectively 0.000)

**5. Business Interpretation:**
For every additional customer visiting the store (footfall), monthly sales are expected to increase by $21.06, assuming all other factors remain constant.

**6. Is the variable useful?**
Yes, this variable appears highly useful because the p-value is practically zero, well below the standard 0.05 threshold of statistical significance.

# Multiple Regression Model (Task 5)

### Model 3: Combined Business Drivers
* **Dependent Variable:** `monthly_sales`
* **Independent Variables:** `marketing_spend`, `footfall`, `avg_discount_pct`, `type_Mall`, `type_HighStreet`, `type_Airport`

**1. Multiple Regression Equation:**
Monthly Sales = 39818.07 + (9.88 * marketing_spend) + (15.66 * footfall) - (15494.70 * avg_discount_pct) + (630.99 * type_Mall) - (1061.74 * type_HighStreet) + (18649.34 * type_Airport)

**2. R-squared:** 0.9721
*(This means an impressive 97.21% of the variance in monthly sales is explained by this combination of variables).*

**3. Intercept Interpretation:**
$39,818.07 is the expected monthly sales if all other variables were zero (zero marketing spend, zero footfall, zero discounts) and the store was our reference category (Residential).

**4. Business Meaning & Direction of Coefficients:**
* **`marketing_spend` (+9.88, P-value = 3.64E-51):** Strong positive relationship. Every additional $1 spent on marketing yields $9.88 in sales.
* **`footfall` (+15.66, P-value = 2.44E-120):** Strong positive relationship. Every additional customer visit yields $15.66 in sales.
* **`avg_discount_pct` (-15494.70, P-value = 1.37E-13):** Strong negative relationship. Assuming discounts are entered as decimals (e.g., 10% = 0.10), a 1% increase in average discount decreases monthly sales by $154.95. While discounts may drive some volume, they heavily eat into overall sales revenue.

**5. Dummy Variable Interpretation (Compared to `Residential`):**
* **`type_Airport` (+18649.34, P-value = 1.25E-103):** Airport stores generate $18,649.34 more in monthly sales than Residential stores. This is a highly significant positive driver.
* **`type_HighStreet` (-1061.74, P-value = 0.0016):** High Street stores generate $1,061.74 less in monthly sales than Residential stores. 

**6. Statistically Weak Variables:**
* **`type_Mall` (+630.99, P-value = 0.0527):** This variable is statistically weak because its p-value is slightly above the standard 0.05 threshold. While Mall stores appear to generate slightly more sales than Residential stores, the evidence is not statistically definitive enough to make firm business decisions on this specific comparison.


# Comprehensive Model Equations and Interpretations (Task 8)

This document details the mathematical equations for all regression models tested, providing clear business interpretations for each variable and justifying the final model selection for leadership.

## Part 1: Simple Regression Models

### Model 1: Marketing Spend
* **Equation:** `Monthly Sales = 51240.23 + (15.66 * marketing_spend)`
* **Business Interpretation:** This baseline model establishes that marketing is a positive driver of revenue. The intercept of $51,240.23 represents the theoretical sales a store would generate if marketing spend was exactly zero. The coefficient of 15.66 means that for every single additional dollar ($1) allocated to a store's marketing budget, we expect monthly sales to increase by $15.66. This suggests a very healthy return on advertising spend (ROAS) when looked at in isolation.

### Model 2: Footfall (Customer Traffic)
* **Equation:** `Monthly Sales = 11520.15 + (21.06 * footfall)`
* **Business Interpretation:** This model confirms that raw customer volume is a massive revenue driver. The intercept of $11,520.15 is the theoretical sales floor. The coefficient of 21.06 means that for every additional customer who physically walks into the store, monthly sales increase by approximately $21.06. This metric essentially acts as our average revenue per visitor.

---

## Part 2: Multiple Regression Model

### Model 3: Combined Business Drivers (Multiple Regression)
* **Equation:** `Monthly Sales = 39818.07 + (9.88 * marketing_spend) + (15.66 * footfall) - (15494.70 * avg_discount_pct) + (630.99 * type_Mall) - (1061.74 * type_HighStreet) + (18649.34 * type_Airport)`

### Business Interpretation of Numerical Coefficients
In a multiple regression environment, coefficients explain the impact of a variable *assuming all other factors are held perfectly constant*.
* **Marketing Spend (+9.88):** When controlling for footfall and store type, the true impact of marketing drops slightly to $9.88 per dollar spent. This is still a highly profitable return, indicating marketing budgets should be maintained or scaled.
* **Footfall (+15.66):** The true value of a single store visitor, when accounting for other factors, is $15.66. Operations teams must prioritize strategies that draw physical traffic.
* **Average Discount Percentage (-15494.70):** This is a critical warning sign for leadership. The severe negative coefficient indicates that heavy discounting destroys revenue. Specifically, a 1% increase in the average discount rate (e.g., from 10% to 11%) actively reduces monthly sales by roughly $154.95. While discounts might artificially inflate footfall, they are fundamentally toxic to the overall top-line sales figures.

### Explanation of Dummy Variables and Reference Category
To include categorical "Store Type" data in our math, we used a dummy variable strategy (converting text to 1s and 0s). 
* **Reference Category:** We selected **`Residential`** stores as our baseline reference category. Therefore, there is no specific variable for Residential in the equation. Instead, the performance of Mall, High Street, and Airport stores is mathematically compared directly against how a Residential store performs.
* **`type_Airport` (+18,649.34):** Airport locations are our strongest performers. Simply being located in an airport generates $18,649.34 more in monthly sales compared to a Residential store, assuming footfall and marketing are equal.
* **`type_HighStreet` (-1,061.74):** High Street locations slightly underperform. They generate $1,061.74 less in monthly sales than a standard Residential store.
* **`type_Mall` (+630.99):** Mall stores generate about $631 more than Residential stores. However, this variable has a p-value of 0.0527, which sits slightly above the standard threshold for statistical significance. Therefore, leadership should not make major strategic real estate decisions based on this specific metric alone.

---

## Part 3: Final Model Selection

**Final Model Selected:** Model 3 (Multiple Regression)

**Reasoning for Selection:** Model 3 is unequivocally the superior tool for executive decision-making. 
1. **Explanatory Power:** It yields an R-squared of 97.21%, meaning it successfully explains nearly all the mathematical variance in our monthly sales, compared to the 66% and 75% generated by our simple models.
2. **Contextual Accuracy:** Simple regressions suffer from "omitted variable bias." For example, Model 1 suggested marketing yields $15.66 per dollar. However, Model 3 revealed the true yield is $9.88, because Model 1 couldn't tell the difference between sales driven by marketing and sales driven by raw foot traffic. 
3. **Actionable Business Insights:** Model 3 allows leadership to pull isolated levers. It clearly identifies the danger of our current discounting strategy and highlights the massive premium of Airport real estate, insights that were completely invisible in the simple regression models.
