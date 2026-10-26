# Air Quality Index (AQI) Data Analysis and Cleaning

A Jupyter notebook project that explores AQI records and prepares the data for a possible air-quality-status classification task. The notebook reads separate training and test CSV files, explores their contents, visualizes AQI and status distributions, cleans missing values, extracts date components, saves cleaned CSV files, and separates features from the `Status` target.

> **Data scope:** The notebook's data contains `Country`, `Date`, `Status`, and `AQI Value` columns. It does not show city-level data or India-only filtering, so this README describes it as country-level AQI records. Confirm the dataset's source and coverage before making a more specific claim.

## Notebook contents

- Inspect training and test datasets, their columns, summary statistics, missing values, and duplicate rows.
- Explore status counts, AQI values, record years, country counts, and average AQI by country and status.
- Plot distributions and summary comparisons with Matplotlib.
- Fill missing AQI values with the training median and missing categorical/date values with training-data modes.
- Extract `Year`, `Month`, and `Day` from `Date`.
- Save cleaned training and test datasets, then prepare `X_train`, `y_train`, `X_test`, and `y_test` with `Status` as the target.

The notebook prepares data for classification but does not train or evaluate a classification model.

## Files expected

Place these source CSV files where the notebook can read them:

- `data_date_train.csv`
- `data_date_test.csv`

Each file is expected to contain `Date`, `Country`, `Status`, and `AQI Value` columns. The notebook writes these outputs when run:

- `data_date_train_cleaned.csv`
- `data_date_test_cleaned.csv`

Only include the source or cleaned datasets in a public repository if their license permits redistribution and they contain no sensitive information. If you leave them out, readers will need to obtain the data separately and place the files in the expected location.

## Requirements

- Python 3
- Jupyter Notebook or Google Colab
- `numpy`
- `pandas`
- `matplotlib`

Install the Python libraries with:

```bash
pip install numpy pandas matplotlib notebook
```

## Run the notebook

1. Clone or download this repository, or open the notebook in Google Colab.
2. Put `data_date_train.csv` and `data_date_test.csv` in the notebook's working directory.
3. Open `Airqualityindexipynb.ipynb` and run the cells from top to bottom.
4. If running locally, change the two input paths near the top of the notebook from `/content/data_date_train.csv` and `/content/data_date_test.csv` to the local CSV paths (for example, `data_date_train.csv` and `data_date_test.csv`).
5. The cleaned CSV files will be saved in the current working directory.

## Data source

Add the original dataset name, source link, license, and any attribution required by its provider here. These details are not identified in the notebook, so they should be filled in before publishing if known.

## Notes

The training and test CSVs already include the `Status` column, which the notebook uses as the target label. The notebook also checks for missing values and duplicates; it does not remove duplicate rows.
