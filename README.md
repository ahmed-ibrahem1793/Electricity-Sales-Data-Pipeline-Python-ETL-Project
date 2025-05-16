Here’s a polished **README.md** for your GitHub repo, tailored to your electricity sales ETL project. It’s structured to be **clear, engaging, and developer-friendly** while highlighting your technical skills:

---

# **Electricity Sales ETL Pipeline**  

A Python-based **data engineering pipeline** that extracts, transforms, and loads (ETL) electricity sales data from CSV/JSON sources into analysis-ready formats (CSV/Parquet).  

## **📌 Project Overview**  
This project automates the processing of electricity sales data by:  
1. **Extracting** nested JSON and tabular (CSV/Parquet) data.  
2. **Transforming** raw data by filtering sectors (`residential/transportation`), cleaning missing values, and deriving time dimensions (`year/month`).  
3. **Loading** results into optimized storage formats (Parquet for efficiency, CSV for accessibility).  

**Use Case**: Enables analysts to quickly query sector-specific electricity pricing trends over time.  

---

## **⚙️ Technical Details**  

### **🔧 Functions**  
1. **`extract_tabular_data(file_path)`**  
   - Reads CSV/Parquet files using Pandas.  
   - Validates file extensions for compatibility.  

2. **`extract_json_data(file_path)`**  
   - Flattens nested JSON into a structured DataFrame using `pd.json_normalize()`.  

3. **`transform_electricity_sales_data(raw_data)`**  
   - Drops records with missing `price` values.  
   - Filters for `residential` and `transportation` sectors.  
   - Derives `year` and `month` columns from the `period` field.  

4. **`load(dataframe, file_path)`**  
   - Saves DataFrames to CSV or Parquet with dynamic format detection.  

### **📊 Data Flow**  
```mermaid
graph LR
    A[JSON/CSV Raw Data] --> B(Extract)
    B --> C(Transform)
    C --> D[Cleaned CSV/Parquet]
```

---

## **🚀 Getting Started**  

### **Prerequisites**  
- Python 3.8+  
- Libraries: `pandas`, `pyarrow` (for Parquet support)  

### **Installation**  
```bash
pip install pandas pyarrow
```

### **Usage**  
1. Place your raw data files (`electricity_sales.csv`, `electricity_capability_nested.json`) in the project directory.  
2. Run the script:  
   ```python
   python etl_pipeline.py
   ```
3. Outputs:  
   - `loaded__electricity_capability.parquet`  
   - `loaded__electricity_sales.csv`  

---

## **🛠️ Tech Stack**  
- **ETL**: Pandas (Python)  
- **Data Formats**: JSON, CSV, Parquet  
- **Data Cleaning**: Missing value handling, type conversion, column filtering  
- **Optimization**: Parquet for storage efficiency  
