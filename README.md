# 🏠 Mexico Real Estate Market Analysis

An exploratory data analysis (EDA) of residential real estate listings across Mexico. This project walks through a complete data workflow — from cleaning three messy, inconsistently-formatted source files into a single tidy dataset, to uncovering what actually drives property prices across different states and property types.

---

## 📋 Overview

The goal of this analysis is to answer a practical question: **what makes a property expensive in Mexico, and where is the best value?**

To get there, the notebook:

1. **Consolidates three separate datasets** with different formats and currencies into one clean, analysis-ready table.
2. **Explores the distribution** of prices and property sizes, and how they vary by location and property type.
3. **Engineers a `price_per_m²` feature** to compare value on an apples-to-apples basis across listings of different sizes.
4. **Quantifies the relationships** between area, location, property type, and price using correlation and variance analysis.

---

## 🗂️ Dataset

The analysis combines three CSV files of Mexican real estate listings, each with its own quirks:

| File | Key cleaning challenge |
|------|------------------------|
| `mexico-real-estate-1.csv` | Prices stored as strings with `$` and `,` (e.g. `"$67,965.56"`) |
| `mexico-real-estate-2.csv` | Prices in Mexican pesos (`price_mxn`), converted to USD at the 2014 rate of ~19 MXN/USD |
| `mexico-real-estate-3.csv` | Combined `lat-lon` field and a pipe-delimited `place_with_parent_names` field needing to be parsed into `lat`, `lon`, and `state` |

After cleaning, all three are concatenated into a single dataset with consistent columns: `property_type`, `state`, `lat`, `lon`, `area_m2`, and `price_usd`.

---

## 🔍 Analysis Highlights

- **Distribution analysis** — Histograms reveal a heavily right-skewed price distribution, which motivated outlier trimming (5th–90th percentile) for clearer visualizations.
- **Geographic & categorical comparison** — Boxplots break down prices by property type and by state to surface where the market is most and least expensive.
- **Area vs. price relationship** — Scatter plots with regression trendlines (overall and faceted by top states) quantify how strongly size predicts price.
- **Correlation deep-dive** — Correlation is computed globally, then broken out *per state* and *per property type* to show that the size–price relationship is far from uniform across the country.
- **Variance decomposition** — A between-state vs. within-state variance breakdown estimates how much of a property's price is explained by *where* it is versus other factors.
- **Value analysis (`price_per_m²`)** — The engineered price-per-square-meter metric identifies which states and property-type combinations offer the most and least value.

---

## 🛠️ Tech Stack

- **Python 3**
- **pandas** — data cleaning, method chaining, groupby aggregation
- **Matplotlib** — histograms, boxplots, scatter plots
- **Seaborn** — regression plots and correlation heatmaps

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas matplotlib seaborn jupyter
```

### Running the notebook

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```
2. Place the three source CSV files in a `data/` directory (see [Dataset](#️-dataset)).
3. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook
   ```

> **Note:** The original notebook was developed in Google Colab and references `/content/` paths. If you're running locally, update the file paths to point to your `data/` directory.

---

## 🙏 Acknowledgments

This project is based on coursework from **[WorldQuant University (WQU)](https://www.wqu.edu/)** and their **Applied Data Science Lab** program.

I'm sincerely grateful to WQU for offering this education **free of charge** and for designing a hands-on curriculum that teaches data science through real, practical projects rather than toy examples. The data cleaning patterns, method-chaining style, and analytical framing in this notebook were all learned through their program. Their commitment to making high-quality, applied data science education accessible to learners around the world is genuinely something special, and this repository exists thanks to that work.

If you're interested in learning data science, I can't recommend their programs enough: **[wqu.edu](https://www.wqu.edu/)**

---

## 📝 Note

This repository represents my own work completed and adapted while learning through the WQU Applied Data Science Lab. It is shared for portfolio and educational purposes.
