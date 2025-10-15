 # Retail Sales and Profit Analysis Dashboard (Power BI)

## Project Overview  
This Power BI report analyzes retail performance across three product categories — **Beauty**, **Clothing**, and **Electronics** — to uncover insights on **sales trends**, **profitability**, **pricing impact**, and **customer spending patterns**.

The goal is to help stakeholders understand:  
- How revenue and costs interact to drive profitability  
- Which product categories perform best  
- How pricing influences profit margins  
- How much customers spend on average per order  

---

## Business Problem
Stakeholders were facing challenges in understanding:
- Whether total sales are consistently exceeding **Cost of Goods Sold (COGS)**  
- Which product categories contribute most to **total profit and revenue**  
- How **pricing** affects **profit margins**  
- The **average order value (AOV)** per customer transaction  

This dashboard solves these problems by consolidating KPIs and visual analytics into one interactive Power BI report.

---

## Dataset Summary
The dataset includes transactional retail data with the following key fields:

| Column | Description |
|--------|--------------|
| `category` | Product type (Beauty, Clothing, Electronics) |
| `sale_date` | Date of transaction |
| `quantity` | Units sold |
| `price_per_unit` | Selling price per product |
| `total_sale` | Total sale amount (Revenue per transaction) |
| `cogs` | Cost of goods sold |
| `profit` | Revenue - COGS |
| `profit_margin` | Profit ÷ Revenue |
| `transaction_id` | Unique identifier per order |

---

## Key Visuals and Insights

---

### **1. Sales VS COGS (Profitability Trend) KPI Visual**
https://github.com/She-yii/Retail-Sales-and-Profit-Visualization/blob/fbf59eb5dc2c4e9656f57c5b550b607cfff6f30c/IMG-20251015-WA0049.jpg

#### **Challenge:**  
Management needed a single visual indicator showing whether total sales were exceeding the cost of goods sold (COGS) over time.

#### **Solution:**  
A **KPI card** compares **Total Sales** and **COGS** to evaluate profitability performance over time.

#### **Insight:**  
- Total Sales significantly exceed COGS.  
- Indicates **healthy profit margins** and **effective cost control**.

---

### **2. Total Revenue by Product Category**
https://github.com/She-yii/Retail-Sales-and-Profit-Visualization/blob/574b87baf0804b2b25aa4652ac764eb97fb271f9/IMG-20251015-WA0051.jpg

#### **Challenge:**  
Which product category contributes the most to total revenue?

#### **Solution:**  
A **bar chart** visualizes total revenue across Beauty, Clothing, and Electronics.

#### **Insight:**  
- **Electronics** leads in total revenue, followed by **Clothing**, then **Beauty**.  
- Suggests that Electronics is the top-performing category and deserves continued marketing investment.

---

### **3. Profitability by Category (Summary Table)**
![Profit Table](images/profit_table.png)

#### **Challenge:**  
The finance team wanted an overview of profit contribution by category and a quick way to track trends.

#### **Solution:**  
A **summary table** was created showing:
- Count of transactions  
- Total Profit  
- Total Revenue  
- Daily Category Trend (sparkline)

#### **Insight:**  
- **Electronics** generates the highest profit (~$788,000), followed by **Clothing** and **Beauty**.  
- All categories show stable daily sales activity, implying steady demand.

---

### **4.  Average Order Value (AOV)**
![AOV KPI](images/aov_kpi.png)

#### **Challenge:**  
The business wanted to understand average customer spending per order.

#### **Solution:**  
A KPI card was created using this DAX formula:

```DAX
AOV = DIVIDE(SUM(Sales[total_sale]), DISTINCTCOUNT(Sales[transaction_id]))
```

- `SUM(total_sale)` gives total revenue.  
- `DISTINCTCOUNT(transaction_id)` represents total unique orders.

#### **Insight:**  
- The **Average Order Value (AOV)** is $456.1.  
- Indicates customers typically spend $456 per purchase, useful for pricing and loyalty program strategies.

---

### **5. Sales Trend and Forecast**
![Sales Forecast](images/sales_forecast.png)

#### **Challenge:**  
Stakeholders wanted to visualize sales patterns over time and forecast future performance.

#### **Solution:**  
A **line chart** plots **Total Sales by Date**, enhanced with Power BI’s **forecasting tool** to predict future sales trends.

#### **Insight:**  
- Sales fluctuate periodically, with visible peaks (possibly during festive periods).  
- The forecast projects moderate growth with upper and lower confidence intervals.  
- Helps stakeholders plan inventory and marketing around sales peaks.

---

### **6. Impact of Product Pricing on Profit Margin**
![Pricing Impact](images/price_vs_profit_margin.png)

#### **Challenge:**  
Do higher prices lead to better profit margins?

#### **Solution:**  
A **scatter plot** compares **average price per unit** to **average profit margin** across product categories.

#### **Insight:**  
- There’s a **negative correlation**: higher prices slightly reduce profit margins.  
- Indicates **competitive pricing pressures**, suggesting the need for balanced pricing strategies.

---

## Key Metrics Summary

| Metric | Formula \ Description | Business Use |
|--------|----------------------|--------------|
| **Total Revenue** | SUM(total_sale) | Measures total sales performance |
| **COGS** | SUM(cogs) | Tracks cost of goods sold |
| **Total Profit** | SUM(total_sale - cogs) | Measures business profitability |
| **Profit Margin** | Profit ÷ Revenue | Evaluates cost efficiency |
| **AOV (Average Order Value)** | Total Revenue ÷ Distinct Orders | Measures customer spending pattern |
| **Category Count** | DISTINCTCOUNT(category) | Shows product diversity |

---

## Tools and Techniques Used
- **Power BI Desktop**  
- **DAX (Data Analysis Expressions)**  
- **Data Modeling and Relationships**  
- **Visual Analytics (KPI Cards, Bar Charts, Tables, Scatter Plots, Forecasting)**  

---

## Conclusion
This Power BI dashboard provides a **comprehensive view of retail sales performance**, enabling data-driven decision-making.  
It empowers stakeholders to:
- Monitor profit and cost dynamics in real time.  
- Identify top-performing categories.  
- Understand how pricing affects profitability.  
- Forecast future trends with confidence.  
