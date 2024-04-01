# PM2.5 Concentration Analysis and Prediction in Chengdu

**Author: Srdjan Protic**  
**Contact: protic783@gmail.com**

This repository contains the analysis and prediction of PM2.5 concentrations in Chengdu, China, based on environmental parameters. The project encompasses linear regression for prediction and k-nearest Neighbors (kNN) classification for hazard categorization.

## Table of Contents

1. [Introduction](#i-introduction)
2. [Database](#ii-database)
3. [Exploratory Data Analysis](#iii-exploratory-data-analysis)
4. [Linear Regression](#iv-linear-regression)
5. [kNN Classifier](#v-knn-classifier)
6. [Model Evaluation Results](#vi-model-evaluation-results)

## I. Introduction

This project focuses specifically on Chengdu, China, utilizing data from the US Post location. The primary objectives include:

1. Linear Regression for PM2.5 Prediction in Chengdu: Developing a linear regression model to predict PM2.5 levels in Chengdu based on various environmental parameters. This analysis aims to understand how different factors contribute to air pollution in the specified location.

2. k-Nearest Neighbors (kNN) Classification for Chengdu: Implementing a kNN classification model to categorize PM2.5 levels in Chengdu into three pollution groups. This approach provides a classification framework to assess the severity of air pollution based on the similarity to neighboring samples.

## II. Database

The database comprises data representing meteorological parameters in the city of Chengdu. We have a total of 52,584 samples, where each sample represents the measured values of meteorological parameters during one hour in a day.

There are a total of 17 different features available, including both categorical and numerical attributes. Categorical features relate to the measurement date, including hourly and seasonal data. There are 24 measurements per day. 

The numerical features include common meteorological parameters such as temperature, humidity, air pressure, and wind direction. In addition to these, there are some unusual features such as cumulative wind speed (m/s), hourly precipitation (mm), and cumulative precipitation (mm). The most crucial numerical feature for our investigation is the concentration of PM2.5 particles (μg/m3) at the US Post location. 

## III. Exploratory Data Analysis

The dataset underwent curation, and exploratory visualizations provided insights into PM2.5 distribution and influential factors. In the pursuit of refining the dataset for scientific investigation, several thoughtful operations were executed to curate a dataset that is both pertinent and devoid of extraneous information. Each operation was undertaken with meticulous consideration, enhancing the overall quality and relevance of the data.

![image](https://github.com/srdjop/Analysis-and-prediction-of-PM2.5-concentration/assets/70009934/f9e83693-a25a-465b-a47d-b11ac6f660af)
![image](https://github.com/srdjop/Analysis-and-prediction-of-PM2.5-concentration/assets/70009934/bd4c73ac-825d-4d7c-9704-9a049a2b2ea2)

## IV. Linear Regression

Linear regression models were tested using a methodology where 30% of randomly selected samples were allocated for the test set,  while the remaining 70% of chosen samples were utilized for training the model.
Initially, a linear regression model with a single hypothesis: 'y= b0+b1x1+...+bnxn' was applied, but the results showed insufficient accuracy.
To enhance model performance, we introduced feature standardization, resulting in no significant improvement. 
We further explore the differences between two linear models using distinct hypotheses. While the second hypothesis:'y=b0+b1x1+b2x2+...+bnxn+c1x1x2+c2x1x3+...+d1x1^2+d2x2^2+...+dnxn^2', yielded better results, it exhibited substantial variations in regression coefficients.
This research provides insights into the application of linear regression models in predicting PM2.5 particle concentrations. Feature standardization and the adoption of Ridge regression proved pivotal in improving model performance and reducing variations in regression coefficients.

## V. kNN Classifier

Classification of hazard levels using the k-Nearest Neighbors (kNN) algorithm involves making decisions about the classification of a specific PM2.5 feature into one of the classes based on the class membership of its nearest neighbors in the training set. In the context of this methodology, the kNN algorithm assesses the similarity between the feature in question and its surrounding data points by measuring distances in the feature space. The decision on the class membership is then determined by the majority class among the k-nearest neighbors. 
This approach leverages the idea that similar instances in the feature space tend to belong to the same class. By employing the kNN algorithm, we aim to capture local patterns and dependencies within the data, allowing for a flexible and adaptive classification of PM2.5 hazard levels.

## VI. Model Evaluation Results

Linear Regression Results:

- **Model 1 (with hypothesis 'y= b0+b1x1+...+bnxn'):**
  - Mean Squared Error: 2349.0535
  - Mean Absolute Error: 35.2897
  - R2 Score: 0.2540
  - R2 Adjusted Score: 0.2537

- **Final model (Ridge Regression):**
  - Mean Squared Error: 1676.6744
  - Mean Absolute Error: 30.0007
  - R2 Score: 0.4675
  - R2 Adjusted Score: 0.4653

  ![image](https://github.com/srdjop/Analysis-and-prediction-of-PM2.5-concentration/assets/70009934/3570950c-5efe-40fc-aaf9-564b7b96f5c3)

Results from the kNN classifier demonstrated robust performance, as shown in the table below:

|           | Safe  | Unsafe | Dangerous |
|-----------|-------|--------|-----------|
| Precision | 0.9867| 0.9867 | 0.9834    |
| Accuracy  | 0.9914| 0.9863 | 0.9948    |
| Sensitivity| 0.9867| 0.9867 | 0.9834    |
| Specificity| 0.9917| 0.9860 | 0.9980    |
| F score   | 0.9867| 0.9867 | 0.9834    |
