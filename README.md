# Diagnosis of COVID-19 and its clinical spectrum

## Table of Contents
1. [Background](#Background)
2. [Dataset](#Dataset)
3. [Submission Expectations](#SubmissionExpectations)
3. [Evaluation Criteria](#EvaluationCriteria)
4. [Additional Notes](#AdditionalNotes)

### Summary of the COVID-19 Dataset

#### **Background**
- The dataset originates from Hospital Israelita Albert Einstein in São Paulo, Brazil, during the COVID-19 pandemic.
- Brazil recorded its first case on February 26, with rapid community transmission leading to overburdened health systems.
- The dataset was collected in the context of an overwhelmed health system, limiting SARS-CoV-2 testing capabilities.

#### **Dataset**
- Contains anonymized data from patients tested for SARS-CoV-2 RT-PCR along with additional lab tests.
  
- Data are standardized to a mean of zero and a unit standard deviation.
  
- We print Missing Values
  ![image](https://github.com/user-attachments/assets/089f03b5-b9c1-4f11-a6d5-7cdad167c509)
- Missing values Heatmap
  ![image](https://github.com/user-attachments/assets/dc067eec-df3e-4395-828a-1545ad9ee96f)
- Missing values distribution

  ![image](https://github.com/user-attachments/assets/242b54a8-bcdc-44c5-bad8-76e458981cec)
   
  We can delete Columns containing more than 90% missing values
- We now preprocess data with missing values, the detail is avaiable in the notebook but basically we average some values by their mean and we create new values such as "has_disease" to avoid missing values among some specific illness

- We create an heatmap to analyze correlations
  ![image](https://github.com/user-attachments/assets/ebba80eb-78f7-485e-9a77-3deee5fb6449)

- We finally use SMOTE to rebalance the data, in fact, most of patients are negative to covid so the model may randomly suppose that most of them are negative and still make a prediction looking accurate and we want to avoid that

  




#### **Task**
**Predict COVID-19 Positive Cases**:
- We Evaluate several models such as random forest, svm, XGB, KNN, LR and even a stacking technique

- We focus on 2 specific KPIs which are Accuracy and Recall, the goal is to ensure the precision of the classification and also to focus on the model's ability to identify true positives among the model's positive elements.

- The best performances are given by Random Forest and Xgboost classifiers

Accuracy Score:  0.9090909090909091

Recall Score: 0.7058823529411765

AUC:  0.8240950226244345

KS:  0.6481900452488688



#### **Additional Notes**
- Decision-making in healthcare is complex and reflected in the dataset's sparsity.
- Clinical and exposure data are not currently available, emphasizing lab results for model development.
- The challenge aims to develop a model useful for routine clinical care with commonly ordered lab tests.

https://www.kaggle.com/datasets/einsteindata4u/covid19/data





