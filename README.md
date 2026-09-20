# Linear Regression: From First Principles to Regularization

A four-part Jupyter notebook series that explains linear regression end to end — from a single-feature model and gradient descent, through multivariate regression, model diagnostics and assumptions, to polynomial regression and regularization — built around a running **Cars24 car-price prediction** case study, alongside supporting case studies on Auto MPG and US electricity consumption.

## Contents

| # | Notebook | Topics |
|---|---|---|
| 1 | [`Linear_Regression_1.ipynb`](./Linear_Regression_1.ipynb) | Introduces the running **Cars24** business case — an automobile company entering the US market and wanting to understand what drives car pricing; loads and previews the car-price dataset |
| 2 | [`Linear_Regression_2.ipynb`](./Linear_Regression_2.ipynb) | **Univariate Linear Regression** — predicting price from a single feature (`max_power`), the `estimate_charges` cost function, weights and bias; **Gradient Descent** intuition, including a 3D visualization of the line-fitting/descent process; **Multivariate Linear Regression** — extending to multiple features; introduction to the **coefficient of determination (R²)** |
| 3 | [`Linear_Regression_3.ipynb`](./Linear_Regression_3.ipynb) | Recap of prior concepts; the **importance of train/test splitting** and random splits; **feature importance and interpretation** of regression coefficients; **why standardization matters** (z-score, min-max scaling) and its limitations; a full **code walkthrough predicting fuel mileage** on the Auto MPG dataset — categorical encoding (label vs. one-hot, dummy variables), missing-value handling, model fitting, and R² / Adjusted R²; the **impact of outliers**; an introduction to **StatsModels**; the five core **assumptions of Linear Regression** (linearity, no multicollinearity via **VIF**, normally distributed errors, independent errors, **homoscedasticity** via the Goldfeld–Quandt test); **Polynomial Regression** via a US electricity-consumption case study; **Occam's Razor**; the **bias–variance tradeoff** (over/underfitting, with a student-exam analogy); and **Regularization** — Ridge (L2), Lasso (L1), and Elastic Net, including the leakage/budget "tug-of-war" analogy for the loss–penalty tradeoff |
| 4 | [`Linear_Regression_4.ipynb`](./Linear_Regression_4.ipynb) | Applies the assumptions and diagnostics from notebook 3 directly to the **Cars24** dataset — fitting an OLS model with StatsModels, iteratively removing high-VIF features, and **automating VIF-based feature elimination** with an R²-threshold stopping rule; revisits **overfitting and underfitting** in this applied setting |

## Suggested learning path

The notebooks build on each other and are meant to be worked through in order:

1. **`Linear_Regression_1.ipynb`** — the business problem and dataset.
2. **`Linear_Regression_2.ipynb`** — univariate and multivariate regression fundamentals, gradient descent, R².
3. **`Linear_Regression_3.ipynb`** — train/test splitting, scaling, a full applied case study, model assumptions, polynomial regression, bias–variance tradeoff, and regularization.
4. **`Linear_Regression_4.ipynb`** — putting the diagnostics and feature-selection techniques from notebook 3 into practice on the Cars24 dataset, including automation.

## Requirements

- Python 3
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `statsmodels`
- `scipy` (Shapiro–Wilk normality test, Goldfeld–Quandt test)
- `gdown` — used to download the datasets in every notebook
- Internet access (for `gdown` downloads and inline images hosted on Google Drive)

Install with:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn statsmodels scipy gdown
```

## Datasets

- **Cars24 car price dataset** (`cars24-car-price-clean.csv` / `cars24-car-price-cleaned.csv`, notebooks 1, 2, and 4) — car listings with features (e.g. `max_power`, `make`, `model`, `year`) used to predict `selling_price`; downloaded via `gdown`.
- **Auto MPG dataset** (notebook 3) — car attributes (including categorical `origin`, `horsepower` with missing values) used to predict fuel mileage; downloaded via `gdown`.
- **US electricity consumption dataset** (notebook 3) — year vs. consumption, used for the polynomial regression case study; downloaded via `gdown`.

All datasets are fetched at runtime within their respective notebooks; no separate data directory is required.

## How to run

Open each notebook with Jupyter or JupyterLab (or Google Colab, given the `gdown` download cells) and run all cells top to bottom:

```bash
jupyter notebook Linear_Regression_1.ipynb
```

Cells within each notebook are sequential — later sections depend on data loaded, cleaned, and split earlier in the same notebook — so run them in order. Notebook 4 assumes familiarity with the diagnostics introduced in notebook 3 but loads and prepares its own data independently.

## Notes

- These notebooks are instructional: they include instructor notes, in-class questions, analogies, and discussion prompts alongside the code, and are best suited for guided teaching or self-paced learning rather than as a production regression library.
- Some sections (e.g., the "10:20 pm" / "Break - 10:22 pm" / "How can we automate" headers) reflect the notebooks' origin as live lecture recordings and are left as-is for context.
