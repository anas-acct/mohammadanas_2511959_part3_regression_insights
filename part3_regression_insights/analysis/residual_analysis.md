# Residual Analysis (Task 7)

## 1. Top 5 Positive Residuals (Overperforming Stores)
Positive residuals occur when a store's actual sales are *higher* than what our regression model predicted. These stores are overperforming expectations.

| Store ID | Actual vs Predicted Difference (Residual) | Store Type |
| :--- | :--- | :--- |
| STR-1024 | +$380,171.69 | Residential |
| STR-1068 | +$339,237.47 | Mall |
| STR-1055 | +$314,069.92 | Airport |
| STR-1045 | +$313,385.17 | Airport |
| STR-1077 | +$307,926.85 | Residential |

## 2. Top 5 Negative Residuals (Underperforming Stores)
Negative residuals occur when a store's actual sales are *lower* than what our regression model predicted. These stores are falling short of their mathematical potential.

| Store ID | Actual vs Predicted Difference (Residual) | Store Type |
| :--- | :--- | :--- |
| STR-1007 | -$1,081,090.00 | Mall |
| STR-1023 | -$896,057.80 | Mall |
| STR-1012 | -$895,883.90 | Residential |
| STR-1015 | -$676,873.50 | Airport |
| STR-1058 | -$428,729.90 | High Street |

## 3. Business Meaning of Residuals
In business terms, residuals represent the "unexplained variance"—the human element of retail that a math equation cannot see. 
* **Positive Residuals** point to best practices. A store beating its prediction by $380k might have an exceptional store manager, highly tenured staff, a superior local layout, or a localized event driving unrecorded purchasing behavior. Leadership should audit these stores to learn from them.
* **Negative Residuals** point to operational failures or local headwinds. A store missing its prediction by $1M has all the right ingredients (high footfall, high marketing) but is failing to convert. This suggests issues like poor customer service, severe stockouts of popular items, or aggressive local competition.

## 4. Model Predictive Tendencies
Looking at the extreme residuals, there are signs that the model may be systematically over-predicting certain stores. Specifically, we see massive negative residuals for Mall stores (e.g., STR-1007 missing by over $1M). 

This suggests that our linear model assumes footfall in Malls scales infinitely with sales. In reality, Mall footfall might include a high volume of "window shoppers" or teenagers who do not make purchases. The model fails to capture this conversion-rate ceiling, resulting in aggressive over-predictions for high-traffic mall locations.
