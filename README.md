# PM2.5 Concentration Analysis and Prediction in Chengdu

**Author: Srdjan Protic**  
**Contact: protic783@gmail.com**

This repository contains the analysis and prediction of PM2.5 concentrations in Chengdu, China, based on environmental parameters. The project encompasses linear regression for prediction and k-Nearest Neighbors (kNN) classification for hazard categorization.

## Table of Contents

1. [Introduction](#i-introduction)
2. [Database](#ii-database)
3. [Exploratory Data Analysis](#iii-exploratory-data-analysis)
4. [Linear Regression](#iv-linear-regression)
5. [kNN Classifier](#v-knn-classifier)
6. [Model Evaluation Results](#vi-model-evaluation-results)
7. [How to Use](#vii-how-to-use)
8. [License](#viii-license)
9. [Acknowledgments](#ix-acknowledgments)

## I. Introduction

This project focuses on predicting and categorizing PM2.5 levels in Chengdu. It includes linear regression for prediction and kNN classification for hazard categorization.

## II. Database

The dataset contains meteorological data from Chengdu, comprising 52,584 samples with 17 features. The primary focus is on PM2.5 concentration.

## III. Exploratory Data Analysis

The dataset underwent curation, and exploratory visualizations provided insights into PM2.5 distribution and influential factors.

## IV. Linear Regression

Linear regression models were tested, leading to the adoption of Ridge regression for improved performance.

## V. kNN Classifier

The kNN classifier categorized PM2.5 levels into hazard classes. Cross-validation yielded optimal parameters for exceptional performance.

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
  - 
Results from the kNN classifier demonstrated robust performance, as shown in the table below:

|           | Safe  | Unsafe | Dangerous |
|-----------|-------|--------|-----------|
| Precision | 0.9867| 0.9867 | 0.9834    |
| Accuracy  | 0.9914| 0.9863 | 0.9948    |
| Sensitivity| 0.9867| 0.9867 | 0.9834    |
| Specificity| 0.9917| 0.9860 | 0.9980    |
| F score   | 0.9867| 0.9867 | 0.9834    |

## VII. How to Use

1. **Clone the Repository:**
   - Open a terminal or command prompt.
   - Run the following command to clone the repository to your local machine:
     ```bash
     git clone https://github.com/yourusername/PM2.5-Chengdu-Analysis.git
     ```
   - Replace "yourusername" with your actual GitHub username.

2. **Navigate to the Project Directory:**
   - Change into the project directory:
     ```bash
     cd PM2.5-Chengdu-Analysis
     ```

3. **Install Dependencies:**
   - Ensure you have Python installed on your machine.
   - Install the required dependencies by running:
     ```bash
     pip install -r requirements.txt
     ```

4. **Open Jupyter Notebook:**
   - Start Jupyter Notebook by running:
     ```bash
     jupyter notebook
     ```
   - This will open a new tab in your web browser showing the Jupyter file explorer.

5. **Explore the Analysis:**
   - In the Jupyter file explorer, locate and open the `PM2.5_Chengdu_Analysis.ipynb` notebook.

6. **Run the Notebook:**
   - Inside the notebook, you can run each cell by clicking on it and pressing `Shift + Enter`.
   - Explore the code, visualizations, and results provided in the notebook.

7. **Contribute:**
   - Feel free to contribute by raising issues, submitting pull requests, or improving the analysis.
