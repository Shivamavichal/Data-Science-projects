# 🍕 Pizza Price Prediction

## 📖 Overview
This repository contains a Data Science and Machine Learning project aimed at predicting the price of pizzas based on various attributes. The project demonstrates an end-to-end machine learning workflow, starting from data ingestion and cleaning, progressing through exploratory data analysis (EDA) and feature engineering, and setting up for predictive modeling.

## 📊 Dataset Information
The dataset (`pizza_v2.csv`) contains 129 entries and 9 columns representing various characteristics of pizzas sold by different companies.

### Features:
*   **company**: The pizza company/brand (e.g., A, B, C, D, E).
*   **price**: The price of the pizza (originally in Indonesian Rupiah `Rp`, converted to Indian Rupee `INR` during cleaning).
*   **diameter**: The diameter of the pizza in inches.
*   **topping**: The primary topping on the pizza (e.g., chicken, mushrooms, mozzarella, smoked beef, etc.).
*   **variant**: The specific variant/style of the pizza (e.g., double_signature, meat_lovers, classic, etc.).
*   **size**: The size category of the pizza (small, medium, regular, large, XL, jumbo).
*   **extra_sauce**: Whether extra sauce was added (yes/no).
*   **extra_cheese**: Whether extra cheese was added (yes/no).
*   **extra_mushrooms**: Whether extra mushrooms were added (yes/no).

## 🛠️ Technologies & Libraries Used
*   **Python 3**
*   **Pandas & NumPy**: Data manipulation and numerical computations.
*   **Matplotlib & Seaborn**: Data visualization and EDA.
*   **Scikit-Learn**: Data preprocessing (`LabelEncoder`), data splitting, and model evaluation metrics.
*   **Machine Learning Algorithms**: Linear Regression, Logistic Regression, Random Forest, Gradient Boosting, Support Vector Regressor (SVR), and XGBoost.
*   **Joblib**: Model saving and loading.

## ⚙️ Project Workflow

### 1. Data Cleaning
*   Extracted numeric values from the `price_rupiah` column by removing the 'Rp' prefix and commas, followed by a currency conversion to Indian Rupees (INR) using a 0.0054 multiplier.
*   Renamed the `price_rupiah` column to `price`.
*   Cleaned the `diameter` column by removing the 'inch' string and converting the values to floating-point numbers.

### 2. Exploratory Data Analysis (EDA)
*   Visualized the **Distribution of Pizza Prices** using a histogram.
*   Created count plots for categorical variables such as `diameter`, `topping`, `variant`, `size`, `extra_sauce`, `extra_cheese`, and `extra_mushrooms`.
*   Analyzed pricing patterns across different companies using Bar plots.
*   Visualized price distributions relative to pizza size using Box plots.

### 3. Data Preprocessing
*   **Outlier Removal**: Identified and removed specific outliers (e.g., 'jumbo' sized pizzas with a diameter of 16 inches or less).
*   **Label Encoding**: Categorical features (`company`, `topping`, `variant`, `size`, `extra_sauce`, `extra_cheese`, `extra_mushrooms`) were converted into numerical formats using Scikit-Learn's `LabelEncoder` to prepare the data for machine learning models.

### 4. Model Training (Setup)
*   The project initializes a robust suite of regression and classification models including Random Forest, Gradient Boosting, XGBoost, and SVR to accurately map pizza features to their respective prices. 

## 🚀 How to Run
1. Clone the repository to your local machine.
2. Ensure you have Python installed along with the required libraries (`pip install pandas matplotlib seaborn scikit-learn xgboost`).
3. Place the `pizza_v2.csv` dataset in the appropriate directory (update the file path in the notebook if running locally outside of Google Colab).
4. Run the Jupyter Notebook cell by cell to observe the data transformations, visualizations, and model preparations.

---
*Generated as a comprehensive summary of the provided Jupyter Notebook workflow.*
