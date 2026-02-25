# Wine Quality Prediction - Regression Project
## Overview
This project focuses on predicting the quality of wine based on its chemical properties. By applying Exploratory Data Analysis and various Machine Learning regression algorithms, the goal is to determine which chemical features most significantly influence expert quality ratings and to build a model capable of automated quality estimation.

## Dataset Description
The dataset used is the Wine Quality Dataset from the UCI Machine Learning Repository. It contains several chemical variables (features) and one target variable:
- Features: Fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, and alcohol.
- Target: quality (score between 0 and 10).

## Project Workflow
1. Exploratory Data Analysis (EDA)
- **Univariate Analysis:** Visualized feature distributions using histograms and boxplots.
- **Outlier Detection:** Used Boxplots to identify extreme values in features like residual sugar and chlorides.
- **Multivariate Analysis:** Created a correlation heatmap and pairplots of the top 5 features most correlated with quality.
- **Feature-Target Analysis:** Used Violin Plots visualize how alcohol change across different quality levels.
2. Data Cleaning & Preprocessing
Significant steps were taken to ensure data quality before modeling:
- **Class Filtering:** Removed extreme minority classes (quality 3 and 9) due to insufficient data points, ensuring a more stable training process.
- **Outlier Removal:** Applied the Interquartile Range (IQR) method to remove extreme values in skewed features.
- **Data Splitting:** Divided the data into training (80%) and testing (20%) sets.
- **Feature Scaling:** Implemented StandardScaler to normalize the range of independent variables.
3. Machine Learning Modeling
I implemented and compared three regression algorithms:
- **Linear Regression**
- **Decision Tree Regressor**
- **Gradient Boosting Regressor**

## Results 

| Model | Test MAE | Test RMSE | Test R2 Score |
| :--- | :---: | :---: | :---: |
| **Linear Regression** | 0.5599 | 0.7137 | 0.2793 |
| **Decision Tree** | 0.5962 | 0.7339 | 0.2379 |
| **Gradient Boosting** | **0.5338** | **0.6697** | **0.3654** |

## Conclusions
- Best Model: Gradient Boosting proved to be the most effective, explaining approximately 36.5% of the variance in wine quality with the lowest error (RMSE: 0.67).
- Error Interpretation: The MAE of 0.53 means the model, on average, predicts the wine quality within 0.5 points of the actual expert rating.
- Feature Importance: Alcohol content and volatile acidity emerged as the strongest predictors of quality.
- Final Thought: While chemical properties are strong indicators, the remaining variance likely stems from subjective factors or data not present in this set.

## Project Structure
```
├── figures/         # plots and visualizations
├── results/         # Model metrics
├── wine_MLproject   # Jupyter Notebook
└── README.md        #  documentation
```
