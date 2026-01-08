<img width="1790" height="1037" alt="Screenshot 2026-01-08 at 9 53 15 AM" src="https://github.com/user-attachments/assets/ebedab2d-7096-4b76-9e76-5f8ff55c7bc4" />

# Hospital Readmission Risk Prediction Analysis

### Overiew
This project explores historical hospital encounter data to identify patterns associated with30-day hospital readmissions. The goal was to build an end-to-end predicttive analystics project by cleaning raw healthcare data, training a classification model, and visualizing population-level insights on an interactive Tableau dashboard.

The dashboard is not intended for clinical decision making or patient level diagnosis, but rather for operational planning and high-level risk monitoring.

### What I Aimed to Learn
This project helped me better understand:
- Working with large datasets
- Preparing data for binary classification
- Handling class imbalance and threshold trade-offs
- Evaluating models beyond accuracy using recall and precision
- Translating predictive model outputs into clear, responsible visualizations
- BUilding dashboards that explain model behavior and risk patterns

### Business Questions Answered
Some of the key analytical questions answered in this project include:
- How does the estimated readmission risk vary by age group?
- Does the estimated readmission risk vary by gender?
- How does length of hospital stay relate to readmission risk?
- What percentage of patients are at high risk of readmission?
- Are patients who use diabetes medications associated with higher predicted risk?
- How well does the model perform at identifying readmissions?

### The Data
Source: [Diabetes 130-US Hospitals for Years 1999-2008](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008)
Domain: Healthcare/hospital operations

Each row represents a hospital encounter and includes information such as:
- Age group
- Gender
- Time in hospital
- Diabetes medication indicator
- Readmission outcome

### Data Cleaning
I prepared the raw data for analysis and modeling, by:
- Removing invalid and inconsistent values
- Handling missing and unknown categories
- Encoding categorical variables for modeling
- Converting the readmission outcome into binary target variable
- Ensuring numeric fields were correctly typed
- Creating a clean, dataset for analysis and visualization

The cleaned and encoded dataset was saved for use in modelling and Tableau but excluded from version control due to it's large file size

### Feature Engineering
I created and refined featured to support predictive modelling and analysis, such as:
- Readmitting Binary Flag:
    -  1 = Readmitted within 30 days
    -  0 = Not readmitted within 30 days
- Encoding demographic and clinical indicators
- Standardizing inputs for model training

### Predictive Modeling
Multiple classification models were trained and evaluated to estimate the probability of a 30-day hospital readmission.

Logistic regression was used as a baseline model to establish interpretability and performance expectations while a random forest model was then trained to show on-linear relationships and interactions between patient characteristica and hospital stay features.

### Model Precision Metrics
Because readmissions are a rare event, evaluation focused on multiple metrics:
- Accuracy : 81.69%
- Recall: 30.52%
- Precision: 24.38%

### Tableau Dashboard
The [Tableau dashboard](https://public.tableau.com/app/profile/temilola.afolabi/viz/HospitalReadmissionRiskDashboardPredictiveAnalytics/HospitalReadmissionDashboard) was used to visualize readmission probabilities generated from the predictive models. The displayed insights include:
- Average predicted readmission risk across encounters
- Comparison between predicted risk and observed readmission rate
- Proportion of encounters classified as high risk based on probability thresholds
- Estimated readmission risk by age group and gender
- Relationship between length of hospital stay and predicted risk
- Risk differences associated with diabetes medication indicators
- Summary of model performance metrics

### Tools Used
- Python(pandas, numpy, scikit-learn)
- Machine Learning(Logistic Regression, Random Forest)
- Jupyter Notebook
- Tableau
- Git & Github

### Project Insights
The analysis found that hospital readmission risk is not evenly distributed among patient groups. The estimated risk varies by age group and increases with longer hospital stays, implying that length of stay could be an important operational risk indicator.

On average, patients who use diabetes medications have a higher anticipated risk, which is most likely due to increased care complexity rather than drug effects. Gender variations in estimated risk are low, indicating that risk is fairly similar across genders in this data set.

When working with uneven healthcare data, model evaluation emphasizes the relevance of recall and precision above accuracy alone. While overall accuracy is excellent, the model only captures a subset of genuine readmissions, a typical issue in predictive healthcare analytics.

### Possible Next Steps
- Tune classification thresholds more formally
- Add fairness and bias evaluation across demographic groups
- Incorporate time-based validation
- Automate data refresh and dashboard updates
- Explore cost-sensitive evaluation metrics


 
