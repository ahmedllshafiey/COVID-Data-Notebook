# COVID-19 Global Statistics

This repository contains analysis and visualizations of global COVID-19 statistics, based on a **snapshot of data on 28/07/2025** from **229 countries**. The dataset includes various metrics such as total cases, deaths, recoveries, testing, and population-adjusted values.

## Dataset Overview

The dataset includes the following columns:

| Column            | Description                           |
| ----------------- | ------------------------------------- |
| `Unnamed: 0`      | Row index or unique ID                |
| `country`         | Country name                          |
| `population`      | Total population of the country       |
| `active_cases`    | Number of active COVID-19 cases       |
| `critical_cases`  | Number of critical COVID-19 cases     |
| `total_cases`     | Cumulative confirmed COVID-19 cases   |
| `recovered_cases` | Total recovered cases                 |
| `total_deaths`    | Total deaths attributed to COVID-19   |
| `1M_pop_cases`    | Total cases per 1 million population  |
| `1M_pop_deaths`   | Total deaths per 1 million population |
| `1M_pop_tests`    | Total tests per 1 million population  |
| `total_tests`     | Total number of tests performed       |

## Project Goals

1. **Data Exploration and Visualization**
   - Understand the distribution of cases, deaths, recoveries, and tests across countries.
   - Identify patterns, trends, and outliers.

2. **Statistical Analysis**
   - Analyze relationships between variables such as `total_tests` vs `recovered_cases` and `total_tests` vs `total_deaths`.

3. **Predictive Modeling**
   - **Regression models** (Linear Regression, Random Forest Regressor) to predict recovered cases.
   - **Classification models** (Logistic Regression, Random Forest Classifier) to categorize countries into low/medium/high recovered cases.

## Visualizations

- Distribution plots for each COVID-19 metric.
- Correlation heatmaps to analyze relationships between variables.
- Scatter plots to study the relationship between testing and outcomes (recoveries/deaths).
- Regression lines to indicate trends in the data.

Color palettes are applied consistently to improve readability.

## Machine Learning Workflow

1. **Preprocessing**
   - Handle missing values.
   - Scale features using `StandardScaler` for classification.
   - Convert continuous target into categories using `KBinsDiscretizer` for classification tasks.

2. **Models Implemented**
   - Regression: Linear Regression, Random Forest Regressor
   - Classification: Logistic Regression, Random Forest Classifier

3. **Evaluation Metrics**
   - Regression: R², RMSE
   - Classification: Accuracy, Precision, Recall, F1-score

## Example Analysis

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.scatterplot(data=df, x="total_tests", y="recovered_cases", color="#c86558")
sns.regplot(data=df, x="total_tests", y="recovered_cases", scatter=False, color="#991f17")
plt.show()
```

## Installation

This project requires Python 3.x and the following libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Usage

1. Clone the repository.
2. Load the dataset using pandas:

```python
import pandas as pd
df = pd.read_csv("covid_data.csv")
```

3. Run Jupyter Notebook cells sequentially to reproduce the analysis and visualizations.

## License

This project is open-source under the **MIT License**.
