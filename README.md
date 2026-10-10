# Milestone 2 — St. Louis Property Value Appreciation

## Project Overview

This project aims to predict one-year log appreciation in assessed property values in St. Louis. The predictions are intended to support preliminary property screening rather than final investment or development decisions.

## Data Source

The project uses annual parcel datasets from 2017 to 2025, downloaded from the City of St. Louis Open Data website.

Source: https://www.stlouis-mo.gov/data/datasets/distribution.cfm?id=189

The original CSV files are not included in this repository.

## Data Preparation

The notebook matches properties across consecutive years using `HANDLE` and calculates one-year log appreciation using `ASMTTOTAL`.

The analysis includes:

- Data quality and missing-value checks
- Property matching across years
- Data cleaning and feature engineering
- Exploratory data analysis
- Chronological train-validation-test split
- Mean baseline and linear regression

## Prediction Target

The target variable is:

`Log_Appreciation = log(Next_ASMTTOTAL / ASMTTOTAL)`

## Data Split

| Dataset | Years |
|---|---|
| Training | 2017–2022 |
| Validation | 2023 |
| Testing | 2024 |

## How to Run

1. Download the annual parcel CSV files from the official data source.
2. Place the files in a folder named `Parcels-CSV-2017-2025` inside the project directory.
3. Install the required Python packages using `requirements.txt`.
4. Open `Milestone2.ipynb` in Jupyter Notebook or VS Code.
5. Run the notebook cells in order.

## Preliminary Results

The initial linear regression model performs slightly better than the mean baseline on the 2023 validation set, but both models show limited predictive performance.

The 2024 test set is reserved for later evaluation.

## Limitations

The project predicts changes in assessed property values rather than actual market transaction prices. Missing data, extreme appreciation values, and changes in assessment practices may affect the results.
