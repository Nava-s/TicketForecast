# Ticket Quantity Prediction Project with XGBoost

## Dataset Description
The dataset contains information about the quantity of restaurant tickets to be ordered each month. It includes the following columns:
1. **Ticket Ordering File**: This dataset contains information about the quantity of restaurant tickets to be ordered each month. It includes the following columns:
   - **Company Name**: The name of the company.
   - **Employee ID**: The unique identifier for each employee.
   - **Job Location**: The location where the employee works.
   - **Quantity of Tickets**: The number of restaurant tickets to be ordered.
   - **Value of Tickets**: The monetary value of the tickets.
   - **Date**: The date of the order, formatted as DD/MM/YYYY (e.g., 30/11/2024 for November 2024).

2. **Employee's Job Information**: This dataset contains information about the employees' job details. It includes the following columns:

   - **Employee ID**: The unique identifier for each employee.
   - **Collective Contract**: The type of collective contract the employee is under.
   - **Qualification**: The employee's job qualification.
   - **Weekly Working Days**: The number of days the employee works per week.
   - **Shift Worker**: Indicates if the employee is a shift worker.
   - **Part-time Percentage**: The percentage of part-time work.
   - **Trustee**: Indicates if the employee is a trustee.
   - **On-call**: Indicates if the employee is on-call.
   - **Smart Working**: Indicates if the employee is working remotely.
   - **Organizational Structure Code**: The code of the organizational structure.
   - **Job Code**: The code of the job position.

## Project Description

This project aims to predict the quantity of tickets using the XGBoost machine learning model. The dataset used contains information about orders and employees, which have been combined and pre-processed to create a final dataset suitable for training the model.

## Project Structure

1. **Data Import**: Data was imported from CSV and Excel files. Unnecessary columns were removed, and dates were converted to datetime format.
2. **Data Augmentation**: Employee data was filtered to include only non-managerial employees and merged with the main dataset.
3. **Preprocessing**: 
   - Outliers were identified and removed.
   - New features such as lags and moving averages were created.
   - Rows with NaN values were removed.
   - The quantity variable was scaled by square root.
4. **Categorical Variable Encoding**: Categorical variables were encoded using the HashingEncoder.
5. **Dataset Splitting**: The dataset was split into training and testing sets in chronoligcal order.
6. **Model Training**: The XGBoost model was trained using the training data.
7. **Model Evaluation**: The model's performance was evaluated using metrics such as MAE and RMSE.
8. **Results Visualization**: Several plots were created to visualize the model's predictions and compare them with actual values. Specifically:
   - A line plot to show the trend of the average quantity over time.
   - A PACF (Partial Autocorrelation Function) plot to analyze the partial autocorrelation of the Qt variable.
   - A QQ Plot to compare the quantiles of the model's predictions with the actual values.
   - Box plots to visualize the distribution of the model's predictions and the actual values.
9. **Model Saving**: The trained model was saved using joblib.
10. **Logging with MLflow**: Model parameters, metrics, and the trained model were logged using MLflow.

## Requirements

- Python 3.10
- Libraries: pandas, numpy, scikit-learn, matplotlib, mlflow, xgboost, category_encoders, joblib, scipy, statsmodels

## Conclusions

This project demonstrates the use of advanced machine learning techniques for predicting ticket quantities. The XGBoost model proved effective in making predictions, with satisfactory performance metrics.
