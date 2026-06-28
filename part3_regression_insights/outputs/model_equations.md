# Model Equations and Interpretations

## Dummy Variable Approach (Task 3)
To include categorical data in the regression models, we converted categorical variables into binary dummy variables (1 or 0). 

For this analysis, we focused on the **`store_type`** variable, which contains the following categories: [Mall, High Street, and Outlet].

To avoid multicollinearity (redundancy), we cannot include all categories in the model simultaneously. Therefore, one category must be omitted to serve as the baseline comparison. 
* **Variables created:** `type_[Mall]` and `type_[High Street]`
* **Reference Category:** `[Outlet]`

Because `[Outlet]` is the reference category, its value is implicitly captured when the other dummy variables are set to 0. Any regression coefficients for `type_[Mall]` or `type_[High Street]` will be interpreted in direct comparison to an `[Outlet]` store.

---
*Note: Regression equations and coefficient interpretations will be added below as the modeling phases are completed.*

# Model Equations and Interpretations

## Dummy Variable Approach (Task 3)
To include categorical data in the regression models, we converted categorical variables into binary dummy variables (1 or 0). 

For this analysis, we focused on the **`store_type`** variable. 

To avoid multicollinearity (the dummy variable trap), we cannot include all categories in the model simultaneously. Therefore, one category must be omitted to serve as the baseline comparison. 
* **Variables created:** `type_Mall`, `type_HighStreet`, `type_Outlet`, and `type_Airport`
* **Reference Category:** `residential`

Because `residential` is the reference category, its value is implicitly captured when all other dummy variables are set to 0. Any regression coefficients for the created store types will be interpreted as the expected difference in monthly sales compared directly to a `residential` store.

---
*Note: Regression equations and coefficient interpretations will be added below as the modeling phases are completed.*
