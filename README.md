# Understanding the Drivers of Used Car Prices

## Executive Summary
I analyszed over 100,000 unique used vehicles to determine which characteristics most strongly influence resale price. Using multiple regression models and cross validation, I identified consistent pricing drivers across brands, vehicle types, and conditions. While vehicle prices are inherently noisy and influenced by many factor not capture in the initial dataset, the analysis reveals patterns that can help guide the inventory acquistion and pricing strategy for used car dealerships in the United States.

## Key Findings

#### 1. Brand Matters
Certain manufacturers command strong price premiums, even after controlling for age and mileage factors. These are high-value brands such as Tesla, Porshe, and diesel heavy manufacturers. Certain low-value brands also exist and should be taken into account, such as Fiat, Saturn, and Mitsubishi. I recommend that the acquisition of premium brands is prioritized when budget allows, while avoiding overpaying for historically lower-value brands such as those listed above.

#### 2. Condition and Title Status
Vehicle condition and title clarity are among the strongest factors in pricing. A clean title, and new or excellent condition drive a price premium, while a salvage title, fair condition, or missing or uncertain title status drive price discounts. I recommend that inventory acquisition is focused on clean-title vehicles in good or better condition. Vehicles with salvage or an unclear title status will require substantial discounting to be competitive in the market.

#### 3. Vehicle Type
Pickup truck and deisel vehicles see notable price premiums relative to sedans and smaller vehicles. I recommend mainting a healthy share of pickup trucks in inventory, especially in regions where truck demand is notably strong.

#### 4. Age and Mileage Depreciation
BOth vehicle age and mileage significantly and negatively impact price. Each additional year of age and each increase in mileage lowers expected resale value. I recommend weighing age and mileage heavily in determining acquisition price.

### Model Performance and Reliability
The Ridge regression model explains approximately 32% of observed price variation. While that does not capture every nuance of pricing, the model consistently identifies major structural drivers of value. Cross validation and test results were consistent, indicating that the model generalizes well to unseen vehicles.

## Business Implications
This analysis provides a framework for:
- identifying high-margin vehicle categories
- avoiding overpayment for historically discounted brands
- quanitfying expected depreciation
- structuring data-drive acquisition decisions

This should be viewed as a pricing support tool rather than a wholesale replacement of expert judgement.

## Opportunities for Further Improvement
Further enhancements could include:
- Trim-level and package data
- Accident history
- Seasonal or regional demand adjustments
With richer data, predictive accuracy can likely improve.

###Final Recommendation
Dealerships can use these findings to fine-tune their inventory towards:
- Premium brands such as Tesla, Porsche
- Clean-Title vehicles
- High-demand vehicle types such as pickup trucks
- Lower age and mileage inventory

Combining these insights with market knowledge and local demand patterns, pricing and inventory decisions can become more consistent, defensible, and, ultimatley, more profitable.