# 🍕 Pizza Price Prediction Using Machine Learning

## 📖 Overview

This project is a **Machine Learning regression project** developed to predict the price of pizzas based on different pizza characteristics.

The project follows an end-to-end Machine Learning workflow, starting from **data loading and cleaning**, followed by **Exploratory Data Analysis (EDA)**, **data preprocessing**, **feature encoding**, **model training**, **model evaluation**, **feature importance analysis**, and **price prediction**.

The project uses multiple regression algorithms and compares their performance using the **R² score**.

---

## 🎯 Project Objectives

The main objectives of this project are:

* 🧹 Clean and preprocess the pizza dataset.
* 🔍 Perform Exploratory Data Analysis (EDA).
* 📊 Visualize pizza prices and their characteristics.
* 🔢 Convert categorical features into numerical values.
* 🤖 Train multiple Machine Learning regression models.
* 📈 Compare model performance using R² score.
* ⭐ Analyze feature importance.
* 💾 Save and load the trained Machine Learning model.
* 🔮 Predict the price of a new pizza based on its features.
* 🖥️ Provide an optional Tkinter-based prediction interface for local execution.

---

## 📊 Dataset Information

The dataset used in this project is:

**`pizza_v2.csv`**

The dataset contains **129 entries and 9 columns** representing different characteristics of pizzas sold by different companies.

### 📌 Dataset Features

| Feature              | Description                               |
| -------------------- | ----------------------------------------- |
| 🏢 `company`         | Pizza company/brand                       |
| 💰 `price_rupiah`    | Original pizza price in Indonesian Rupiah |
| 📏 `diameter`        | Pizza diameter in inches                  |
| 🍗 `topping`         | Main pizza topping                        |
| 🍕 `variant`         | Specific pizza variant/style              |
| 📦 `size`            | Pizza size category                       |
| 🥫 `extra_sauce`     | Whether extra sauce is added              |
| 🧀 `extra_cheese`    | Whether extra cheese is added             |
| 🍄 `extra_mushrooms` | Whether extra mushrooms are added         |

### 📋 Example Categories

The dataset contains categories such as:

* 🏢 Companies: A, B, C, D, E
* 🍗 Toppings: Chicken, Mushrooms, Mozzarella, Smoked Beef, etc.
* 🍕 Variants: Double Signature, Meat Lovers, Classic, etc.
* 📦 Sizes: Small, Medium, Regular, Large, XL, Jumbo
* 🥫 Extra Sauce: Yes / No
* 🧀 Extra Cheese: Yes / No
* 🍄 Extra Mushrooms: Yes / No

---

## 🛠️ Technologies & Libraries Used

### 💻 Programming Language

* 🐍 **Python 3**

### 📚 Python Libraries

* 🐼 **Pandas** — Data manipulation and analysis
* 🔢 **NumPy** — Numerical computations
* 📊 **Matplotlib** — Data visualization
* 🎨 **Seaborn** — Statistical visualization
* 🤖 **Scikit-Learn** — Data preprocessing, model training, and evaluation
* 🚀 **XGBoost** — Gradient boosting regression
* 💾 **Joblib** — Saving and loading trained models
* 🖥️ **Tkinter** — Optional graphical user interface

---

## 🔄 Project Workflow

```text
📂 Dataset
    ↓
🧹 Data Cleaning
    ↓
📊 Exploratory Data Analysis
    ↓
🔧 Data Preprocessing
    ↓
🔢 Feature Encoding
    ↓
✂️ Train/Test Split
    ↓
🤖 Model Training
    ↓
📈 Model Evaluation
    ↓
⭐ Feature Importance
    ↓
💾 Model Saving
    ↓
🔮 Price Prediction
```

---

# 🧹 1. Data Cleaning

The dataset is first loaded and inspected to understand its structure, data types, and missing values.

### 💰 Price Cleaning

The original `price_rupiah` column contains prices in Indonesian Rupiah.

The following preprocessing steps are performed:

* Removed the `Rp` prefix.
* Removed commas from the price values.
* Converted the cleaned values into numeric format.
* Renamed `price_rupiah` to `price`.
* Converted the price using the factor **0.0054** as used in the notebook.

Example:

```python
df['price'] = df['price_rupiah'].str.replace('Rp', '', regex=False)
df['price'] = df['price'].str.replace(',', '', regex=False)
df['price'] = df['price'].astype(int)
df['price'] = df['price'] * 0.0054
```

### 📏 Diameter Cleaning

The `diameter` column contains values such as:

```text
8 inch
12 inch
16 inch
18 inch
```

