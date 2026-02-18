# Used Car Pricing Analysis

## Business Understanding

The objective of this analysis is to identify the characteristics that influence used car resale prices in the United States. By understanding which features are associated with higher or lower prices, dealerships can fine-tune their inventory acquisition and pricing strategies.

This project translates structured vehicle listing data into actionable insights for used car dealers looking to optimize margins and improve consistency in pricing decisions.

---

## Data Understanding

The dataset contains over 426,000 used vehicle listings. After deduplication using VIN, the dataset was reduced to approximately 118,000 unique vehicles to ensure each row represented a distinct car.

Key variables include:

- Price  
- Year  
- Manufacturer  
- Condition  
- Cylinders  
- Fuel type  
- Odometer  
- Title status  
- Transmission  
- Drive type  
- Vehicle type  
- Paint color  
- State  

Initial exploration revealed significant missingness in some variables (such as size), heavy right skew in price, and extreme outliers in both price and mileage. These integrity issues were addressed during the data preparation phase.

---

## Data Preparation

Several steps were taken to prepare the dataset for modeling:

- Removed duplicate vehicles using VIN  
- Dropped identifier columns to prevent leakage  
- Removed zero and negative prices  
- Trimmed extreme price and mileage outliers using percentile thresholds  
- Log-transformed price to stabilize variance  
- Engineered vehicle age from model year  
- Converted cylinders to numeric format  
- Removed high-cardinality variables such as model and region  
- Filled missing categorical values with "unknown" where appropriate  

The final modeling dataset contains approximately 102,000 vehicles and 14 predictive features.

---

## Modeling

Three regression models were evaluated:

- Linear Regression  
- Ridge Regression  
- Lasso Regression  

Five-fold cross validation was used to compare model performance. Ridge regression was selected as the final model due to slightly improved stability and generalization performance.

The selected Ridge model achieved:

- Cross-validated R² ≈ 0.319  
- Test R² ≈ 0.319  

This indicates the model explains approximately 32 percent of variation in log-transformed vehicle prices.

While the model captures meaningful structural drivers of value, much of vehicle price variation remains influenced by unobserved factors such as trim level, accident history, optional packages, dealer pricing strategies, and local demand conditions.

---

## Key Findings

### 1. Brand Matters

Certain manufacturers are associated with higher average resale prices in the dataset. Brands such as Tesla and Porsche command strong premiums, while others such as Fiat, Saturn, and Mitsubishi tend to be associated with lower resale values.

**Recommendation:** Prioritize acquisition of premium brands when budget allows, and avoid overpaying for historically lower-value brands.

---

### 2. Condition and Title Status Drive Price

Vehicle condition and title clarity are among the strongest drivers of resale price.

Vehicles with clean titles and those in new or excellent condition are associated with meaningful price premiums. Salvage titles, fair condition, or missing title information are associated with substantial discounts.

**Recommendation:** Focus on acquiring clean-title vehicles in good or better condition. Vehicles with salvage or unclear titles require disciplined pricing and deeper discounts.

---

### 3. Vehicle Type and Fuel Type Influence Demand

Pickup trucks and diesel-powered vehicles, particularly in truck segments, show notable price premiums relative to sedans and smaller vehicles.

**Recommendation:** Maintain strong representation in high-demand vehicle categories such as pickup trucks, especially in regions where demand supports it.

---

### 4. Age and Mileage Depreciation

Both vehicle age and mileage are negatively associated with price. Each additional year of age and increase in mileage reduces expected resale value in a consistent and measurable way.

**Recommendation:** Weigh age and mileage heavily when determining acquisition price, particularly for trade-ins and auction purchases.

---

## Evaluation

The Ridge regression model demonstrates stable performance across cross validation and test evaluation, indicating that the modeling process generalizes well to unseen data.

Although the model does not capture every nuance of vehicle pricing, it successfully identifies economically intuitive drivers of value. These findings provide a structured and data-driven foundation for improving inventory selection and pricing discipline.

---

## Deployment and Business Application

This analysis should be used as a pricing support tool rather than a replacement for dealership expertise.

Dealerships can use these insights to:

- Identify high-margin vehicle categories  
- Avoid overpaying for historically discounted brands  
- Quantify expected depreciation more consistently  
- Support more objective and standardized acquisition decisions  

By combining model-driven insights with local market knowledge and operational experience, dealerships can make more consistent, defensible, and ultimately more profitable inventory decisions.

---

## Final Recommendation

To fine-tune inventory strategy, dealerships should prioritize:

- Premium brands such as Tesla and Porsche  
- Clean-title vehicles  
- High-demand vehicle types such as pickup trucks  
- Lower age and mileage inventory  

At the same time, they should apply disciplined pricing and acquisition standards to salvage-title vehicles, high-mileage inventory, and historically lower-demand brands.

Used thoughtfully, this framework provides meaningful analytical support for strategic decision-making in the used vehicle marketplace.
