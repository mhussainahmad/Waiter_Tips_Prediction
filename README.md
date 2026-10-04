# Waiter Tips Prediction

A short Google Colab notebook from April 2022 that explores the restaurant tips dataset and fits a linear regression to predict the tip amount.

## Overview

`Waiter_Tips_Prediction.ipynb` works with the columns `total_bill`, `tip`, `sex`, `smoker`, `day`, `time` and `size` (party size).

1. **Exploration (Plotly).** Scatter plots of tip vs. total bill coloured by day, sex and time, with OLS trendlines; donut charts of total tips by day, smoker status and lunch vs. dinner.
2. **Encoding.** Maps the categorical columns to integers (`sex`: Female 0 / Male 1, `smoker`: No 0 / Yes 1, `day`: Thur 0 to Sun 3, `time`: Lunch 0 / Dinner 1).
3. **Model.** Trains a scikit-learn `LinearRegression` on `total_bill, sex, smoker, day, time, size` with an 80/20 train/test split (`random_state=42`), then predicts the tip for one example input.

The notebook does not compute an evaluation metric on the test split.

## Running

The notebook was written for Google Colab and reads the data from `/content/drive/MyDrive/Datasets/Waiter tips prediction.txt` (a Google Drive path). The data file is not included in this repository. To run it elsewhere, point the data-loading cell at your own copy of the CSV, or load the same data with `seaborn.load_dataset("tips")`.

Dependencies: numpy, pandas, plotly, statsmodels (for the trendlines) and scikit-learn.

## Data

The tips dataset (Bryant and Smith, 1995), which is also bundled with seaborn.