The text `inch` and spaces are removed and the values are converted into floating-point numbers.

---

# 📊 2. Exploratory Data Analysis (EDA)

Exploratory Data Analysis is performed to understand the distribution and relationships within the dataset.

### 📈 Visualizations Used

The project includes visualizations such as:

* 📊 Distribution of Pizza Prices
* 📏 Diameter Distribution
* 🍗 Topping Distribution
* 🍕 Variant Distribution
* 📦 Pizza Size Distribution
* 🥫 Extra Sauce Distribution
* 🧀 Extra Cheese Distribution
* 🍄 Extra Mushroom Distribution
* 🏢 Price Comparison by Company
* 📦 Price Distribution by Pizza Size

### 📉 Visualization Techniques

The following visualization techniques are used:

* Histograms
* Count plots
* Bar plots
* Box plots

These visualizations help understand the characteristics of the dataset before applying Machine Learning models.

---

# 🔧 3. Data Preprocessing

Before training the Machine Learning models, the dataset is prepared for numerical processing.

### 🧹 Outlier Analysis

The project investigates pizza sizes and diameters to identify unusual observations.

The notebook specifically examines **jumbo-sized pizzas** and records with larger diameters.

### 🔢 Label Encoding

Categorical columns are converted into numerical values using Scikit-Learn's `LabelEncoder`.

The encoded columns include:

```text
company
topping
variant
size
extra_sauce
extra_cheese
extra_mushrooms
```

This allows Machine Learning algorithms to work with the categorical data.

---

# ✂️ 4. Train-Test Split

The dataset is divided into training and testing sets.

The project uses:

```python
test_size = 0.2
random_state = 42
```

Therefore:

* 🟢 **80%** → Training data
* 🔵 **20%** → Testing data

The `random_state=42` ensures reproducibility of the split.

---

# 🤖 5. Machine Learning Models

The project trains and compares multiple regression algorithms.

### 📌 Models Used

1. 📈 Linear Regression
2. 🔵 Support Vector Regression (SVR)
3. 🌳 Random Forest Regressor
4. 🚀 Gradient Boosting Regressor
5. ⚡ XGBoost Regressor

These models are used to learn the relationship between pizza characteristics and pizza prices.

---

# 📈 6. Model Evaluation

The models are evaluated using the **R² (R-squared) score**.

### 🏆 Recorded Results

| 🤖 Model                    |  📊 R² Score |
| --------------------------- | -----------: |
| Linear Regression           |     0.704968 |
| Support Vector Regression   |     0.024939 |
| Random Forest Regressor     |     0.891004 |
| Gradient Boosting Regressor | **0.930305** |
| XGBoost Regressor           |     0.767284 |

The values above are the scores recorded in the submitted notebook for the particular train/test split.

> 📌 **Note:** The notebook later saves an XGBoost model as the final model, although the recorded comparison table shows Gradient Boosting with the highest R² score. The README preserves the actual recorded results rather than changing them.

---

# ⭐ 7. Feature Importance

Feature importance is analyzed for the tree-based models.

The recorded XGBoost feature importance values are:

| Feature            | Importance |
| ------------------ | ---------: |
| 📏 Diameter        |   0.439365 |
| 📦 Size            |   0.350467 |
| 🥫 Extra Sauce     |   0.091034 |
| 🍕 Variant         |   0.080240 |
| 🧀 Extra Cheese    |   0.014667 |
| 🍗 Topping         |   0.014376 |
| 🏢 Company         |   0.005316 |
| 🍄 Extra Mushrooms |   0.004536 |

Based on the recorded XGBoost feature importance values, **diameter and size receive the largest importance values** among the features in the model.

---

# 💾 8. Model Saving and Loading

The project uses **Joblib** to save and load the trained Machine Learning model.

Example:

```python
import joblib

joblib.dump(model, 'pizzaprice_predictionmodel')
```

The saved model can later be loaded using:

```python
model = joblib.load('pizzaprice_predictionmodel')
```

This makes it possible to use the trained model for future predictions without retraining it every time.

---

# 🔮 9. Pizza Price Prediction

After training the model, the project demonstrates prediction using a sample pizza.

Example encoded input:

```text
company          = 1
diameter         = 16
topping          = 1
variant          = 1
size             = 1
extra_sauce      = 1
extra_cheese     = 1
extra_mushrooms  = 1
```

The recorded prediction in the notebook is approximately:

```text
💰 Predicted Price ≈ 517.1159
```

---

# 🖥️ 10. Graphical User Interface

The project also contains an optional **Tkinter GUI** for making predictions locally.

