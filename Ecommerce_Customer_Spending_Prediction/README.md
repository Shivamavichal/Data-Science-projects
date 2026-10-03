# Ecommerce Customer Yearly Spending Prediction

## 📌 Project Overview

This project uses Machine Learning to predict the yearly amount spent by ecommerce customers based on their usage and membership information.

A Linear Regression model is trained using customer features such as time spent on the app, time spent on the website, and length of membership.

## 🎯 Objective

The main objective of this project is to understand the relationship between customer behavior and yearly spending and build a regression model that can predict the amount a customer is likely to spend.

## 📊 Dataset

The dataset contains information about ecommerce customers.

Important features used for prediction:

* **Time on App** – Time spent by the customer on the mobile app
* **Time on Website** – Time spent by the customer on the website
* **Length of Membership** – Number of years the customer has been a member

### Target Variable

* **Yearly Amount Spent** – Yearly amount spent by the customer

The dataset contains 500 customer records.

## 🔍 Exploratory Data Analysis

The project includes:

* Dataset inspection
* Statistical summary
* Feature relationships
* Pair plot visualization
* Joint plots
* Linear relationship visualization

## 🤖 Machine Learning Model

### Linear Regression

Linear Regression is used to predict the yearly amount spent by customers.

### Features

```text
Time on App
Time on Website
Length of Membership
```

### Target

```text
Yearly Amount Spent
```

The dataset is divided into training and testing sets using a 70:30 split.

## 📈 Model Evaluation

The model is evaluated using:

* Mean Absolute Error (MAE)
* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)
* R² Score

Current notebook results:

```text
MAE  : 20.69
MSE  : 678.40
RMSE : 26.05
Explained Variance : 0.9069
```

The R² score can also be calculated in the notebook using `r2_score`.

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

## 📁 Project Structure

```text
Ecommerce-Customer-Spending-Prediction/
│
├── Ecommerce_Customer_Spending_Prediction.ipynb
├── Ecommerce_Customers.csv
├── README.md
├── requirements.txt
```

## 🚀 How to Run

1. Clone the repository.
2. Install the required Python libraries.
3. Open the Jupyter Notebook.
4. Make sure the CSV file is in the same project folder.
5. Run the notebook cells.

## 📌 Conclusion

The Linear Regression model demonstrates that customer engagement and membership duration can be used to predict yearly ecommerce spending. The project provides practical experience with data exploration, visualization, regression modeling, and model evaluation.
