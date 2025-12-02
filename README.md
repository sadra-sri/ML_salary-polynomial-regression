# Salary Prediction – Polynomial Regression on Position Levels

This project uses a small **Position vs Salary** dataset to show how
**polynomial regression** can model a non-linear relationship better than a
simple linear regression.

The goal is to predict **salary** based on the **position level** and to
visually and numerically compare:

- Linear Regression (straight line)
- Polynomial Regression (curved fit using polynomial features)

---

## Dataset

- **Name:** Position_Salaries  
- **Source:** Kaggle  
- **Link:** https://www.kaggle.com/datasets/ankushsawarkar/simple-vs-polynomial-regression-salary-predict  

The dataset typically contains:

- `Position` – job title (e.g. Business Analyst, Manager, CEO)
- `Level` – numeric level from 1 to 10
- `Salary` – corresponding salary

> **Note:** The dataset file (`Position_Salaries.csv`) is **not** included in this repository.  
> Please download it from Kaggle and place it in the same folder as the notebook.

---

## Project Overview

In the notebook I:

- Load the dataset and inspect basic info (`head`, `info`, `describe`)
- Select:
  - **Feature (X):** `Level` (or equivalent column name, e.g. `Level_In_Office`)
  - **Target (y):** `Salary` (or equivalent column name, e.g. `Salary_Month`)
- Plot a **scatter chart** of Level vs Salary to see that the relationship is
  clearly **non-linear**
- Train a baseline **Linear Regression** model:
  - Fit `LinearRegression` on the original `Level` feature
  - Plot the straight regression line over the data
  - Observe underfitting (the line does not follow the curve of the points)
- Train a **Polynomial Regression** model:
  - Use `PolynomialFeatures` (e.g. degree 3 or 4) to generate `[x, x², x³, …]`
  - Fit `LinearRegression` on the transformed features
  - Create a fine grid of Level values and plot the smooth polynomial curve
  - Visually compare **linear vs polynomial** fits
- Perform a **train/test split**:
  - Split data using `train_test_split`
  - Fit the polynomial model on the train set
  - Evaluate on the test set using:
    - **R² (coefficient of determination)**
    - **RMSE (root mean squared error)**

---

## How to Run

1. **Clone the repository:**

   ```bash
   git clone https://github.com/sadra-sri/ML_salary-polynomial-regression.git
   cd ML_salary-polynomial-regression

2. (Optional) Create and activate a virtual environment.

3. Install dependencies:

    pip install -r requirements.txt

4. 4. Download the `Position_Salaries.csv` file from Kaggle and save it in the project folder (same directory as the notebook).


5. Run the notebook:

    jupyter notebook Salary.ipynb


