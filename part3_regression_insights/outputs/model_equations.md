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
**5. Business Interpretation:**
For every additional customer visiting the store (footfall), monthly sales are expected to change by [Insert Coefficient amount], assuming all other factors remain constant.

**6. Is the variable useful?**
[If the P-value is less than 0.05, write: "Yes, this variable appears highly useful because the p-value is below the standard 0.05 threshold of statistical significance." If it is above 0.05, write: "No, this variable does not appear statistically useful as a standalone predictor because the p-value is above 0.05."]
