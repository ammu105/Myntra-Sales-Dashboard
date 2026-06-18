# 🛍️ Myntra Sales Dashboard – Power BI Project

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Tool](https://img.shields.io/badge/Tool-Power%20BI-yellow)
![Domain](https://img.shields.io/badge/Domain-E--Commerce%20Analytics-pink)


An interactive, end-to-end Power BI dashboard built to analyze **Myntra's e-commerce sales performance**, covering revenue trends, category-wise distribution, delivery efficiency, payment behavior, and regional sales — all wrapped in a clean, modern UI with a data-driven storytelling approach.

## Business Problem

E-commerce businesses generate massive volumes of transactional data daily — but raw data alone doesn't drive decisions. Myntra's stakeholders (hypothetically) needed a single, centralized view to answer:

- Which product categories are driving the most revenue?
- How are sales trending month-over-month and day-over-day?
- Which cities/regions are top performers?
- How efficient is the delivery process (on-time vs. late vs. cancelled)?
- Which payment methods do customers prefer?
- Where should discounting strategy be adjusted by category?

This dashboard was built to answer all of these questions through a **single interactive Power BI report**.

## Myntra Sales Dashboard Screenshot
![Myntra Sales Dashboard](https://github.com/ammu105/Myntra-Sales-Dashboard/blob/main/Myntra%20Dashboard%20Picture.png)

## 📊 Key Performance Indicators (KPIs)

| KPI | Description |
|---|---|
| **Total Revenue** | Sum of all order values within the selected date/filter range |
| **Total Products Sold** | Total quantity of items sold |
| **Total Customers** | Count of unique customers |
| **Avg Customer Rating** | Average product/service rating given by customers |
| **On-Time Delivery %** | Percentage of orders delivered within the expected timeframe |
| **Late Delivery %** | Percentage of orders delivered past the expected date |
| **Cancelled Orders %** | Percentage of orders cancelled before fulfillment |
| **Avg Discount by Category** | Average discount percentage applied per product category |

---

## 💡 Key Business Insights

📈 **Revenue Performance** — Strong overall revenue generated across the selected date range, with **Home & Living** emerging as the top-performing category.

⭐ **Customer Satisfaction** — Maintained a healthy average customer rating, indicating consistent service quality.

📅 **Seasonality** — **January** recorded the highest revenue month, suggesting a strong post-holiday/new-year shopping spike — a useful signal for planning future promotional campaigns.

💳 **Payment Behavior** — **UPI** emerged as the most preferred payment method, reflecting the broader digital payment adoption trend in Indian e-commerce.

🚚 **Delivery Efficiency** — Achieved a **87% On-Time Delivery Rate**, with **13% Late Deliveries** and a small fraction of cancelled orders — highlighting an area for potential logistics optimization.

🏙️ **Regional Performance** — **Chennai** recorded the highest order volume among tracked cities, with strong contributions also coming from Kolkata, Delhi, Kochi, and Lucknow — showing solid performance across South and North Indian metros.

## 🧮 DAX Measures Used

Examples of core DAX measures built for this dashboard:

```DAX

>> Total Revenue = sum('📦 Raw Sales Data'[Revenue (₹)])

>> Total Sold Products = sum('📦 Raw Sales Data'[Quantity])

>> Total Customers = COUNT('📦 Raw Sales Data'[Customers])

>> Avg Customers Rating = AVERAGE('📦 Raw Sales Data'[Customer Rating])

>> On-timeOrders % = 
                    DIVIDE(
                          CALCULATE(
                             COUNTROWS('📦 Raw Sales Data'),
                                '📦 Raw Sales Data'[Delivered on time or delayed] = "On-time"
                             ),
                           COUNTROWS('📦 Raw Sales Data'),
                           0
                         )


>> Late Orders % = 
                 DIVIDE(
                    CALCULATE(
                       COUNTROWS('📦 Raw Sales Data'),
                            '📦 Raw Sales Data'[Delivered on time or delayed] = "Late"
                        ),
                     COUNTROWS('📦 Raw Sales Data'),
                     0
                 )

>> Cancelled Order = 
              DIVIDE(
                CALCULATE(
                    COUNTROWS('📦 Raw Sales Data'),
                       '📦 Raw Sales Data'[Is Returned] = "Yes"
                   ),
                   COUNTROWS('📦 Raw Sales Data'),
                   0
                )           

```
---
## 🔗 Data Model

The dashboard is built on a simple **two-table relational model**:

```
   Sales Table  ──────────────▶  Category Table
 (Fact: orders,                (Reference: Category
  revenue, customers,           Name/ID + Image URL
  delivery, payment)            for category visuals)
```
## 🧠 Skills Demonstrated

This project helped strengthen the following skills:

- **Business Intelligence (BI) Reporting**
- **Data Analysis & Exploratory Data Analysis (EDA)**
- **KPI Development & Tracking**
- **DAX (Data Analysis Expressions)**
- **Power Query (ETL — Extract, Transform, Load)**
- **Data Modeling & Relationship Design**
- **Dashboard Design & UI/UX for Analytics**
- **Data Storytelling & Insight Communication**
---
## ▶️ How to Use This Project

1. Clone or download this repository.
2. Open the `.pbix` file in **Power BI Desktop** (latest version recommended).
3. If prompted, update the data source path to point to your local dataset copy.
4. Use the **Date, City, Category, and Payment Method** slicers on the report to explore the data interactively.
5. Navigate between report pages using the left-hand navigation menu (Sales, Orders, Category, Delivery, Payment, Marketing Analytics, Reports).

---

## 🤝 Connect With Me

💬 Feedback and suggestions are always welcome — feel free to reach out or open an issue if you'd like to discuss this project, suggest improvements, or collaborate on similar data analytics work.

---

⭐ *If you found this project useful or interesting, consider giving it a star!*
