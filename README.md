# 🍽️ Zomato Data Analytics Dashboard (Power BI)

This project showcases a **Power BI dashboard** built using a **Zomato orders dataset** for end-to-end data analytics and visualization.  
The dashboard provides insights into restaurant performance, order trends, customer behavior, and delivery operations.

---

## 📊 Dashboard Overview

![Zomato Dashboard](e9fe65e9-a909-47d1-b58c-39ed778d43f1.png)

**Key KPIs Displayed:**
- **Total Orders:** 1K  
- **Total Revenue:** ₹2.22M  
- **Cancellation Rate:** 4.70%  
- **Average Order Value:** ₹2.22K  
- **Average Delivery Time:** 44.16 mins  
- **Average Rating:** 4.01  

---

## 🔍 Insights from Dashboard

- **Order Trends:** Orders peak during summer months (May–July) and decline toward year-end.  
- **Top Cuisines:** Desserts, Seafood, and Chinese lead in order volume.  
- **City Performance:** Pune and Mumbai contribute most to total orders.  
- **Payment Modes:** UPI and Wallet dominate customer preferences.  
- **Delivery Partners:** Zomato Rider and Instakart handle the majority of deliveries.

---

## 🧹 Dataset Details

The dataset contains **1,000 records** of simulated Zomato order transactions with intentionally **dirty data** for data cleaning practice.

**Columns include:**
- `order_id`, `restaurant_name`, `cuisine`, `city`
- `order_date`, `order_time`
- `customer_id`, `customer_name`
- `items_count`, `order_value`, `discount`
- `payment_type`, `rating`
- `delivery_time_mins`, `is_cancelled`
- `promo_code_used`, `delivery_partner`

**File:** [`zomato_1000_dirty.csv`](./zomato_1000_dirty.csv)

---

## 🧠 Tools & Technologies Used

- **Power BI:** Dashboard creation, data modeling, DAX measures, visualization  
- **Excel / Power Query:** Data transformation, cleaning, and preprocessing  
- **Python (Pandas):** Exploratory Data Analysis (EDA), data validation, and export  
- **GitHub:** Project documentation and version control  

---

## 🧩 Key DAX Measures Used

```DAX
Total Orders = COUNTROWS(Zomato)
Total Revenue = SUM(Zomato[order_value])
Cancellation Rate = DIVIDE(
    CALCULATE(COUNTROWS(Zomato), Zomato[is_cancelled] = TRUE()),
    COUNTROWS(Zomato)
)
Average Order Value = AVERAGE(Zomato[order_value])
Average Rating = AVERAGE(Zomato[rating])
