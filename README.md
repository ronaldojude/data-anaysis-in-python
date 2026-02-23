## Sales Data Analysis using Python (Pandas & Matplotlib)
# Project Overview

This project performs exploratory data analysis (EDA) on a sales dataset using Python, Pandas, and Matplotlib.
The goal is to analyze sales performance, profit trends, customer segments, regions, and time-based insights from the dataset.

# The project demonstrates:

Data cleaning & preprocessing

Date-time transformation

Filtering & conditional analysis

Groupby operations

Sales & profit trend visualization

 # Technologies Used

Python 

Pandas

Matplotlib

Jupyter Notebook

# Dataset Used

The dataset contains order-level sales data with the following columns:

Order Date

Ship Date

Ship Mode

Sales

Profit

Discount

Quantity

Region

Segment

Dataset file used: orders.csv

## Project Workflow
# Data Loading
import pandas as pd
df = pd.read_csv("orders.csv")
# Data Exploration

df.head()

df.tail()

df.info()

df.describe()

df.sample()

# Data Cleaning & Date Formatting

Converted columns to datetime format:

df["Order Date"] = pd.to_datetime(df["Order Date"], errors="coerce")
df["Ship Date"] = pd.to_datetime(df["Ship Date"], errors="coerce")
# Data Filtering Examples

High sales (> 1000)

Profitable orders (Profit > 0)

High discount (> 0.9)

High quantity (> 4)

Region-based filtering (South)

Example:

df[df["Sales"] > 1000]
## Groupby Analysis
# Total Sales by Region
df.groupby("Region")["Sales"].sum()
# Total Profit by Segment
df.groupby("Segment")["Profit"].sum()
# Profit Summary Statistics
df.groupby("Segment")["Profit"].describe()
## Time-Based Analysis
# Monthly Sales
monthly_sales = df.groupby(df["Order Date"].dt.month)["Sales"].sum()
# Daily Profit
daily_profit = df.groupby(df["Order Date"].dt.day)["Profit"].sum()
## Data Visualization
# Monthly Sales Trend
monthly_sales.plot()
# Daily Profit Trend
daily_profit.plot()
# Yearly Sales (Bar Chart)
yearly_profit.plot(kind="bar")
# Yearly Sales (Pie Chart)
yearly_profit.plot(kind="pie")
## Key Insights

Sales performance varies significantly by region.

Certain segments generate higher profit.

Monthly trends show seasonal sales behavior.

High discounts impact profit margins.

Quantity and discount levels influence overall revenue.

## How to Run This Project

Install Python (3.x recommended)

Install required libraries:

pip install pandas matplotlib

Place orders.csv in your project folder.

Open Jupyter Notebook:

jupyter notebook

Run the notebook file.

## Project Structure
Sales-Data-Analysis/
│
├── orders.csv
├── sales_analysis.ipynb
└── README.md
## Learning Outcomes

Practical understanding of Pandas

Real-world dataset analysis

Data filtering techniques

Groupby operations

Data visualization using Matplotlib

Time-series data handling

## Future Improvements

Add Seaborn visualizations

Create interactive dashboard (Power BI / Streamlit)

Perform predictive sales forecasting

Add correlation heatmaps

Build a machine learning sales prediction model

 ## Author

Ronaldo Jude
Aspiring Data Analyst | Python Enthusiast

# If You Like This Project

Give it a ⭐ on GitHub and feel free to fork or contribute!
