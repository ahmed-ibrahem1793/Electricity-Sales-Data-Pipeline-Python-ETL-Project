⚙️ Technical Details
🔧 Functions
extract_tabular_data(file_path)

Reads CSV/Parquet files using Pandas.

Validates file extensions for compatibility.

extract_json_data(file_path)

Flattens nested JSON into a structured DataFrame using pd.json_normalize().

transform_electricity_sales_data(raw_data)

Drops records with missing price values.

Filters for residential and transportation sectors.

Derives year and month columns from the period field.

load(dataframe, file_path)

Saves DataFrames to CSV or Parquet with dynamic format detection.

📊 Data Flow
Diagram
Code




🚀 Getting Started
Prerequisites
Python 3.8+

Libraries: pandas, pyarrow (for Parquet support)

Installation
bash
pip install pandas pyarrow
Usage
Place your raw data files (electricity_sales.csv, electricity_capability_nested.json) in the project directory.

Run the script:

python
python etl_pipeline.py
Outputs:

loaded__electricity_capability.parquet

loaded__electricity_sales.csv

🛠️ Tech Stack
ETL: Pandas (Python)

Data Formats: JSON, CSV, Parquet

Data Cleaning: Missing value handling, type conversion, column filtering

Optimization: Parquet for storage efficiency
