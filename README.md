# House-Price-Prediction
House Price Prediction is a machine-learning regression project that predicts the estimated price of a house based on property characteristics such as location, house size, number of bedrooms and bathrooms, house age, parking spaces, and distance from the city.
# House Price Prediction

## Overview

House Price Prediction is a machine-learning regression project that predicts the estimated price of a house using different property-related features.

The project considers factors such as location, house size, number of bedrooms, number of bathrooms, house age, parking spaces, and distance from the city.

A Linear Regression model is used to learn the relationship between these features and house prices.

This project is intended for educational, academic, and machine-learning practice purposes.

## Objectives

* Analyze house-related data.
* Understand factors affecting house prices.
* Clean and preprocess the dataset.
* Handle missing values.
* Encode categorical data.
* Standardize numerical features.
* Train a regression model.
* Predict house prices.
* Evaluate model performance.
* Identify important factors affecting house prices.
* Visualize house-price patterns.
* Compare actual and predicted prices.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Linear Regression
* StandardScaler
* OneHotEncoder
* SimpleImputer
* Pipeline
* ColumnTransformer

## Project Structure

```text
House_Price_Prediction/
│
├── README.md
├── requirements.txt
├── house_price_prediction.py
└── house_prices.csv
```

The program also generates visualization files after execution.

## Dataset

The project uses a synthetic house-price dataset containing property information and corresponding house prices.

### Dataset Features

| Feature             | Description                          |
| ------------------- | ------------------------------------ |
| property_id         | Unique property identifier           |
| location            | Location category of the property    |
| house_size_sqft     | Size of the house in square feet     |
| bedrooms            | Number of bedrooms                   |
| bathrooms           | Number of bathrooms                  |
| house_age_years     | Age of the property in years         |
| parking_spaces      | Number of available parking spaces   |
| distance_to_city_km | Distance from the city in kilometers |
| price               | House price                          |

## Target Variable

The target variable is:

```text
price
```

The model predicts this value as a continuous numerical output.

## Data Preprocessing

The project performs several preprocessing operations before training the machine-learning model.

The following steps are performed:

1. Load the dataset using Pandas.
2. Display the first five records.
3. Check the dataset shape.
4. Check for missing values.
5. Remove `property_id` because it is an identifier rather than a predictive feature.
6. Separate the input features and target variable.
7. Identify numerical and categorical features.
8. Fill missing numerical values using the median.
9. Standardize numerical features using `StandardScaler`.
10. Fill missing categorical values using the most frequent value.
11. Convert the `location` feature into numerical form using `OneHotEncoder`.
12. Combine preprocessing and regression into a Scikit-learn pipeline.

## Numerical Features

The numerical features used by the model are:

```text
house_size_sqft
bedrooms
bathrooms
house_age_years
parking_spaces
distance_to_city_km
```

## Categorical Features

The categorical feature used by the model is:

```text
location
```

The encoder uses `handle_unknown="ignore"` so that the model can process previously unseen location categories during prediction.

## Machine Learning Algorithm

### Linear Regression

The project uses Linear Regression as the prediction algorithm.

Linear Regression is suitable for this project because house price is a continuous numerical value.

The model learns the relationship between property characteristics and house prices from the training dataset.

## Train-Test Split

The dataset is divided into:

* 80% training data
* 20% testing data

A `random_state` of `42` is used to make the train-test split reproducible.

## Model Evaluation

The model is evaluated using three regression metrics.

### Mean Absolute Error

MAE represents the average absolute difference between actual house prices and predicted house prices.

A lower MAE indicates better prediction performance.

### Root Mean Squared Error

RMSE represents the square root of the average squared prediction error.

RMSE gives more importance to larger prediction errors.

A lower RMSE indicates better model performance.

### R² Score

The R² score measures how well the model explains the variation in house prices.

A value closer to `1` generally indicates better performance.

## Example House Prediction

The project includes an example property with the following characteristics:

```text
Location: Suburban
House Size: 1800 sq ft
Bedrooms: 3
Bathrooms: 2
House Age: 8 years
Parking Spaces: 2
Distance to City: 10 km
```

The trained model uses these values to estimate the property's price.

The predicted price is displayed when the program is executed.

## Feature Importance

The project analyzes the coefficients generated by the Linear Regression model.

The coefficients are used to identify the factors that have the strongest relationship with the predicted house price.

The program calculates the absolute impact of each feature and displays the top 10 factors affecting house price.

A positive coefficient indicates a positive relationship with the predicted price, while a negative coefficient indicates a negative relationship, assuming other model inputs remain constant.

## Visualizations

The project generates two visualizations.

### 1. House Size vs House Price

This scatter plot shows the relationship between house size and house price.

Generated file:

```text
size_vs_price.png
```

### 2. Actual vs Predicted House Prices

This scatter plot compares the actual prices from the test dataset with the prices predicted by the Linear Regression model.

Generated file:

```text
actual_vs_predicted.png
```

## Installation

Make sure Python is installed on your computer.

Open a terminal inside the project directory and install the required libraries:

```bash
pip install -r requirements.txt
```

## Requirements

The project requires the following Python libraries:

```text
pandas
numpy
matplotlib
scikit-learn
```

## How to Run

After installing the required dependencies, run:

```bash
python house_price_prediction.py
```

The program will:

1. Load the house-price dataset.
2. Display the first five records.
3. Display the dataset shape.
4. Check for missing values.
5. Clean missing numerical and categorical data.
6. Prepare the input features and target.
7. Encode the location feature.
8. Standardize numerical features.
9. Split the dataset into training and testing data.
10. Train the Linear Regression model.
11. Generate house-price predictions.
12. Calculate MAE.
13. Calculate RMSE.
14. Calculate the R² score.
15. Predict the price of a new house.
16. Display the most important model factors.
17. Generate house-price visualizations.

## Output

The program displays:

* Dataset preview
* Dataset dimensions
* Missing-value information
* Mean Absolute Error
* Root Mean Squared Error
* R² Score
* Predicted price for a new house
* Top factors affecting house prices

The program also generates:

```text
size_vs_price.png
actual_vs_predicted.png
```

## Dataset Note

The included house-price dataset is synthetic and is intended for educational and classroom machine-learning practice.

It does not contain real property records or real-time market prices.

## Limitations

House prices in real-world markets depend on many additional factors that are not included in this dataset, such as:

* Exact neighborhood
* Property condition
* Construction quality
* Local market demand
* Nearby schools
* Transportation facilities
* Economic conditions
* Interest rates
* Property amenities
* Recent comparable sales

Therefore, the model should be considered an educational house-price estimation system rather than a professional real-estate valuation tool.

## Disclaimer

This project is created for educational and machine-learning practice purposes.

The predicted prices are estimates generated from the available synthetic dataset and should not be considered official property valuations, market prices, or guaranteed selling prices.
