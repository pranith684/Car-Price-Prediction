# Car Price Prediction using Machine Learning

This project demonstrates a complete machine learning workflow to predict the selling price of used cars based on their features. The model is built using Python and the Scikit-learn library.

![Actual vs Predicted Prices]("C:\Users\solas\Downloads\actual_vs_predicted.png")

---

## Table of Contents
- [Project Goal](#project-goal)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Model Performance](#model-performance)
- [How to Run This Project](#how-to-run-this-project)
- [Technologies Used](#technologies-used)

---

## Project Goal
The primary objective of this project is to build a reliable linear regression model that can accurately estimate the selling price of a used car based on its key attributes like its present price, age, kilometers driven, and fuel type.

---

## Dataset
The dataset used for this project is `cardata.csv`, which contains information on 301 used cars. The features include:
- **Car_Name:** The name of the car model.
- **Year:** The year the car was manufactured.
- **Selling_Price:** The price the car was sold for (in Lakhs). **(Target Variable)**
- **Present_Price:** The current showroom price of the car (in Lakhs).
- **Kms_Driven:** The total kilometers the car has been driven.
- **Fuel_Type:** The type of fuel the car uses (Petrol, Diesel, CNG).
- **Seller_Type:** Whether the seller is a Dealer or an Individual.
- **Transmission:** The transmission type of the car (Manual, Automatic).
- **Owner:** The number of previous owners the car has had.

---

## Methodology
The project follows a standard machine learning pipeline:

1.  **Data Loading & Inspection:** The dataset is loaded using Pandas for initial inspection and to check for missing values.
2.  **Feature Engineering:** A new feature, `Age`, is created by subtracting the manufacturing `Year` from the current year. This provides a more intuitive feature for the model.
3.  **Data Preprocessing:**
    * The `Car_Name` column is dropped as it is not suitable for a linear regression model.
    * Categorical features (`Fuel_Type`, `Seller_Type`, `Transmission`) are converted into a numerical format using one-hot encoding. This is a crucial step to allow the model to process text-based data correctly.
4.  **Model Training:** The dataset is split into training (80%) and testing (20%) sets. A `LinearRegression` model is trained on the training data.
5.  **Model Evaluation:** The trained model's performance is evaluated on the unseen test data using standard regression metrics.

---

## Model Performance
The model achieved the following results on the test set:

- **R-squared (R²) Score:** **0.85**
  - *This indicates that the model can explain 85% of the variance in the car prices, which is a strong result.*
- **Mean Absolute Error (MAE):** 1.22 Lakhs
  - *On average, the model's predictions are off by approximately 1.22 Lakhs.*
- **Root Mean Squared Error (RMSE):** 1.87 Lakhs

The scatter plot of actual vs. predicted values shows a strong positive correlation, confirming the model's predictive power.

---

## How to Run This Project
To run this project on your local machine, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/pranith684/Car-Price-Prediction.git](https://github.com/pranith684/Car-Price-Prediction.git)
    cd Car-Price-Prediction
    ```
2.  **Install the required libraries:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Run the script:**
    ```bash
    python predict.py
    ```
The script will run the model and print the evaluation metrics to the console.

---

## Technologies Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
