# Mexico Real Estate Analysis

A data science project analyzing real estate properties across Mexico, including property types, locations, sizes, and prices.

## Project Overview

This project explores a dataset of 700 real estate properties in Mexico, examining characteristics such as:
- **Property Types**: Houses and apartments
- **Geographic Data**: State locations, latitude, and longitude coordinates
- **Physical Attributes**: Property area in square meters
- **Market Data**: Prices in USD

## Dataset Description

### Data Source
- **File**: `mexico-real-estate-1.csv`
- **Total Records**: 700 properties
- **Clean Records**: 583 (after removing missing geographic data)
- **Format**: CSV

### Columns

| Column | Type | Description |
|--------|------|-------------|
| `property_type` | Categorical | Type of property (house/apartment) |
| `state` | String | Mexican state where property is located |
| `lat` | Float | Latitude coordinate |
| `lon` | Float | Longitude coordinate |
| `area_m2` | Float | Property area in square meters |
| `price_usd` | String | Price in USD (formatted with currency symbol) |

### Data Quality Notes

- **Missing Values**: 117 properties have missing latitude/longitude coordinates (NaN values)
  - Example: Properties in Veracruz de Ignacio de la Llave and Morelos have missing coordinates
  - Data cleaning removes these rows for geographic analysis
  
- **Price Format**: Prices are stored as formatted strings (e.g., "$67,965.56") and require conversion to numeric format for analysis

## Files Included

- `DS2P1L1.ipynb` - Jupyter notebook with data exploration and analysis
- `mexico-real-estate-1.csv` - Main dataset file
- `README.md` - This file

## Getting Started

### Prerequisites

```bash
pip install pandas jupyter
```

### Basic Usage

```python
import pandas as pd

# Load the dataset
path = "mexico-real-estate-1.csv"
df = pd.read_csv(path)

# View first 5 rows
df.head()

# View dataset info
df.info()

# Check for missing values
df.isnull().sum()

# Clean data - remove rows with missing coordinates
df_clean = df.dropna()
```

## Key Insights

### Property Distribution
- Dataset contains both houses and apartment properties
- Properties distributed across multiple Mexican states including:
  - Estado de México
  - Nuevo León
  - Guerrero
  - Yucatán
  - Querétaro
  - Puebla
  - Distrito Federal
  - And others

### Price Range
- Prices vary from $56,637.97 to $237,089.17+ USD
- Average property area: ~150-200 square meters

### Geographic Coverage
- 583 properties have complete coordinate data for mapping and spatial analysis
- 117 properties require additional geocoding or data imputation

## Recommended Analysis Tasks

1. **Data Cleaning**
   - Convert `price_usd` from string format to numeric values
   - Handle missing latitude/longitude values
   - Validate coordinate ranges

2. **Exploratory Data Analysis (EDA)**
   - Distribution of prices by property type
   - Average prices by state
   - Correlation between area and price
   - Geographic clustering of properties

3. **Statistical Analysis**
   - Price per square meter analysis
   - State-wise price comparisons
   - Identify price outliers

4. **Visualization**
   - Geographic maps of properties
   - Price distribution histograms
   - Box plots by property type/state
   - Scatter plots (area vs. price)

## Tools & Libraries

- **Python 3.x**
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib/Seaborn** - Data visualization
- **Folium/Plotly** - Geographic visualization

## Environment

This project was developed in Google Colab with the following setup:
- **Kernel**: Python 3
- **Runtime**: Colab or local Jupyter

## Acknowledgments

This project is part of the coursework from **[World Quant University](https://www.wqu.edu/)**, a leading online educational institution providing accessible, high-quality education in:

- **Data Science** - Statistical analysis, machine learning, and data-driven decision making
- **Machine Learning** - Advanced algorithms and predictive modeling
- **Quantitative Finance** - Financial mathematics and risk analysis
- **Financial Engineering** - Derivatives, portfolio management, and trading strategies

World Quant University is committed to democratizing access to world-class quantitative education. Their comprehensive curriculum combines theoretical foundations with practical, real-world applications.

**Learn more at**: https://www.wqu.edu/

## Next Steps

1. Run data cleaning operations on the dataset
2. Perform exploratory data analysis
3. Build visualizations for key insights
4. Create predictive models for price estimation
5. Generate summary report with findings

## License

This project is part of the Data-science repository.

## Author

madhavaai

---

**Last Updated**: June 9, 2026
