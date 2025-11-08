# ECommerce-Sales-DashBoard
🎯 Project Objective

The purpose of this Tableau project is to analyze sales performance, market contribution, and customer trends using Key Performance Indicators (KPIs).
It allows stakeholders to:

Track year-over-year progress

Monitor target achievements

Evaluate market share and customer growth

Identify areas needing improvement in sales and profit

🧮 Data Source and Structure
Data Source:

The workbook uses a Federated Data Source (seen in the .twb file).
This means multiple data tables (like Orders, Sales, Customers, Markets) are joined or blended together in Tableau.

Typical fields used:

Order Date

Sales

Profit

Quantity

Customer ID

Market / Region

Category

Sub-Category

Target (optional or calculated)

Data Model:

The data is structured at a transaction level, aggregated into summaries for each market, category, or month — depending on the worksheet.

📈 KPIs Used in the Project (Detailed Explanation)
🧩 1. Sales KPI

Purpose:
To track total sales performance over time and compare against targets or previous periods.

Metrics Used:

SUM(Sales) — Total revenue generated.

YTD Sales — Sales from the start of the year to the current date.

PYTD Sales — Previous Year-To-Date sales for comparison.

Calculated Fields Example:

YTD Sales:

IF YEAR([Order Date]) = YEAR(TODAY()) THEN [Sales] END


PYTD Sales:

IF YEAR([Order Date]) = YEAR(TODAY()) - 1 THEN [Sales] END


% Growth:

([YTD Sales] - [PYTD Sales]) / [PYTD Sales]


Visualization Used:

KPI card showing total sales amount and percentage growth.

Green/Red color indicator to show increase or decrease.

Optionally a sparkline or bar trend by month.

Insights:

Measures revenue growth over time.

Highlights performance improvements vs. last year.

Indicates whether the company is meeting its sales targets.

💰 2. Profit KPI

Purpose:
To evaluate business profitability and cost efficiency.

Metrics Used:

SUM(Profit) — Total profit across transactions.

Profit Margin — Profit as a percentage of total sales.

Calculated Fields:

Profit Margin:

[Profit] / [Sales]


Profit Target Achievement:

[Profit] / [Target Profit]


(if target field exists)

Visualization Used:

KPI card with profit value and profit margin.

Conditional color formatting:

Green → Profit positive and above target.

Red → Profit below target or negative.

Bar chart by category or market for comparative profit distribution.

Insights:

Identifies which markets or product categories are most profitable.

Helps management focus on high-margin products.

Detects cost inefficiencies or loss-making regions.

📦 3. Order Quantity KPI

Purpose:
To monitor the number of units sold or orders processed — an indicator of demand volume.

Metrics Used:

SUM(Quantity) — Total number of items ordered.

Average Quantity per Order — Optional metric for performance consistency.

Calculated Fields:

Order Growth %:

([Current Year Orders] - [Previous Year Orders]) / [Previous Year Orders]


Visualization Used:

Numeric KPI tile showing total quantity sold.

Trend line for month-over-month order movement.

Insights:

Indicates sales volume momentum.

Helps understand demand trends over time.

Useful for inventory planning and forecasting.

🌎 Additional Analytical Worksheets
📊 4. Category Wise YTD vs PYTD Sales

Purpose:
To compare current and previous year sales by product category.

Metrics:

SUM(Sales) grouped by Category

YTD Sales and PYTD Sales comparison

Visualization:

Dual-bar chart (Current Year vs Previous Year)

Label showing % change for each category

Insights:

Highlights which categories are performing better or worse than last year.

Supports product strategy and category-level forecasting.

🌐 5. Market Share by Sales

Purpose:
To analyze how much each market contributes to total sales.

Metrics:

SUM(Sales) grouped by Market

Market Share % = Sales of Market / Total Sales * 100

Visualization:

Donut or Pie Chart showing contribution %

Optional map visualization by region

Insights:

Identifies dominant markets.

Helps in geographical performance analysis.

Aids decision-making for regional strategy and investments.

👥 6. Market Wise Customer Acquisition Per Month

Purpose:
To track how many new customers are acquired each month in each market.

Metrics:

COUNTD(Customer ID) — Distinct customers

First Purchase Date to identify new customers

Calculated Field Example:

IF [Order Date] = { FIXED [Customer ID] : MIN([Order Date]) } THEN "New Customer" ELSE "Existing Customer" END


Visualization:

Line chart showing monthly customer acquisition trend.

Color by market for visual differentiation.

Insights:

Monitors business growth through customer acquisition.

Shows seasonal or campaign-driven customer spikes.

Useful for marketing and retention strategy.

📊 Dashboard — “Dashboard 1”

Purpose:
To bring all KPIs and visualizations together for a single executive overview.

Contents:

Top section: KPI tiles (Sales, Profit, Orders)

Middle section: Category-wise and Market-wise visuals

Bottom: Monthly customer acquisition trends

Filters:

Market / Region

Year

Product Category

User Experience:

Clean, interactive interface with filters for quick insights.

Allows comparison across time, region, and product category.

Provides a summarized performance snapshot for business meetings.

🧠 Key Takeaways

Combines operational and strategic KPIs into a single dashboard.

Enables data-driven insights into revenue, profit, and customer performance.

Highlights growth opportunities and underperforming areas.

Ideal for sales managers, business analysts, and executives.
