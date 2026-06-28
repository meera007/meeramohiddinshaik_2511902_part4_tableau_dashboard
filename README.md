# Sales Dashboard Dataset – Data Inspection

## Overview
This dataset contains transactional sales data including customer details, product information, shipping data, and performance metrics such as sales and profit.

---

## Data Structure

### Date Fields
- `order_date` (converted from Excel serial format)
- `ship_date` (converted from Excel serial format)

---

### Geographic Fields
- `region` (North, South, East, West)
- `state`
- `city`

---

### Categorical Fields (Dimensions)
- `order_id`
- `customer_id`
- `customer_segment` (Consumer, Corporate, Home Office)
- `category` (Furniture, Technology, Office Supplies)
- `sub_category`
- `product_name`
- `ship_mode` (First Class, Second Class, Standard Class, Same Day)
- `campaign_channel` (Organic, Paid, Social, Referral, Email)

---

### Numerical Measures
- `sales` (revenue per order)
- `profit` (can be negative indicating loss)
- `quantity`
- `discount` (percentage applied)
- `delivery_days`
- `customer_rating` (range approx. 1–5)

---

### Binary Field
- `return_flag`
  - 0 = Not returned
  - 1 = Returned

---

## Data Assumptions

1. Date fields (`order_date`, `ship_date`) are stored as Excel serial numbers and must be converted to proper date formats.
2. `profit` includes negative values representing losses on sales.
3. `discount` is represented as a decimal (e.g., 0.2 = 20%).
4. `delivery_days` represents the difference between ship date and order date.
5. `customer_rating` is assumed to be on a 1–5 scale.
6. `return_flag` is binary and indicates whether an order was returned.
7. Geographic fields are based on Indian locations and may require mapping roles in Tableau.

---

## Notes for Tableau
- Convert date fields using calculated fields:






=============================================

# Business Insights Dashboard Project

---

## 1. Business Problem Summary

The objective of this project is to analyze sales, profitability, customer behavior, and operational efficiency using transactional data. The goal is to identify key performance drivers, uncover risks such as high returns or low margins, and provide actionable insights to support business decision-making.

---

## 2. Dataset Description

The dataset contains transactional sales data with the following components:

- Order details: order_id, order_date, ship_date  
- Customer information: customer_id, customer_segment  
- Product information: category, sub_category, product_name  
- Geography: region, state, city  
- Sales metrics: sales, profit, quantity, discount  
- Operational data: ship_mode, delivery_days  
- Customer feedback: customer_rating  
- Marketing channel: campaign_channel  
- Return indicator: return_flag  

The data represents sales transactions across multiple regions and product categories.

---

## 3. Tableau Workbook Description

The Tableau workbook contains multiple sheets and one executive dashboard designed to provide a comprehensive overview of business performance.

The dashboard integrates:
- Sales trends over time  
- Regional performance analysis  
- Category and sub-category profitability  
- Customer segment comparison  
- Discount vs profit relationship  
- Shipping performance analysis  
- Return analysis  

These views are connected through filters and interactions to enable dynamic exploration.

---

## 4. Calculated Fields Created

The following calculated fields were created:

- **Profit Margin** = Profit / Sales  
- **Cost** = Sales - Profit  
- **Average Order Value** = Sales / Number of Orders  
- **Return Rate** = Returned Orders / Total Orders  
- **Shipping Delay Bucket** = Categorized delivery days:
  - Same Day  
  - Fast (1–2 days)  
  - Standard (3–5 days)  
  - Delayed (6+ days)  

Additional fields:
- Profitability Flag (Profit vs Loss)  
- Discount Category (Low/High/No Discount)  
- Customer Rating Bucket  

---

## 5. Dashboard Components

The executive dashboard includes:

### KPI Cards
- Total Sales  
- Total Profit  
- Profit Margin  
- Average Order Value  
- Return Rate  

### Visualizations
- Sales Trend (Line Chart)  
- Regional Performance (Map/Bar Chart)  
- Category Profitability (Bar Chart)  
- Customer Segment View (Bar Chart)  
- Discount vs Profit (Scatter Plot)  
- Shipping Performance (Bar Chart)  
- Return Analysis (Bar Chart/Highlight Table)  

---

## 6. Filters and Interactions Used

### Filters
- Region  
- Category  
- Customer Segment  
- Order Date  
- Ship Mode  
- Campaign Channel  

Filters are applied globally across all views and are displayed as dropdowns for usability.

### Interaction
- Clicking on a region (map) filters all other charts  
- Enables dynamic, drill-down analysis  

---

## 7. Key Business Insights

- Sales are growing overall but show seasonal fluctuations  
- Western and Northern regions drive the highest revenue  
- Some product categories generate high sales but low profit  
- Corporate and Consumer segments are key revenue drivers  
- High discounts negatively impact profitability  
- Faster delivery improves sales performance  
- Certain categories and regions have higher return rates  
- Loss-making products and over-discounting represent business risks  

---

## 8. Dashboard Story Summary

The dashboard highlights a business that is achieving strong revenue growth but facing profitability challenges. While high-performing regions and categories provide growth opportunities, issues such as excessive discounting, shipping delays, and product returns impact margins.

By optimizing pricing strategies, improving operational efficiency, and focusing on high-margin products, the business can enhance profitability while sustaining growth.

---

## 9. Assumptions and Limitations

### Assumptions
- Dates were converted from Excel serial format  
- Discount values are represented as decimals (e.g., 0.2 = 20%)  
- Return_flag represents binary return status  
- Profit includes all necessary cost components  

### Limitations
- No detailed cost breakdown beyond profit  
- No information on return reasons  
- External factors (market trends, competition) are not included  
- Customer lifetime value is not available  

---

## 10. Screenshots Included

├── screenshots/
│   ├── full_dashboard.png
│   ├── sales_trend_view.png
│   ├── regional_performance_view.png
│   ├── category_profitability_view.png
│   └── filter_interaction_view.png