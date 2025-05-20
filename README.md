# DS-Portfolio-Project

Medical Insurance Cost Analysis

Project Overview: 

The goal of this project is to understand what factors influence medical insurance premiums and to build a predictive model that can estimate insurance costs based on individual health indicators. By doing so, we aim to identify key drivers of premium pricing and improve cost prediction accuracy.

Evaluation Metrics:

We focused on the following metrics to evaluate our models:
Primary Metric: R-squared (R²), which shows how well our model explains the variability in insurance costs.
Secondary Metrics: Mean Absolute Error (MAE) and Mean Squared Error (MSE), which help gauge the accuracy of our predictions.

Workflow Summary:

A)Data Preprocessing:

Loaded the dataset (insurance.csv) with 986 records and 11 features.
No missing values were found.
Validated data types and adjusted premium prices for consistency.
Engineered a new BMI feature using height and weight.

B) Exploratory Data Analysis (EDA):

Visualized the distribution of each numerical feature.
Found a wide spread in PremiumPrice and Age; binary patterns in Diabetes and BloodPressureProblems.
Discovered moderate correlations between PremiumPrice and both Weight and Number of Major Surgeries.

C) Outlier Detection:

Used the IQR method to detect outliers in:
PremiumPrice: Outliers above $38,500
Weight: Below 37 kg or above 117 kg
Number of Major Surgeries: More than 2 surgeries
Takeaway: Handling or segmenting these outliers could improve model performance.

D) Hypothesis Testing:

ANOVA showed significant differences in premium prices based on the number of surgeries.

E) T-tests indicated:

Chronic diseases significantly impact premiums.
Cancer history has a moderate effect.

Machine Learning Models

Preprocessing:
1. Standardized numerical features and applied one-hot encoding to categorical ones.
2. Split data: 80% training, 20% testing.

Models & Performance:

Model       	MSE   	MAE	    R² Score
Linear Regression	12,221,661	2,586	0.713
Decision Tree	14,893,939	1,096	0.651
Random Forest	5,310,708	1,034	0.875
Gradient Boosting	6,166,949	1,502	0.855
Neural Network	577,411,808	23,238	-12.541

Best Model: The Random Forest Regressor outperformed others with an R² of 0.875, making it the most reliable model for prediction.

Deployment Plan

1. Developed a modular machine learning pipeline for preprocessing and model training.
2. Saved the trained Random Forest model using serialization.
3. Ready for deployment through a Flask or Streamlit web app.
4. Can be served via API or integrated into a UI for user interaction.

Key Insights & Recommendations

1. Weight and Number of Major Surgeries are strong predictors of insurance premiums.
2. Patients with chronic illnesses or a history of cancer are likely to face higher costs.

Recommendations:

1. Consider building separate models for different health groups (e.g., chronic vs. non-chronic conditions).
2. Apply feature capping or transformation techniques to deal with extreme values.
3. Incorporate additional features like income level, smoking habits, or geographic location to improve model accuracy further.
