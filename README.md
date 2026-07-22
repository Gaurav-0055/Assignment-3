# Assignment-3
# 📈 Salary Prediction using Polynomial Regression

> AI-ML Assignment 3 — Predicting employee salaries from position level using a degree-3 Polynomial Regression model.

## 👤 Author

| Field | Detail |
|---|---|
| **Name** | Gaurav Gour |
| **Registration No.** | 23BSA10096 |
| **Application No.** | IN26011516 |
| **Batch** | 1A |

## 🎯 Objective
The goal of this project is to predict employee salaries based on their position level using Polynomial Regression. Since salary does not increase linearly with position level, a polynomial model is used to capture the non-linear relationship between the two variables.

## 📊 Dataset
**Position Salaries Dataset**
🔗 Kaggle Link: [https://www.kaggle.com/datasets/akram24/position-salaries](https://www.kaggle.com/datasets/akram24/position-salaries)

The dataset contains 3 columns:
| Column | Description |
|---|---|
| `Position` | Job title |
| `Level` | Numeric position level (1–10) — **input feature** |
| `Salary` | Employee salary — **target variable** |

> Note: The dataset is not included in this repository. Please download it from the Kaggle link above.

## 🛠️ Libraries Used
- `pandas` — data loading and manipulation
- `numpy` — numerical operations
- `matplotlib` — data visualization
- `scikit-learn` — model building (`PolynomialFeatures`, `LinearRegression`) and evaluation metrics (`train_test_split`, `mean_absolute_error`, `mean_squared_error`, `r2_score`)

## 🧩 Methodology
1. **Data Understanding** — Loaded the dataset, inspected the first five records, identified `Level` as the input feature and `Salary` as the target variable, and reviewed dataset info and summary statistics.
2. **Data Preprocessing** — Checked for missing values, selected the feature and target columns, and split the data into 80% training and 20% testing sets.
3. **Model Development** — Transformed the input feature using `PolynomialFeatures` (degree = 3) and trained a Linear Regression model on the transformed features to perform polynomial regression.
4. **Model Evaluation** — Predicted salaries on the test set and evaluated performance using MAE, MSE, and R² Score. Visualized the results with a scatter plot of the original data and the fitted polynomial regression curve.

## 📉 Results

| Metric | Value |
|---|---|
| **Mean Absolute Error (MAE)** | 70,635.25 |
| **Mean Squared Error (MSE)** | 6,263,853,282.86 |
| **R² Score** | 0.876 |

**Observations:**
- The polynomial regression curve (degree 3) closely follows the non-linear growth in salary across position levels, fitting the data noticeably better than a straight line would.
- An R² Score of **0.876** indicates the model explains about 87.6% of the variance in salary, suggesting a strong fit given the data.
- Salary rises slowly at lower levels and sharply at senior levels — a pattern linear regression cannot capture, and the relatively high MAE/MSE reflect how large the salary jumps are at the top levels (e.g. CEO).

> Note: with only 10 data points, an 80/20 split leaves a very small test set, so these metrics should be interpreted with that limitation in mind.

## ✅ Conclusion
This project applied Polynomial Regression to predict employee salaries based on position level. Since salary growth across levels was clearly non-linear — rising slowly at first and then sharply at senior levels — a simple Linear Regression model would have underfit the data, producing a straight line that misses the curve entirely. Polynomial Regression, by transforming the single input feature into higher-degree terms (degree 3 here), allowed the model to capture this curvature while still using a linear regression algorithm underneath.

The key difference between the two lies in flexibility: Linear Regression assumes a constant rate of change, while Polynomial Regression can model varying rates of change across the range of the input. One clear advantage of Polynomial Regression for this dataset is that it captures the exponential-like jump in salary at higher position levels, which a straight-line model simply cannot represent, leading to a much better fit as reflected in the R² score.
