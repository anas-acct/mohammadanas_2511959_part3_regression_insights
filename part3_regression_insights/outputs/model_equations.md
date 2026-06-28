## Dummy Variable Approach (Task 3)
To include categorical data in the regression models, we converted categorical variables into binary dummy variables (1 or 0). 

For this analysis, we focused on the **`store_type`** variable. 

To avoid multicollinearity (the dummy variable trap), we cannot include all categories in the model simultaneously. Therefore, one category must be omitted to serve as the baseline comparison. 
* **Variables created:** `type_Mall`, `type_HighStreet`, and `type_Airport`
* **Reference Category:** `residential`

Because `residential` is the reference category, its value is implicitly captured when all other dummy variables are set to 0. Any regression coefficients for the created store types will be interpreted as the expected difference in monthly sales compared directly to a `residential` store.

---
*Note: Regression equations and coefficient interpretations will be added below as the modeling phases are completed.*

## Simple Regression Models (Task 4)

### Model 1: Marketing Spend
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

### Model 2: Footfall
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

## Multiple Regression Model (Task 5)

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

