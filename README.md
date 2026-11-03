# Medical Cost Prediction with Linear Regression

A portfolio project exploring how demographic and lifestyle variables relate to insurance charges and using multiple linear regression** to predict medical costs.

## Project at a glance

- **Task:** Supervised regression
- **Data:** 1,338 insurance records; features include age, sex, BMI, number of children, smoking status, and region
- **Tools:** Python, pandas, NumPy, seaborn, matplotlib, scikit-learn, Jupyter
- **Approach:** Exploratory data analysis, one-hot encoding, 80/20 train/test split, ordinary least-squares linear regression
- **Outcome:** R² of 0.7836 on the saved test split; see the evaluation table below

## Problem statement

Can a simple interpretable regression model estimate insurance charges using demographic and lifestyle information? The project investigates patterns in the dataset and evaluates a baseline linear regression model.


## Workflow

1. Load the insurance dataset and inspect data types and missing values.
2. Explore numeric correlations and visualise distributions and charges across demographic groups.
3. Convert categorical columns to indicator variables using `pd.get_dummies(drop_first=True)`.
4. Split the features and target into 80% training and 20% testing (`random_state=42`).
5. Fit `sklearn.linear_model.LinearRegression` and predict test-set charges.
6. Evaluate predictions using MAE, MSE, RMSE and R².

## Results

| Metric | Test result |
|---|---:|
| Mean Absolute Error (MAE) | 4,181.19 |
| Mean Squared Error (MSE) | 33,596,915.85 |
| Root Mean Squared Error (RMSE) | 5,796.28 |
| R² | 0.7836 |

The original analysis describes higher charges among smokers, a positive relationship between age and charges, and relatively similar charge distributions across sex and region. These are descriptive associations and **do not demonstrate causation**. The MAE indicates substantial typical prediction error despite the R² score.

## Visual exploration

![Saved exploratory chart 1](images/notebook_figure_03_02.png)

![Saved exploratory chart 2](images/notebook_figure_04_01.png)

![Saved exploratory chart 3](images/notebook_figure_05_01.png)

![Saved exploratory chart 4](images/notebook_figure_05_02.png)

![Saved exploratory chart 5](images/notebook_figure_05_03.png)

![Saved exploratory chart 6](images/notebook_figure_05_04.png)

## How to run

1. Clone or download this repository.
2. Install Python 3.10+ and the dependencies: `pip install -r requirements.txt`.
3. Obtain the correctly licensed dataset and save it as `insurance.csv` in the repository root.
4. Launch Jupyter: `jupyter notebook medical_cost_prediction.ipynb`.
5. Select **Kernel → Restart & Run All** to reproduce the analysis.

## Limitations and next steps

- The original notebook uses one train/test split; it does not report cross-validation or confidence intervals.
- The regression assumes a linear relationship; the notebook does not include a residual diagnostic or error breakdown by subgroup.
- The dataset provenance and license need to be verified before publishing the data.
- Future work: compare against a mean-prediction baseline, perform cross-validation, inspect residuals and subgroup errors, and compare with tree-based regressors.

## Repository structure

```text
medical-cost-prediction/
├── README.md
├── medical_cost_prediction.ipynb
├── requirements.txt
├── .gitignore
└── images/
    └── notebook_figure_*.png
```

## Author

Nontokozo Dladla — MSc Data Science candidate, University of the Witwatersrand.

*Educational portfolio project; not intended for clinical or insurance decision-making.*
