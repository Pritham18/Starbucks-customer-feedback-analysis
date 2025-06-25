# Starbucks-customer-feedback-analysis
  Starbucks Survey Insights – Customer Feedback Analysis
STAT 515 Final Project – Team 14
📘 Project Overview
This project explores customer preferences and satisfaction patterns based on survey responses collected from Starbucks customers in Malaysia. Using statistical modeling and data analysis techniques, we investigate what factors influence customer loyalty, dining preferences, and the likelihood of using Starbucks for social or business meetings.

Our study combines descriptive analytics, logistic regression, and ordinal regression to derive actionable insights from survey data.

📊 Dataset Details
Source: Starbucks Customer Satisfactory Survey on GitHub

Sample Size: 122 respondents

Survey Period: October 1st – October 5th, 2019

Location: Starbucks stores in Malaysia

Survey Format: 20 multiple-choice and rating-based questions

Key Data Columns:
Age, Gender, Occupation, Membership status

Frequency of visit and purchase

Ambience, Wi-Fi, and Service ratings

Proximity to nearest outlet

Likelihood to revisit Starbucks

Preference for meetings/hangouts

🎯 Research Questions
How do students and employed individuals differ in their preference for Starbucks?

Does proximity to a Starbucks outlet influence a customer’s dining choice (dine-in, takeaway, drive-through)?

What are the key predictors of customer loyalty based on ambiance, price, Wi-Fi, and service quality?

Does the quality of service affect a customer’s likelihood of using Starbucks for meetings or hangouts?

🧰 Tools & Technologies Used
Tool	Purpose
R	Statistical analysis, regression modeling, data visualization
Excel	Data cleaning, column renaming, filtering duplicates
ggplot2	Creating stacked bar plots and predictive probability plots
R’s polr() function	Ordinal logistic regression analysis

📈 Key Analyses Performed
1. Descriptive Statistics & Bar Plots
Compared customer preferences by occupation: employed individuals showed the strongest preference for Starbucks.

Visualized customer behavior by outlet distance: nearby customers preferred takeout, while mid-distance customers chose dine-in.

2. Ordinal Logistic Regression
Target: Likelihood of choosing Starbucks for meetings or hangouts

Key Predictor: Level of service

Findings: A higher service rating significantly increased the probability of Starbucks being chosen for meetings (coefficient = 0.8948).

Model Fit: AIC = 279.83, Residual Deviance = 269.83

3. Logistic Regression on Loyalty
Target: Revisit Intention (Customer Loyalty)

Predictors: Ambiance, Service, Price, Promotions, Wi-Fi

Insights:

Ambiance, price, and promotion positively influenced loyalty.

Surprisingly, service and Wi-Fi had negative coefficients—suggesting high expectations in these areas might lead to disappointment if unmet.

📉 Model Evaluation
Logistic Regression Diagnostics revealed model limitations:

Residuals vs Fitted plot showed poor fit for lower-leverage observations.

Q-Q plot indicated deviations from normality in residuals.

Cook’s Distance highlighted high-influence outliers affecting model reliability.

Recommendation:
Future models should consider transforming predictors, applying regularization, or using ensemble models to better capture real-world complexity.

✅ Key Takeaways
Occupation matters: Employed customers show stronger Starbucks loyalty than students or self-employed individuals.

Location influences behavior: People near stores prefer quick takeout; those further out are more likely to dine in.

Service quality is essential: Strong predictor for using Starbucks as a social/business venue.

Loyalty drivers are nuanced: Good ambiance and fair pricing build loyalty, but overemphasis on service/Wi-Fi may lead to dissatisfaction.

📂 Repository Structure
bash
Copy
Edit
.
├── clean_survey_analysisnew.csv       # Cleaned dataset used for modeling
├── TEAM14_PPT.pptx                    # Presentation slides summarizing the analysis
├── STAT515-Group14-FinalProject.pdf   # Final project report
├── README.md                          # Project documentation (this file)
📚 References
Prasertcbs. (n.d.). Starbucks Satisfactory Survey Dataset. GitHub Repository:
https://github.com/prasertcbs/basic-dataset/blob/master/Starbucks%20satisfactory%20survey.csv

📌 How to Reproduce This Project
Download the dataset from the link above or use the provided cleaned CSV.

Use RStudio or any R environment.

Load the dataset and run:

r
Copy
Edit
library(MASS)
model <- polr(as.factor(MeetingChoice) ~ Service + SituationalFactors, data = dataset)
summary(model)
Recreate visualizations using ggplot2.

