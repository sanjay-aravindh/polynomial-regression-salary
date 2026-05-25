# Polynomial Regression vs Linear Regression

A hands-on comparison of **Linear Regression** and **Polynomial Regression (degree 4)** using scikit-learn, applied to a position-salary dataset.

---

## Overview

This notebook demonstrates why polynomial regression outperforms simple linear regression when the underlying relationship between variables is non-linear. Using a classic HR dataset of job levels and salaries, we fit both models, visualize their curves, and compare predictions.

---

## Project Structure

```
polynomial-regression-salary/
│
├── polynomial_regression.ipynb   # Main notebook
├── position_salaries.csv         # Dataset (Position, Level, Salary)
├── requirements.txt              # Python dependencies
└── README.md
```

---

## Dataset

The `position_salaries.csv` file contains:

| Column     | Description                    |
|------------|--------------------------------|
| Position   | Job title (e.g. Manager, CEO)  |
| Level      | Numeric position level (1–10)  |
| Salary     | Annual salary in USD           |

---

## Models

### Linear Regression
Fits a straight line through the data. Works well for linear trends but underfits non-linear salary growth.

### Polynomial Regression (Degree 4)
Transforms features using `PolynomialFeatures(degree=4)` and fits a LinearRegression on the expanded feature set — capturing the curve of exponential salary growth at senior levels.

---

## Results

| Model                 | Prediction for Level 5.5 |
|-----------------------|--------------------------|
| Linear Regression     | ~$249,500                |
| Polynomial (Degree 4) | ~$158,862                |

The polynomial model better captures the non-linear salary curve, making it the more accurate predictor for mid-level positions.

---

## Getting Started

### Prerequisites

- Python 3.7+
- Jupyter Notebook or JupyterLab

### Installation

```bash
git clone https://github.com/your-username/polynomial-regression-salary.git
cd polynomial-regression-salary
pip install -r requirements.txt
jupyter notebook polynomial_regression.ipynb
```

---

## Requirements

See `requirements.txt`:

```
numpy
pandas
matplotlib
scikit-learn
jupyter
```

---

## Key Fixes from Original Code

| Bug | Fix |
|-----|-----|
| `import ijumpy as np` | `import numpy as np` |
| Inconsistent `x` / `X` casing | Standardized to `X` throughout |
| Missing indentation in `viz_linear()` | Fixed Python indentation |
| `viz_polymonial()` typo | Renamed to `viz_polynomial()` |
| No smooth curve in polynomial plot | Added `X_grid` with step 0.1 for a smoother line |

---

## License

MIT License
