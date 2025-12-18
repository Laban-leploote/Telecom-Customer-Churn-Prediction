

## TELECOM CUSTOMER CHURN PREDICTION
You can’t build a profitable future on a revolving door of customers, yet this is the reality facing many telecommunications companies like SyriaTel. Every month, a significant segment of the subscriber base decides to cease service, walking away with their future revenue and inflating the company’s costs.This project analyzes the syriatel dataset to predict customers who will churn from the telecommunication company.
## BACKGROUND
The background of this study is rooted in a critical challenge facing the modern telecommunications industry: Customer Churn. For a company like SyriaTel, the ability to predict which customers are likely to cancel their service is not just a technical goal, but a fundamental requirement for financial stability and growth.
## OBJECTIVES
This study aims to solve the churn problem through three primary pillars:

Predictive Modeling: Developing a high-accuracy model (like Random Forest) to classify potential churners.

Feature Identification: Determining the top drivers (e.g., total day minutes, service calls) so management knows exactly why customers are leaving.

Strategic Intervention: Providing data-backed recommendations on how to deploy retention budgets effectively to maximize Return on Investment (ROI).

## STAKEHOLDERS
1. Chief Marketing Officer and Retention Team
2. Chief Financial Officer
3. Customer Service Department Head
4. Product and Service Department Team

## DATA SOURCE
The dataset was sourced from Kaggle and it contains 3,333 customer records with 21 attributes.
 Target Variable: churn(14.5% churn rate).
 Key challenge: There was significant class imbalance that was addressed using SMOTE to ensure the model learnt the patterns of the minority class.

 ## KEY FEATURES
1. Customer Service Calls
Insight: This is the most actionable predictor. Every call to customer service increases the probability of churn. Our data suggests that after the 3rd call, a customer enters a "high-risk" zone.
2. Total Day Minutes
Insight: Total Day Minutes is the #1 predictor. Interestingly, it’s not just the dissatisfied customers leaving; it’s the heavy users. These are likely high-revenue customers who are being targeted by competitors with "unlimited" or "volume-discounted" day plans.
3. International Plan & Intl Minutes
Insight: Customers with an International Plan churn at a significantly higher rate than those without. This suggests a "Value Gap"—the current plan may be too expensive, or the rates for international minutes aren't competitive enough for people who actually use them.
4. Account Length
Insight: The model identifies account length as a key factor. This implies there are specific periods in a customer’s tenure (e.g., the 1-year mark) where they are more likely to re-evaluate their contract.
5. Evening & Night Minutes
Insight: While Day minutes are most critical, Evening and Night usage also rank in the top 10. Churn is rarely caused by one thing; it’s a cumulative shift in behavior.


