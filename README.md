# 🎬 DVD Rental Sales Dashboard – Power BI Project

This is an interactive business intelligence dashboard created using the **DVD Rental** dataset. The dashboard explores key insights such as customer behavior, sales performance by country and city, most popular movies, and rental trends.


---

## 📊 Overview

The aim of this project was to:

- Practice creating **interactive dashboards** using Power BI  
- Write **custom SQL queries** to extract and transform data  
- Build visuals that are **interconnected** and easy to interpret  
- Gain insight into customer activity, payments, movie performance, and more  

---

## 🧰 Tools & Technologies

- 🟨 Power BI Desktop  
- 🐘 PostgreSQL  
- 💾 SQL for data extraction and transformation  
- 📁 Excel (for minor data preparation)

---

## ⚙️ Features

- Fully interactive slicers by **country**, **city**, and **customer**
- Dynamic visualizations showing:
  - Top 10 movies by rentals (per selected region)
  - Genre-based performance (pie & bar charts)
  - Revenue cards (total sales, average ticket, number of payments)
  - Customer segmentation by spending
- All visuals are **linked together** — selecting any element filters the entire dashboard

---

## 🧠 Sample SQL Query (Top Movies per Country)

```sql
SELECT
  country,
  film.title,
  COUNT(payment.payment_id) AS rental_count
FROM payment
JOIN rental ON payment.rental_id = rental.rental_id
JOIN inventory ON rental.inventory_id = inventory.inventory_id
JOIN film ON inventory.film_id = film.film_id
JOIN customer ON payment.customer_id = customer.customer_id
JOIN address ON customer.address_id = address.address_id
JOIN city ON address.city_id = city.city_id
JOIN country ON city.country_id = country.country_id
GROUP BY country, film.title
ORDER BY country, rental_count DESC;

```
This query was used to create the visual for **Top Movies by Country**.


## 🗂️ Project Structure

| File                             | Description                                |
|----------------------------------|--------------------------------------------|
| `DvdDashboard.pbix`     | Power BI dashboard file                    |
| `assets/dashboard_screenshot.png` | Preview image of the dashboard             |

---

## 📌 Notes

- Only the most **essential SQL queries** are shared here.
- Built using **realistic business KPIs** and kept **user-friendly**.
- Project created as a **learning exercise**, but presented professionally.
- All charts, tables, and cards are **fully responsive** to user selections.

---

## 🔮 Possible Improvements

- Add trendline visuals for rental behavior over time
- Include map visuals for geographic representation
- Use advanced **DAX** measures and calculated columns
- Style customization with themes

---


## 📬 Contact

If you have any suggestions or questions, feel free to reach out via GitHub!

---
