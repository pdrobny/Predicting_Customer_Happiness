# Predicting Customer Happiness

## Project Overview
A logistics and delivery startup would like to predict customer happiness or unhappiness based on customer survey responses.  

In addition, they are very interested in finding which questions/features are more important when predicting a customer’s happiness and if any questions can be removed in the next survey.

##  Installation and Setup
Editor Used:  Jupyter Notebook
Python Version:  3.12.4
Python Packages:  pandas, numpy, matplotlib, seaborn, gdown, warnings, logging, lazypredict, random, hyperopt, sklearn

## Data
The customer survey data is in .csv format located in the link below: 
[Survey Data link](https://drive.google.com/open?id=1KWE3J0uU_sFIJnZ74Id3FDBcejELI7FD)

Data Description:

  Y = target attribute (Y) with values indicating 0 (unhappy) and 1 (happy) customers
  
  X1 = my order was delivered on time
  
  X2 = contents of my order was as I expected
  
  X3 = I ordered everything I wanted to order
  
  X4 = I paid a good price for my order
  
  X5 = I am satisfied with my courier
  
  X6 = the app makes ordering easy for me
  

Attributes X1 to X6 indicate the responses for each question and have values from 1 to 5 where the smaller number indicates less and the higher number indicates more towards the answer.

## Methods
Data Cleaning:  The data check was checked for validity and completeness and determined no data cleaning was needed.  

Data Visualation:  A heat map was generated to look for correlation between customer survey scores and customer happiness.  Barcharts were created to look for any trends or patterns for each survey question.

Predictive Model Evaluation and Selection:  The data split into test and training sets.  Hyper parameter optimization was peformed using hyperopt on Linear Regression, Random Forest, Linear SVC models.  These models were trained and fit using the best found hyperparameters and evaluated for overall accuracy and recall for "Unhappy" customers.  Random Forest as found to be the best performing model with a recall score   

Feature Selection:  Recursive Feature Elimination (RFE) was used on the random forest model to determine the most important features using "Unhappy" recall as the scoring metric.  RFE found the features that resulted in the highest 'Unhappy' recall score were X1, X3, and X5 with a recall score of 88% 

Final Model Training:  The Random Forest was retrained using the RFE recommended features and optimized again using hyperopt resulting in a overall accuracy of 81% and "Unhappy" recall of 88%.

## Conclusion
Following model evaluation and feature selection a random forest model was able to achieve a prediction accuracy of 81% and unhappy customer recall of 88%. The features of most importance were found to be X1, X3, and X5, and it is recommended to remove X2, X4, and X6 from the next survey.

<img width="614" alt="image" src="https://github.com/user-attachments/assets/650e40e8-dabd-42de-9e35-71937e0613ca" />

