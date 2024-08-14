PROJECT CONTENTS
================
- prompt_III_AC_v1p1.ipynd: Jupyter file
- readme.md (this file): Project content description

GENERAL DESCRIPTION
===================
This project pertains to a marketing effort to encourage existing and new customers to open deposit accounts at a banking institution.
Customers are contacted through different methods (cellular, telephone calls) to promote deposit account offerings. 
The goal of the project is to develop quantitative models using AI/ML techniques that can be used to predict which customers will susbcribe new deposits at the bank. 
The project uses data contained in UC Irvine's Machine Learning reporsitory located at https://archive.ics.uci.edu/dataset/222/bank+marketing
The dataset reflects data collected for 17 marketing campaigns that took place between May 2008 and November 2010.

DETAILED DESCRIPTION
====================
This dataset is publicly available for research. The details are described in [Moro et al., 2014]. 
  [Moro et al., 2014] S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems, In press, http://dx.doi.org/10.1016/j.dss.2014.03.001

  Available at: [pdf] http://dx.doi.org/10.1016/j.dss.2014.03.001
                [bib] http://www3.dsi.uminho.pt/pcortez/bib/2014-dss.txt

Input variables:
   Bank client data:
   1 - age (numeric)
   2 - job : type of job (categorical: "admin.","blue-collar","entrepreneur","housemaid","management","retired","self-employed","services","student","technician","unemployed","unknown")
   3 - marital : marital status (categorical: "divorced","married","single","unknown"; note: "divorced" means divorced or widowed)
   4 - education (categorical: "basic.4y","basic.6y","basic.9y","high.school","illiterate","professional.course","university.degree","unknown")
   5 - default: has credit in default? (categorical: "no","yes","unknown")
   6 - housing: has housing loan? (categorical: "no","yes","unknown")
   7 - loan: has personal loan? (categorical: "no","yes","unknown")

   
   related with the last contact of the current campaign:
   
   8 - contact: contact communication type (categorical: "cellular","telephone") 
   9 - month: last contact month of year (categorical: "jan", "feb", "mar", ..., "nov", "dec")
  10 - day_of_week: last contact day of the week (categorical: "mon","tue","wed","thu","fri")
  11 - duration: last contact duration, in seconds (numeric). Important note:  this attribute highly affects the output target (e.g., if duration=0 then y="no"). Yet, the duration is not known before a call is performed. 
  Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.

  
  other attributes:
  
  12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
  13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
  14 - previous: number of contacts performed before this campaign and for this client (numeric)
  15 - poutcome: outcome of the previous marketing campaign (categorical: "failure","nonexistent","success")
  
  social and economic context attributes
  16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)
  17 - cons.price.idx: consumer price index - monthly indicator (numeric)     
  18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)     
  19 - euribor3m: euribor 3 month rate - daily indicator (numeric)
  20 - nr.employed: number of employees - quarterly indicator (numeric)


  Output variable (desired target):
  21 - y - has the client subscribed a term deposit? (binary: "yes","no")

ANALYSIS SCOPE
==============
The attached Jupyter notebook contains a detailed analysis of the data using several well-know data classification methods:
1) Decision Tree (DTree)
2) Logistic Regression (LR)
3) K-Mearest Neighbor (KNN)
4) Support Vector Machine (SVM)

The performance of these classifiers was evaluated on the basis of the following metrics:
1) Accuracy 
2) Precision
3) Recall
4) F1 score
5) Training time
   
Additional assesment tools and visualizations were employed to determine classification method performance:
1) Classification Report
2) Confusion Matrix


SUMMARY OF MAIN ACTIONS AND FINDINGS
====================================
- Data was explored for inconsistencies and missing values
- Feature engineering was conducted to select the best features to use for modeling
- Categorical features were hot-encoded
- Target variable clasess were binary encoded
- Numeric features were standardized
- Main findings
    - Decision Tree and SVM classifiers performed the best when models were optimized for accuracy or precision
    - Overall, it can be argued that SVM was the best performer for the conditions tested
    - The main drawback in using SVM was the long computation time compared to the other methods evaluated (KNN, LR, Decision Tree)
    - The performance of the models was affected by a significant class imbalance in the target variable (88.7% on target entries were 0 ('no') and 11.3% were 1 ('yes')) 
    - Data splitting stratification was partially successful in mitigating the biasing effects of target variable class imbalance

NEXT STEPS AND RECOMMENDATIONS
==============================
We have shown how the CRISP-DM framework can be used for the analysis of a marketing application using AI/ML methods. We illustrated how different quantitative classification methods can perform when 
predicting customer behavior (whether customer chooses to subscribe to offered deposit or not). The methods analyzed can be instrumental in ensuring the success of marketing campaigns with similar binary classification goals.
Simple stratification could not completely reduce the effects of severe class imbalance in the target variable. Focused intent sampling is required to mitigate this imbalance. 
We will explore this technique in a future revision of this work.
