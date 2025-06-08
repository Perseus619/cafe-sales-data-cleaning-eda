# Cafe Sales Data Cleaning Project

This project demonstrates a comprehensive workflow for cleaning and preparing raw cafe transaction data for analysis using Python and pandas.

## Project Overview

The goal is to transform messy, incomplete, and inconsistent sales data into a clean dataset ready for analysis. The process includes handling missing values, correcting data types, removing duplicates, and intelligently filling gaps using statistical methods.

## Folder Structure

```
.
├── data/
│   ├── raw/
│   │   └── dirty_cafe_sales.csv
│   └── processed/
│       └── cleaned_cafe_sales.csv
├── notebooks/
│   └── cleaning.ipynb
└── README.md
```

## Data Sources

- **Raw Data:** `data/raw/dirty_cafe_sales.csv`  
  Contains unprocessed cafe sales transactions.
- **Cleaned Data:** `data/processed/cleaned_cafe_sales.csv`  
  Output after all cleaning steps.

## Cleaning Steps

All cleaning steps are documented in `notebooks/cleaning.ipynb`:

1. **Loading Data**
   - Import the raw CSV into a pandas DataFrame.

2. **Initial Audit**
   - Inspect data shape, columns, and summary statistics.
   - Identify missing values and data types.

3. **Column Cleanup**
   - Strip whitespace from column names.
   - Rename columns for consistency.
   - Drop irrelevant columns (e.g., Transaction ID).

4. **Type Conversion**
   - Convert date columns to datetime.
   - Convert numeric columns to appropriate types.

5. **Handling Missing & Invalid Values**
   - Replace "ERROR" and "UNKNOWN" with NaN.
   - Fill missing values in `Total Purchase`, `Quantity`, and `Price Per Unit` using available data.
   - Impute missing `Item` values based on `Price Per Unit` and contextual probabilities.
   - Impute missing `Payment Method` and `Location` using grouped probabilities and lookup tables.

6. **Deduplication**
   - Remove duplicate rows.

7. **Final Cleanup**
   - Drop any remaining rows with critical missing values.
   - Export the cleaned dataset to `data/processed/cleaned_cafe_sales.csv`.

## How to Run

1. Open `notebooks/cleaning.ipynb` in Jupyter Notebook or VS Code.
2. Run all cells to reproduce the cleaning process.
3. The cleaned data will be saved to `data/processed/cleaned_cafe_sales.csv`.

## Requirements

- Python 3.x
- pandas
- numpy

Install dependencies with:

```sh
pip install pandas numpy
```

## Outputs

- **Cleaned CSV:** Ready for analysis or reporting.
- **Notebook:** Step-by-step documentation of the cleaning logic.

## License

This project is for educational purposes.

---