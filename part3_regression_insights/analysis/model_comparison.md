# Regression Model Comparison (Task 6)

## 1. Model 1: Marketing Spend
* **Variables used:** Dependent: `monthly_sales` | Independent: `marketing_spend`
* **R-squared:** 0.6681 (Explains ~66.8% of the variance in sales)
* **Significant variables:** `marketing_spend` (p-value: 2.15E-240)
* **Business usefulness:** While this model proves that marketing spend is a positive driver of sales, it is too simplistic for executive decision-making. It ignores other massive drivers like foot traffic and discounts, leading to potential tunnel vision if leadership only looks at marketing.

## 2. Model 2: Footfall
* **Variables used:** Dependent: `monthly_sales` | Independent: `footfall`
* **R-squared:** 0.7548 (Explains ~75.5% of the variance in sales)
* **Significant variables:** `footfall` (p-value: 1.13E-306)
* **Business usefulness:** This model is slightly more useful than Model 1, as footfall naturally drives more revenue than marketing alone. However, it still fails to capture the full picture of store operations. It tells us that foot traffic matters, but doesn't tell us how our discounting strategy or store formats impact the bottom line.

## 3. Model 3: Multiple Regression (Combined Drivers)
* **Variables used:** Dependent: `monthly_sales` | Independent: `marketing_spend`, `footfall`, `avg_discount_pct`, `type_Mall`, `type_HighStreet`, `type_Airport`
* **R-squared:** 0.9721 (Explains ~97.2% of the variance in sales)
* **Significant variables:** `marketing_spend`, `footfall`, `avg_discount_pct`, `type_Airport`, `type_HighStreet`
* **Business usefulness:** This is a highly useful model for strategic decision-making. By controlling for multiple variables simultaneously, leadership can see the isolated impact of each lever. For example, it clearly highlights the severe negative impact of heavy discounting, even when footfall and marketing are high. It also proves that Airport locations drastically outperform all other formats.

## 4. Overall Model Limitations
While Model 3 is highly accurate mathematically, leadership must be aware of the following limitations:
* **Missing External Factors:** The model does not capture macroeconomic conditions, seasonality (like holiday spikes), local competitor actions, or inventory quality.
* **Correlation vs. Causation:** The model proves strong statistical associations, but it cannot definitively prove causation. For instance, we know marketing spend is associated with higher sales, but there may be a point of diminishing returns that a linear model cannot easily visualize. 
* **Reference Category Baseline:** The store type impacts are specifically measured against "Residential" stores. If the retail chain exits the residential market, the baseline changes entirely.
