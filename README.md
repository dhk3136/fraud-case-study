# Case Study - Predicting Fraud  
### Daniel Kim  

![lead photo](img/fraud_case_study_dark_room.png)  

## Overview and Method  
Tasked with predicting fraud for an event-ticketing company:    
- Conducted a thorough EDA by analyzing data provided by the company  
  - Cleaned, processed the dataset, utilized feature engineering, generated plots  
- Implemented four models to obtain best performance metrics
- Applied techniques to understand and predict probabilities for fraudulent activity 
  - Set probability thresholds for fraud rather than simple binary classification  
- Developed a Flask app capable of taking in random data for prediction  

## Data
The full dataset is composed of over 14,000 events with various numerical and categorical features. Data leakage was a major concern, and rigorous analysis was used to prevent leakage. Class imbalance between fraud and non-fraud cases (9% vs 91%) may present issues in modeling.  

## Preview of Results: 4-model Comparison  
![img](img/model_comparison.png)  

## EDA  
In exploratory data analysis, the following features displayed a large amount of variance between fraud and non-fraud events.

![Analysis of Body Length on Fraud](img/Analysis_of_Body_Length_on_Fraud_boxplot.jpg)  

![img](img/Analysis_of_Event_Posting_boxplot.jpg)

![img](img/Analysis_of_Description_boxplot.jpg)

![img](img/Analysis_of_Event_Posting_boxplot.jpg)

![Analysis of Body Length on Fraud](img/Analysis_of_delivery_method_box.jpg)

These features, among others, were used for modeling. Along with rigorous feature engineering and the conversion to dummied categorial features, 228 features remained. After conversion to binary classification, these features were removed with little utility or viable relationships commensurate with the EDA.  

## Results  
Ultimately, the Random Forest classifier performed best for the fraud task. The boosted models, XGBoost and Gradient Boosting, also performed well and comparably to Random Forest. Naive Bayes Classification, on the other hand, lagged behind the others by a considerable amount. Ultimately, the choice to go with Random Forest was primarily one aimed at interpretability, drawing out feature importances, and with a consideration of audience and human readability.

![Model Comparison](img/recall_prec.png)

![Model Comparison](img/F_1.png)

![Model Comparison](img/model_comparison_roc_plot.jpg)

![img](img/feature_importance_Random_Forest_1.png)  

## Deployment
A flask app was deployed that uses live streaming data, makes fraud predictions, and logs predictions.

