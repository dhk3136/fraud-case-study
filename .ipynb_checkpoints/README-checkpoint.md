# Case Study - Predicting Fraud  
- Jarred Bultema, Daniel Kim, Alyse Record, Peter Schmeiser  

### Method  
Tasked with predicting fraud for an event-ticketing company:    
- We conducted a thorough EDA by analyzing data provided by the company  
  - Cleaned the dataset, utilized feature engineering, generated plots  
- Experimented with several different models to obtain performance metrics
- Implemented steps to obtain probabilities for fraudulent activity 
  - Set probability thresholds for fraud rather than simple yes/no classification  
- Developed a Flask app capable of taking in random data for prediction

### Data
The full dataset is composed of over 14,000 events with various numerical and categorical features. Data leakage was a major concern, and rigorous analysis was used to prevent leakage. Class imbalance between fraud and non-fraud cases (9% vs 91%) may present issues in modeling.

In exploratory data analysis, we found the following features to show large variable between Fraud and non-Fraud events.

![Analysis of Body Length on Fraud](Analysis_of_Body_Length_on_Fraud_boxplot.jpg)  

![img](Analysis_of_Event_Posting_boxplot.jpg)

![img](Analysis_of_Description_boxplot.jpg)

![img](Analysis_of_Event_Posting_boxplot.jpg)

![Analysis of Body Length on Fraud](Analysis_of_delivery_method_box.jpg)

These features, among others, were used for modeling. After dummied categorial features, we were left with 228 features.


### Modeling   
Ultimately, the Random Forest classifier performed best for our task. We began with 43 features and concluded with 228. Using feature engineering, we converted all columns for binary classification, removing those with little utility or viable relationships according to our EDA.  

![Model Comparison](recall_prec.png)

![Model Comparison](F1.png)

![img](screenshot.png)

![Model Comparison](model_comparison_roc_plot.jpg)

### Deployment
We deployed a flask app that uses live streaming data, makes Fraud predictions, and logs predictions.

