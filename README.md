Project Workflow

1. Data Collection — Import and validate the retail sales dataset for completeness.

2. Data Cleaning — Handle missing values, remove duplicates, standardize column formats, convert data types.

3. Exploratory Data Analysis (EDA) — Sales trend, profitability, category-wise, and customer behavior analysis using Pandas, Matplotlib, and Seaborn.

4. SQL Analysis — Revenue calculations, top-product identification, customer insights, regional performance queries.

5. Dashboard Development (Power BI / Tableau) — KPI cards, interactive filters, trend visualizations.

6. Streamlit Web App — A config-driven, self-serve version of the dashboard (see architecture below).

7. Automated Reporting — Multi-sheet Excel exports via openpyxl, scheduled for delivery to stakeholders.

Streamlit App Architecture

The web app renders dashboard widgets dynamically from a configuration table rather than hardcoding charts, which makes it easy to add, reorder, or hide widgets without touching app code.

Streamlit App Architecture

The web app renders dashboard widgets dynamically from a configuration table rather than hardcoding charts, which makes it easy to add, reorder, or hide widgets without touching app code.

dashboard_widgets schema:

Field        Type        Description 
dashboard_id reference    Links the widget to a parent dashboard
widget_type  picklist     Line Chart, Table, Pie Chart, Bar Chart, Heatmap, Map, Card
title        text         Widget display title
data_source  picklist     Sales Transactions, Region Performance, Revenue Trends, Top Products, Product Performance
filter_criteria  text     Filter expression applied to the data source
visualization_config JSON/text  Chart-specific rendering options
position    number        Sort order on the dashboard grid
is_visible  boolean     Toggles whether the widget renders

This config-driven approach is what powers the "dynamic filters" and self-serve experience described above — stakeholders (or the app maintainer) can adjust what's shown on the dashboard by editing widget records rather than redeploying code.

Repository Structure

Retail-Sales-Analytics-Dashboard
│
├── data
│   └── retail_sales.csv
│
├── notebooks
│   └── sales_analysis.ipynb
│
├── sql
│   └── sales_queries.sql
│
├── dashboard
│   └── retail_dashboard.pbix
│
├── app
│   ├── streamlit_app.py
│   └── widgets_config.py
│
├── reports
│   └── export_to_excel.py
│
├── images
│   └── dashboard_preview.png
│
├── requirements.txt
├── README.md
└── LICENSE

Getting Started

# Clone the repo
git clone https://github.com/Vidyashree-L/Retail-Sales-Analytics-Dashboard.git
cd Retail-Sales-Analytics-Dashboard

# Install dependencies
pip install -r requirements.txt

# Run the Streamlit app
streamlit run app/streamlit_app.py

Sample Insights Generated

Identified the highest revenue-generating product categories.
Determined regions contributing maximum profit.
Analyzed customer purchasing patterns and repeat-purchase behavior.
Evaluated monthly sales growth trends.
Measured overall business performance against core KPIs.

Skills Demonstrated

Data Cleaning · Exploratory Data Analysis (EDA) · SQL Querying · Data Visualization · Dashboard Development · Business Intelligence · Statistical Analysis · Web App Development · Reporting Automation

Future Enhancements

Sales forecasting using machine learning
Customer churn prediction
Real-time data integration
Cloud deployment (AWS)


Author

Vidya Shree L
Aspiring Data Analyst | Python | SQL | Power BI | Data Science