The GUI allows the user to enter the required feature values and obtain a predicted pizza price.

### ⚠️ Important

The GUI is intended for a **local Python environment** such as:

* VS Code
* PyCharm
* Local Jupyter environment

It is not designed to run directly inside Google Colab.

---

# 📁 11. Project Structure

```text
🍕 Pizza-Price-Prediction/
│
├── 📓 AvichalShivamKalpeshkumar_PizzaPricePrediction.ipynb
│
├── 📊 pizza_v2.csv
│
├── 📄 requirements.txt
│
├── 📖 README.md
│
├── 📝 AvichalShivamKalpeshkumar_ProjectReport.docx
│
└── 💾 pizzaprice_predictionmodel
```

---

# ⚙️ 12. Installation

### 1️⃣ Clone the Repository

```bash
git clone <your-repository-url>
```

### 2️⃣ Navigate to the Project Folder

```bash
cd Pizza-Price-Prediction
```

### 3️⃣ Install Required Libraries

```bash
pip install -r requirements.txt
```

Or install the main libraries manually:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost joblib
```

---

# ▶️ 13. How to Run

### 📓 Using Google colab Notebook

Start Colab Notebook:

```bash
colab notebook
```

Then open:

```text
AvichalShivamKalpeshkumar_PizzaPricePrediction.ipynb
```

Run the cells sequentially from top to bottom.

### 💻 Running Locally

The original notebook contains Google Colab/Google Drive file-loading code.

For local execution, the dataset can be loaded directly using:

```python
import pandas as pd

df = pd.read_csv("pizza_v2.csv")
```

Make sure `pizza_v2.csv` is located in the same directory as the notebook.

---

# 📦 14. Requirements

The main dependencies required for this project are:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
joblib
Google colab or jupyter 
ipykernel
```

A complete list is available in:

📄 `requirements.txt`

---

# ⚠️ 15. Project Limitations

* 📊 The dataset contains only **129 records**, so the model may not generalize to completely different datasets.
* 🔢 Label Encoding is used for categorical variables.
* 📈 The model evaluation is based on a single train/test split.
* 💱 The currency conversion uses a fixed **0.0054** factor from the submitted notebook rather than a live exchange rate.
* 💾 The categorical encoders are not separately saved with the model.
* 🖥️ The GUI currently expects encoded numerical values instead of user-friendly dropdown selections.
* 📊 The recorded model comparison shows Gradient Boosting with the highest R², while the notebook later saves XGBoost as the final model.

---

# 🚀 16. Future Improvements

The project can be improved by:

* 🔧 Using `ColumnTransformer` and `Pipeline`.
* 🔢 Using `OneHotEncoder` for categorical variables.
* 🔍 Applying cross-validation.
* ⚙️ Performing hyperparameter tuning.
* 📊 Evaluating models using MAE, RMSE, and R².
* 💾 Saving the complete preprocessing pipeline.
* 🖥️ Improving the GUI with dropdown menus.
* 🌐 Creating a Streamlit web application.
* ☁️ Deploying the trained model as an online prediction service.
* 💱 Using a live exchange-rate source if currency conversion is required.

---

# 📚 17. Dataset Source

The exact original public dataset URL is **not recorded inside the submitted colab Notebook**. Therefore, the `pizza_v2.csv` file included in this repository is the actual dataset used for the project.

A related public description of the Indonesian pizza-price dataset can be found here:

🔗 https://medium.com/@faizfadhilah1/prediksi-harga-pizza-indonesia-dengan-linear-regression-random-forest-regression-dan-xgboost-b7ad6dd52bd

---

# 👨‍💻 18. Author

# **Avichal Shivam Kalpeshkumar**

🎓 Computer Engineering Student
🤖 Machine Learning & Data Science Enthusiast
🐍 Python | SQL | Machine Learning | Data Analysis

---

## ⭐ Project Highlights

```text
🍕 Pizza Price Prediction
🐍 Python
📊 Data Analysis
🧹 Data Cleaning
📈 Exploratory Data Analysis
🤖 Machine Learning
🌳 Random Forest
🚀 Gradient Boosting
⚡ XGBoost
📉 Model Evaluation
⭐ Feature Importance
💾 Joblib
🖥️ Tkinter GUI
```

---

### 📌 Project Summary

> This project demonstrates an end-to-end Machine Learning workflow for predicting pizza prices using pizza characteristics such as company, diameter, topping, variant, size, and additional ingredients. Multiple regression models are trained and evaluated using the R² metric, followed by feature-importance analysis and model-based price prediction.
