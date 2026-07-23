# 🍔 Swiggy Order Data Analysis

An exploratory data analysis (EDA) of ~200K Swiggy food delivery orders using **Python, Pandas, Matplotlib, Seaborn, and Plotly**. The project cleans and explores raw order-level data to surface sales trends, customer rating patterns, and regional performance.

## 📂 Dataset

The dataset (`swiggy_data.xlsx`) contains order-level records with the following columns:

| Column | Description |
|---|---|
| `State` | State where the order was placed |
| `City` | City where the order was placed |
| `Order Date` | Date of the order |
| `Restaurant Name` | Name of the restaurant |
| `Location` | Locality/area within the city |
| `Category` | Menu category (e.g. Snack, Recommended, North Indian Gravy) |
| `Dish Name` | Name of the dish ordered |
| `Price (INR)` | Order price in INR |
| `Rating` | Restaurant/dish rating |
| `Rating Count` | Number of ratings received |

**Size:** 197,430 rows × 10 columns
**Date range:** Jan 1, 2025 – Aug 31, 2025

## 🛠️ Tools & Libraries

- **Pandas / NumPy** – data loading, cleaning, aggregation
- **Matplotlib / Seaborn** – line and bar charts
- **Plotly Express** – interactive pie and bar charts

## 🧹 Data Prep

- Loaded the raw Excel file with `pandas.read_excel` (via `openpyxl`)
- Inspected shape, dtypes, and summary statistics
- Derived new columns: `YearMonth`, `DayName`, `Quarter`, and a keyword-based `Food Category` (Veg / Non-Veg) flag

## 📊 Key Metrics

| Metric | Value |
|---|---|
| **Total Sales** | ₹5,30,12,505.77 |
| **Total Orders** | 197,430 |
| **Average Order Value** | ₹268.51 |
| **Average Rating** | 4.3 / 5 |
| **Total Ratings Count** | 5,591,574 |

### Price & Rating Summary Statistics

| Stat | Price (INR) | Rating | Rating Count |
|---|---|---|---|
| Mean | 268.51 | 4.34 | 28.32 |
| Min | 0.95 | 1.5 | 0 |
| 25% | 139.00 | 4.3 | 0 |
| 50% (Median) | 229.00 | 4.4 | 2 |
| 75% | 329.00 | 4.5 | 15 |
| Max | 8,000.00 | 5.0 | 999 |
| Std Dev | 219.34 | 0.42 | 87.54 |

### Quarterly Summary

| Quarter | Total Sales (INR) | Avg Rating | Total Orders |
|---|---|---|---|
| 2025 Q1 | 1,96,67,821.77 | 4.34 | 73,096 |
| 2025 Q2 | 1,99,02,256.59 | 4.34 | 74,163 |
| 2025 Q3 | 1,34,42,427.41 | 4.34 | 50,171 |

*(Note: Q3 2025 is a partial quarter — data only runs through August 31.)*

## 📈 Charts & Insights

### 1. Monthly Sales Trend
Revenue tracked month-over-month across the full Jan–Aug 2025 window.

<img width="862" height="630" alt="image" src="https://github.com/user-attachments/assets/8fe14263-8bae-4a95-89b6-eae34139e2f0" />


### 2. Daily Revenue Trend (Mon–Sun)
Total revenue aggregated by day of the week to spot weekday vs. weekend ordering patterns.

<img width="864" height="470" alt="image" src="https://github.com/user-attachments/assets/b25ab008-bbe2-4def-815d-4e9eea450ae0" />


### 3. Veg vs Non-Veg Revenue Split
Dishes were tagged **Non-Veg** if their name contained keywords like *chicken, egg, fish, mutton, prawn, biryani, kabab*, else **Veg**. Chart shows each category's share of total revenue.

<img width="861" height="400" alt="image" src="https://github.com/user-attachments/assets/85a3393a-7bb9-45de-8ff5-8be6c1f9384e" />


### 4. Revenue by State
Total revenue broken down across every state in the dataset.

<img width="1279" height="647" alt="image" src="https://github.com/user-attachments/assets/1fd387c4-9360-4d5c-bad9-da039b437d55" />


### 5. Top 5 Cities by Sales
The five highest-revenue-generating cities.

<img width="1268" height="529" alt="image" src="https://github.com/user-attachments/assets/4258cc2a-dc52-4292-a599-797b29c5b8ba" />


## 🚀 How to Run

1. Clone this repo and install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn plotly openpyxl
   ```
2. Place `swiggy_data.xlsx` in the project directory (update the file path in the notebook if needed).
3. Open and run `swiggy_python.ipynb` in Jupyter Notebook / JupyterLab.

## 📁 Project Structure

```
.
├── swiggy_python.ipynb     # Main analysis notebook
├── swiggy_data.xlsx        # Source dataset (not included in repo)
├── charts/                 # Exported chart images
└── README.md
```

## 🔮 Possible Next Steps

- Build an interactive dashboard (Streamlit / Power BI) on top of this analysis
- Analyze top-performing restaurants and dishes by revenue
- Correlate rating count with order volume to study popularity vs. quality
- Add cuisine-level breakdown beyond the Veg/Non-Veg split
