# Blinkit-Sales-Analysis-Python
Python-based Blinkit sales analysis project using Pandas, NumPy, and Matplotlib to clean data, calculate KPIs, visualize sales patterns, and derive business insights
# Blinkit Sales Analysis using Python

Exploratory data analysis of Blinkit retail sales data using Python, Pandas and Matplotlib. The project cleans the raw data, calculates headline KPIs, and examines how sales vary by product category, fat content, outlet size, outlet location tier and outlet establishment year.

## Table of Contents

- [Project Overview](#project-overview)
- [Problem Statement and Objectives](#problem-statement-and-objectives)
- [Dataset](#dataset)
- [Tools and Technologies](#tools-and-technologies)
- [Workflow](#workflow)
- [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Key Findings](#key-findings)
- [Visualizations](#visualizations)
- [Recommendations](#recommendations)
- [Project Structure](#project-structure)
- [How to Run Locally](#how-to-run-locally)
- [Skills Demonstrated](#skills-demonstrated)
- [Limitations and Future Improvements](#limitations-and-future-improvements)
- [Author](#author)

## Project Overview

This project analyses 7,060 cleaned sales records (from 8,523 raw records) to understand which product categories and outlet types contribute most to sales. It covers data cleaning, KPI calculation, group-wise aggregation and chart-based analysis in a single Jupyter Notebook.

**Headline KPIs (after cleaning)**

| KPI | Value |
|---|---|
| Total Sales | 997,159.22 |
| Average Sales per record | 141.24 |
| Records analysed | 7,060 |
| Average Rating | 3.97 |

**Project files**

- Notebook: [notebook/blinkit_sales_analysis.ipynb](notebook/blinkit_sales_analysis.ipynb)
- PDF export of the notebook: [report/blinkit_sales_analysis_notebook_export.pdf](report/blinkit_sales_analysis_notebook_export.pdf)

## Problem Statement and Objectives

A retail business needs to know where its sales come from before deciding on stock, promotions and outlet strategy. This project answers:

1. What are the total sales, average sales per record and average rating?
2. Which product categories generate the most and the least sales?
3. How do sales differ between Low Fat and Regular items?
4. How do sales differ by outlet size, outlet location tier and outlet establishment year?

## Dataset

- **File:** `blinkit_data.csv`
- **Source:** Not specified
- **Size:** 8,523 rows and 12 columns (raw); 7,060 rows after cleaning
- **Time period and currency of `Sales`:** Not specified
- **Availability:** The dataset file is not included in this repository. See [data/README.md](data/README.md) for how to add it.

| Column | Notes from the notebook |
|---|---|
| Item Identifier | Product ID (e.g. FDX32) |
| Item Type | 16 categories, e.g. Fruits and Vegetables, Snack Foods, Household |
| Item Fat Content | Raw data had 5 label variants (see cleaning section) |
| Item Weight | Numeric; 1,463 missing values |
| Item Visibility | Numeric; not analysed |
| Outlet Identifier | Outlet ID (e.g. OUT049) |
| Outlet Establishment Year | 8 distinct years after cleaning (2000 to 2022) |
| Outlet Size | High, Medium, Small |
| Outlet Location Type | Tier 1, Tier 2, Tier 3 |
| Outlet Type | Present; not analysed |
| Sales | Numeric sales value |
| Rating | Numeric rating |

## Tools and Technologies

- Python
- Pandas for cleaning and aggregation
- Matplotlib for visualization
- Jupyter Notebook
- NumPy and Seaborn are imported in the notebook but not used in the analysis steps

## Workflow

1. Load the raw CSV and inspect it (`head`, `columns`, `shape`, missing values).
2. Remove rows with missing values.
3. Standardise inconsistent `Item Fat Content` labels.
4. Calculate KPIs: total sales, average sales, record count, average rating.
5. Aggregate sales with `groupby` by fat content, item type, outlet establishment year, outlet size and outlet location type.
6. Visualize each aggregation and interpret the results.

## Data Cleaning and Preprocessing

**Missing values.** Only `Item Weight` had missing values (1,463 rows). These rows were dropped with `dropna()`, reducing the dataset from 8,523 to 7,060 rows. `Item Weight` is not used in any later analysis step.

**Inconsistent labels.** `Item Fat Content` contained five spellings for two categories:

| Raw value | Standardised to |
|---|---|
| Regular, reg | Regular |
| Low Fat, low fat, LF | Low Fat |

## Exploratory Data Analysis

- Total sales split by fat content (pie chart)
- Record count and total sales by item type (bar chart)
- Total sales by outlet establishment year (line chart)
- Total sales by outlet size (bar chart)
- Total sales by outlet location type (pie chart)

## Key Findings

All figures are totals computed on the cleaned data of 7,060 rows. Percentages are calculated from the totals printed in the notebook.

| Area | Finding |
|---|---|
| Item type | Fruits and Vegetables (147,188.96) and Snack Foods (144,949.13) are the top two categories, together about 29% of total sales. Household (113,210.14) is third. |
| Item type | Seafood (7,397.56) and Breakfast (12,696.19) are the lowest, together about 2% of total sales. |
| Item type | The three highest-selling categories also have the most records (1,019, 988 and 759), and the lowest have the fewest (Seafood 51, Breakfast 89). Category totals appear to track how many records each category has. |
| Fat content | Low Fat accounts for 644,516.73 (64.6%) and Regular for 352,642.49 (35.4%). |
| Outlet size | Medium (377,181.05, 37.8%) and Small (370,986.59, 37.2%) are close; High is lower at 248,991.58 (25.0%). |
| Outlet location | Tier 2 leads with 393,150.64 (39.4%), then Tier 3 with 341,418.35 (34.2%) and Tier 1 with 262,590.23 (26.3%). |
| Establishment year | Seven of the eight establishment years show similar totals (about 129,000 to 133,000). 2011 is much lower at 78,131.56, roughly 40% below the average of the other seven years. The cause was not investigated. |

## Visualizations

| | |
|---|---|
| ![Sales by Fat Content](images/01_sales_by_fat_content_pie.png) | ![Sales by Item Type](images/02_sales_by_item_type_bar.png) |
| Sales by fat content | Sales by item type |
| ![Sales by Outlet Size](images/04_sales_by_outlet_size.png) | ![Sales by Outlet Location Type](images/05_sales_by_outlet_location_type.png) |
| Sales by outlet size | Sales by outlet location type |

![Sales by Outlet Establishment Year](images/03_sales_by_outlet_establishment_year.png)


## Author

**Subhakar🙎🏼‍♂️**
