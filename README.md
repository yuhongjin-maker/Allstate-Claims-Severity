# Allstate-Claims-Severity

### Objective

This competition aims to predict how severe the claim will or might be for a new household, predict future loss based on given features.

### Introduction

Allstate, the largest casualty insurer in America strives to improves its claim service and published a dataset which will help in building models that can predict claims severity. This competition aims to develop automated models for predicting the serverity of a particular insurance claim. It could help to ensure a worry-free customer experience.

#### Data

train.csv - the training set
test.csv - the test set. You must predict the loss value for the ids in this file.
sample_submission.csv - a sample submission file in the correct format

#### Metrics 

Mean Absolute Error(MAE)
This is a simple and direct obvious metric that compares the predicted value with the actual value. 

<img width="290" alt="Screen Shot 2023-03-16 at 2 59 58 AM" src="https://user-images.githubusercontent.com/59128675/225539385-da6334cb-a683-4039-8e85-a2551339901b.png">

### Methodology

<img width="581" alt="Screen Shot 2023-03-16 at 3 39 32 AM" src="https://user-images.githubusercontent.com/59128675/225547544-c0c05064-4d51-4186-bff6-a4f81ed4d299.png">

According to the graph, it's important to change the target variable in this way as RMSE algorithms (default for all regressions) prefer symmetric data: asymmetric output would bias the prediction towards higher losses.

Then change the categorical variables into numeric. I used only 1 column as the XGBoost algorithm doesn't really benefit from several columns. So I'm going to add the category codes to each categorical grouping value to find out the most import features.

<img width="578" alt="Screen Shot 2023-03-16 at 3 41 03 AM" src="https://user-images.githubusercontent.com/59128675/225547839-55a00968-4156-44b7-a5ef-b6cfc73436a6.png">

<img width="601" alt="Screen Shot 2023-03-16 at 3 41 31 AM" src="https://user-images.githubusercontent.com/59128675/225547950-92bb637e-0272-4aa9-babf-bdff26d9fdc6.png">

### Result

I used only 1 column as the XGBoost algorithm. Once I predicted and converted to csv file we got a LB score of 1152.3107. So far this is the best model that I built.
