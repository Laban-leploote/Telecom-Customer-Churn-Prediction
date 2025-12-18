<img width="600" height="436" alt="image" src="https://github.com/user-attachments/assets/57b02ed5-8834-4104-967c-a90e64de8521" />
Author: Laban

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

## DATA PREPARATION
Feature Selection: Dropped phone number and redundant charge columns to prevent multicollinearity (minutes and charges were perfectly correlated).

Encoding: * Mapped "Yes/No" plans to 1/0.

Applied One-Hot Encoding to geographic data (State/Area Code).

Handling Imbalance: Since only 14.5% of customers churned, we used stratification during the train-test split to ensure the model learned from a representative sample.

Scaling: Applied StandardScaler to ensure features like "minutes" (high range) didn't overshadow "service calls" (low range).

## EDA 
Service Friction: Churn probability spikes dramatically after the 3rd customer service call. This is the primary indicator of a "breaking point."

The Usage Paradox: High-usage "Power Users" (specifically high daytime minutes) churn at a higher rate, likely seeking better unlimited deals from competitors.

Plan Mismatch: Customers with an International Plan are significantly more likely to leave, suggesting a perceived lack of value in that specific product.

Regional Variance: High-churn "hotspots" identified in states like NJ, CA, and TX.

## MODELLING
We reframed the business problem as a binary classification task. While we tested several algorithms, the Random Forest was chosen for its ability to handle non-linear relationships and provide clear feature importance.

Baseline: Logistic Regression (High recall, but too many false alarms).

Final Choice: Tuned Random Forest (Optimized via GridSearchCV for F1-Score).

## RESULTS
We tuned the models to find the optimal balance between catching churners (Recall) and ensuring we don't waste money on loyal customers (Precision).
Model,Test Accuracy,Precision,Recall,F1-Score,ROC-AUC
Tuned Random Forest,92.7%,80.0%,66.0%,0.72,0.89
Key Finding: Our final model catches 66% of all churners with 80% precision. This means that out of every 5 customers we flag as "at risk," 4 are truly planning to leave.

## LIMITATIONS
Static Data: The model uses a snapshot of usage; it does not capture real-time changes in competitor pricing or network outages.

Unstructured Data: We lack the text/audio of customer service calls, which could provide deeper sentiment insights.

Binary Scope: The model does not distinguish between "voluntary churn" (switching carriers) and "involuntary churn" (non-payment).

## INSIGHTS AND RECOMMENDATIONS
The 3-Call Alert: Automatically flag any customer who calls support a 3rd time for proactive outreach by a senior specialist.

High-Usage Retention: Offer "loyalty data bonuses" to high daytime users to prevent them from shopping for competitors.

International Plan Audit: Review the pricing of the International Plan; consider a "first 3 months free" or price-match strategy.

Threshold Deployment: * High Risk (Prob > 0.7): Direct phone call or high-value discount.

Medium Risk (Prob 0.4 - 0.7): Targeted email/SMS with a "Thank you" offer.

