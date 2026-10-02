# 📊 Marketing & Product Performance Dashboard (Power BI)

An interactive Power BI dashboard that analyzes marketing campaign performance across social media platforms. It tracks spend, revenue, profit, ROI, clicks and conversions, and connects campaign results to customer behavior (subscription tier and post-refund satisfaction).

## 🎯 Project Goals

- Measure how efficiently marketing budget turns into revenue and profit
- Compare performance across platforms (Facebook, Instagram, TikTok, Snapchat)
- Track trends over time (monthly and yearly)
- Identify high-ROI campaigns
- Understand how subscription tier and customer satisfaction relate to revenue and conversions

## 🗂️ Dataset

**File:** `marketing_and_product_performance.csv`
**Size:** ~10,000 records covering roughly 4 years of daily data

| Group | Columns |
|---|---|
| Campaign | `Campaign_ID`, `Date`, `Platform`, `Common_Keywords` |
| Spend & results | `Budget`, `Clicks`, `Conversions`, `Revenue_Generated`, `ROI` |
| Product & sales | `Product_ID`, `Units_Sold`, `Bundle_ID`, `Bundle_Price`, `Flash_Sale_ID`, `Discount_Level` |
| Customer | `Customer_ID`, `Subscription_Tier`, `Subscription_Length`, `Customer_Satisfaction_Post_Refund` |

## 🧹 Data Preparation (Power Query)

- Loaded the CSV source and promoted headers
- Set correct data types (text, date, whole number, decimal)
- Removed 7 empty/unnamed columns created by the CSV export
- Used Power BI's auto date hierarchy (Year / Quarter / Month / Day) for time analysis

## 🧮 DAX Measures

All measures live in a dedicated `Measures table`.

| Measure | Logic | Meaning |
|---|---|---|
| Total Revenue | `SUM(Revenue_Generated)` | Total revenue generated |
| Total Budget | `SUM(Budget)` | Total marketing spend |
| Profit | `[Total Revenue] - [Total Budget]` | Revenue minus spend |
| Profit Margin | `[Profit] / [Total Revenue]` | Share of revenue kept as profit |
| ROAS | `[Total Revenue] / [Total Budget]` | Return on ad spend |
| Average ROI | `AVERAGE(ROI)` | Mean campaign ROI |
| CPC | `[Total Budget] / [Total Clicks]` | Cost per click |
| CPR (cost per result) | `[Total Budget] / [Total Conversions]` | Cost per conversion |
| Conversion Rate | `[Total Conversions] / [Total Clicks]` | Clicks that convert |
| Revenue per Click | `[Total Revenue] / [Total Clicks]` | Revenue earned per click |
| Revenue per Conversion | `[Total Revenue] / [Total Conversions]` | Average value of a conversion |
| Number of Campaigns | `DISTINCTCOUNT(Campaign_ID)` | Unique campaigns |
| High ROI Campaigns | Campaigns with `ROI > 3` | Top-performing campaigns |
| Customer Satisfaction | `AVERAGE(Customer_Satisfaction_Post_Refund)` | Mean satisfaction score |
| Life Time Value | Revenue summed per `Customer_ID` | Customer-level value |
| Total Clicks / Conversions / Units Sold | `SUM(...)` | Base volume metrics |

## 📑 Dashboard Pages

**1. Overview (KPI summary)**
KPI cards for Average ROI, CPC, cost per result, conversion rate, revenue per click, revenue per conversion, profit, number of campaigns and high-ROI campaigns. Includes a platform comparison of budget vs. revenue vs. profit and a monthly trend line.

**2. Marketing Dashboard (main view)**
- Cards: total revenue, total budget, total conversions, number of campaigns, average ROI
- Donut chart: profit share by platform
- Column chart: conversions by platform
- Bar chart: conversions by subscription tier
- Line chart: revenue, budget and profit by month
- Funnel: clicks → conversions → units sold
- **Year slicer** to filter the whole page

**3. Efficiency & Customer Insights**
- Cards: ROAS, customer satisfaction, profit margin, CPC, revenue per conversion
- Revenue by subscription tier
- Revenue by post-refund customer satisfaction
- ROI by campaign
- Monthly clicks trend
- Year slicer

## 🛠️ Tools & Skills Demonstrated

- **Power BI Desktop**: report design, slicers, funnel/donut/line/bar visuals, custom layout
- **Power Query**: data import, type conversion, column cleanup
- **DAX**: calculated measures, `DIVIDE`, `CALCULATE`, `DISTINCTCOUNT`, `SUMX`
- **Marketing analytics**: ROI, ROAS, CPC, conversion funnel, customer lifetime value

## 🚀 How to Use

1. Download `Marketing_project.pbix`
2. Open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
3. If prompted, update the data source path to where you saved `marketing_and_product_performance.csv` (**Home → Transform data → Data source settings**)
4. Use the **Year slicer** and click chart elements to cross-filter

## 📸 Screenshots

_Add screenshots of each dashboard page here:_

...
<img width="1157" height="652" alt="marketing1" src="https://github.com/user-attachments/assets/7a086456-059d-4005-8d16-9703c5205b34" />
<img width="1157" height="655" alt="Marketing 2" src="https://github.com/user-attachments/assets/164fcb50-12f6-45d5-a8df-799d37a78f88" />


```

