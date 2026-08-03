# 🍽️ Zomato Restaurant Dataset — Exploratory Data Analysis

An exploratory data analysis of 51,000+ Zomato restaurant listings from Bangalore,
uncovering patterns in ratings, pricing, cuisines, and restaurant types using Python.

## 📌 Overview

This project cleans and analyzes a raw Zomato dataset covering restaurants across
Bangalore to understand what drives restaurant popularity and ratings — online
ordering availability, table booking, location, cuisine type, and pricing — using
pure Python data analysis and visualization (no SQL or BI tool in this project,
by design, to demonstrate Python-based EDA skills).

**Raw Rows:** 51,717 &nbsp;|&nbsp; **After Cleaning:** 35,151 &nbsp;|&nbsp; **Avg Rating:** 3.57 / 5

## 🛠️ Tech Stack
- **Python** — Pandas, NumPy for data cleaning and manipulation
- **Matplotlib, Seaborn** — visualizations
- **Jupyter Notebook** — analysis environment

## 📂 Dataset
Raw Zomato listings with 17 original columns, including restaurant name, address,
online order availability, table booking, ratings, votes, location, restaurant
type, cuisines, and approximate cost for two people.

## 🧹 Data Cleaning
- Dropped irrelevant columns (`url`, `phone`, `listed_in(city)`, `reviews_list`, `menu_item`)
- Renamed all columns to clear, consistent uppercase labels
- Removed duplicate rows (51,717 → 35,151 rows)
- Cleaned the `RATINGS` column: stripped `/5` suffix, converted `'NEW'` and `'-'` placeholders to `0.0`, cast to float, filled missing values with the column mean (3.57), rounded to 1 decimal
- Removed non-ASCII characters from `ADDRESS`
- Filled missing `LOCATION`, `REST_EXP`, `SPECIAL_DISHES`, and `CUISINES` values using each column's mode
- Cleaned `APPROX_COST_TWO_PEOPLE`: removed comma separators, filled missing values with the median, cast to integer
- Verified zero remaining nulls across all 12 retained columns

## 🔍 Analysis & Visualizations
- Online order availability vs. restaurant count
- Table booking availability vs. restaurant count
- Ratings distribution by table booking availability (boxplot)
- Top 10 restaurant locations by count
- Ratings by location for the top 5 locations (boxplot)
- Restaurant count by serving type (Buffet, Cafes, Delivery, Pubs and bars, etc.)
- Ratings by restaurant type (boxplot)
- Distribution of approximate cost for two people
- Restaurant count by location (full breakdown)
- Most popular restaurant chains, ranked by votes-per-rating ratio

## 📈 Key Insights
- Online order availability appears linked to restaurant popularity — restaurants offering online ordering tend to have higher visibility.
- Restaurants with higher ratings generally cluster around moderate pricing rather than the most expensive listings.
- **North Indian** and **Chinese** are among the most commonly listed cuisines across Bangalore restaurants.
- Restaurant density is heavily concentrated in a small number of locations, with the top 10 areas accounting for a disproportionate share of listings.

## 📁 Project Structure
```
Zomato-EDA/
├── data/
│   └── zomato.csv
├── notebook/
│   └── zomato_eda.ipynb
└── README.md
```

## 🚀 How to Use
1. Open `notebook/zomato_eda.ipynb` in Jupyter Notebook or JupyterLab
2. Run all cells to reproduce the cleaning steps and visualizations
3. Requires: `pandas`, `numpy`, `matplotlib`, `seaborn`

## 📌 Future Enhancements
- Sentiment analysis on the `reviews_list` column (dropped in this version, but rich for NLP)
- Predictive model for restaurant rating based on cost, cuisine, and location
- Interactive dashboard (Plotly/Streamlit) for filtering by location and cuisine
