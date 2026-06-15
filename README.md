# 🚗 Auto MPG Dataset — Analysis & Prediction

A data science project that explores and models the classic **Auto MPG dataset**, predicting a vehicle's fuel efficiency (miles per gallon) based on its physical and mechanical attributes. Built entirely in a Jupyter Notebook with rich visualizations and regression modeling.

---

## 📌 Overview

Fuel efficiency is a critical indicator of vehicle performance, environmental impact, and running cost. This project performs a complete end-to-end analysis of the Auto MPG dataset — originally from the UCI Machine Learning Repository — covering data cleaning, exploratory data analysis (EDA), feature engineering, and predictive regression modeling.

The goal is to accurately **predict the MPG (miles per gallon)** of a car given features like engine size, horsepower, weight, and origin.

---

## 🗂️ Repository Structure

```
auto-mpg-dataset/
│
├── auto_mpg_dataset.ipynb   # Main notebook: EDA, visualizations, preprocessing, regression models
├── auto_data.csv            # Dataset (~398 vehicles, 9 features)
└── README.md                # Project documentation
```

---

## 📦 Dataset

**File:** `auto_data.csv`
**Records:** ~398 vehicles
**Source:** UCI Machine Learning Repository — Auto MPG Dataset

### Features

| Column         | Type        | Description                                        |
|----------------|-------------|----------------------------------------------------|
| `mpg`          | Continuous  | 🎯 **Target** — Miles per gallon (fuel efficiency) |
| `cylinders`    | Discrete    | Number of engine cylinders (4, 6, 8)              |
| `displacement` | Continuous  | Engine displacement (cubic inches)                 |
| `horsepower`   | Continuous  | Engine horsepower (contains missing values)        |
| `weight`       | Continuous  | Vehicle weight (lbs)                               |
| `acceleration` | Continuous  | Time to accelerate from 0–60 mph (seconds)         |
| `model_year`   | Discrete    | Model year (70–82, representing 1970–1982)         |
| `origin`       | Categorical | Country of origin (1=USA, 2=Europe, 3=Japan)      |
| `car_name`     | String      | Make and model name of the vehicle                 |

> ⚠️ The `horsepower` column contains a small number of missing values (`?`) that require preprocessing.

---

## 🔍 Project Pipeline

The notebook covers a complete data science workflow:

### 1. 📥 Data Loading & Inspection
- Load `auto_data.csv` with Pandas
- Inspect shape, dtypes, null values, and summary statistics

### 2. 🧹 Data Preprocessing
- Handle missing `horsepower` values (imputation or row removal)
- Convert `horsepower` from string to numeric
- Encode the `origin` feature (one-hot or label encoding)
- Drop non-predictive columns (`car_name`)

### 3. 📊 Exploratory Data Analysis (EDA)
- Distribution plots for MPG and all numerical features
- Correlation heatmap to identify relationships
- Scatter plots: MPG vs weight, horsepower, displacement
- Box plots: MPG grouped by cylinders, origin, and model year
- Year-over-year trend of fuel efficiency improvements

### 4. ⚙️ Feature Engineering
- Derived features if applicable
- Feature scaling / normalization for regression models
- Train-test split (typically 80/20)

### 5. 🤖 Model Training
One or more regression models trained and compared:
- **Linear Regression** — Baseline model
- **Polynomial Regression** — Captures non-linear relationships
- **Ridge / Lasso Regression** — Regularized variants
- **Random Forest Regressor** — Ensemble tree-based approach

### 6. 📏 Model Evaluation

| Metric     | Description                                            |
|------------|--------------------------------------------------------|
| **MAE**    | Mean Absolute Error — average prediction error in MPG  |
| **MSE**    | Mean Squared Error — penalizes large errors more heavily |
| **RMSE**   | Root MSE — error in same units as target (MPG)         |
| **R² Score** | Proportion of variance explained by the model        |

### 7. 📈 Results & Visualizations
- Actual vs. Predicted MPG scatter plot
- Residual plots to assess model fit
- Feature importance ranking

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Nimra064/auto-mpg-dataset.git
cd auto-mpg-dataset
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 3. Run the Notebook

```bash
jupyter notebook auto_mpg_dataset.ipynb
```

Or open directly in **Google Colab** — upload `auto_data.csv` to the session files before running.

---

## 💡 Key Insights

Some patterns typically uncovered in this dataset:

- **Weight** is the strongest negative predictor of MPG — heavier cars are significantly less fuel-efficient
- **Displacement** and **horsepower** are highly correlated with each other and negatively correlated with MPG
- **Model year** shows a clear positive trend — cars became more fuel-efficient over the 1970s and early 1980s
- **Japanese and European cars** (origin = 2, 3) tend to have higher MPG than American cars
- **4-cylinder** engines consistently achieve higher fuel efficiency than 6- or 8-cylinder engines

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **Python** | Core language |
| **Pandas** | Data loading and manipulation |
| **NumPy** | Numerical computations |
| **Matplotlib & Seaborn** | Data visualization and EDA charts |
| **Scikit-learn** | Regression models, preprocessing, evaluation |
| **Jupyter Notebook** | Interactive development environment |

---

## 🔮 Possible Enhancements

- Add **cross-validation** for more robust model evaluation
- Try **XGBoost** or **Gradient Boosting** regressors
- Build a simple **Streamlit app** where users input car specs and get an MPG prediction
- Use **SHAP values** for model explainability
- Extend with a **modern dataset** (EPA fuel economy data) to compare vintage vs. contemporary trends

---

## 📄 License

This project is open-source and available for educational and research use.

---

## 🙏 Acknowledgements

- Dataset originally from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/auto+mpg)
- Widely used as a benchmark dataset in regression and EDA tutorials

---
