 <h1 align="center">Grocery Sales Dashboard</h1>  
<img width="1280" height="718" alt="Home Dashboard" src="https://github.com/user-attachments/assets/ca97d374-f68d-454a-b81f-26ce11a1042a" />

## 🧩 About Project 

This project showcases a Power BI dashboard built to analyze a grocery sales dataset originally sourced from Kaggle. The dataset reflects real-world transactional activity over a span of 128 days, capturing key entities such as sales, customers, products, employees, and geographic regions. The dashboard uses intuitive visualizations — including charts, tables, and maps — to explore business questions related to revenue trends, product performance, and regional market insights.
While the raw dataset is available on [Kaggle](https://www.kaggle.com/datasets/155a87ba8d7e92c5896ddc7f3ca3e3fa9c799207ed8dbf9a1cedf2e2e03e3c14), this Power BI dashboard is powered by a custom PostgreSQL database I designed in a related [SQL project](https://github.com/Seyyed-Reza-Mashhadi/SQL-Project_Grocery-Sales), which includes full data modeling and analytical queries.

## 💡 Project Objectives

The dashboard was designed to address the following analytical goals:

| Objective | Description |
|-----------|-------------|
| **Q1**    | Track sales performance over time, including monthly revenue, transaction count, and active date range. |
| **Q2**    | Identify high- and low-performing products based on sales volume and revenue contribution. |
| **Q3**    | Classify customers by spending behavior and calculate metrics like **Average Order Value (AOV)** and **Average Basket Size**. |
| **Q4**    | Evaluate employee performance using revenue metrics and explore potential links with experience or age. |
| **Q5**    | Analyze regional sales across cities and countries to identify top-performing markets. |

> 🔎 **Note:** Objectives Q1, Q2, Q3, and Q5 are fully or mostly implemented in the current dashboard. Q4 (employee evaluation) is partially explored but not deeply visualized due to time constraints.

---

## 📊 Dashboard Overview



The Power BI report includes the following visual elements:

- **Revenue Trends** over time (daily, weekly, monthly)
- **Top Products** by revenue and quantity sold
- **Customer Segmentation** based on spending behavior
- **AOV and Basket Size** breakdowns
- **Geographic Sales Distribution** via interactive map
- Filterable dashboards using **slicers** (e.g., by date, country, category)

---

## 🧠 Data Model & Queries

The dashboard uses a **local PostgreSQL database** (imported into Power BI using the *Import* mode, not *DirectQuery*). This choice was made to optimize performance and reduce live query dependencies, given the manageable dataset size.

### 🧱 Modeling Process:

1. **Data Import:** All relevant tables were loaded from the PostgreSQL database.
2. **Relationship Validation:** The model view in Power BI confirmed that foreign key relationships (e.g., customer_id, employee_id) were preserved during import.
3. **Schema Simplification:**  
   - The original schema included separate `cities` and `countries` tables linked indirectly via both customers and employees.
   - To reduce ambiguity and simplify relationships, these were **merged** into the `customers` and `employees` tables, respectively.
   - This eliminates redundancy while preserving location data — a trade-off aligned with best practice for star-schema-like modeling in BI tools.

---

## 🔧 Tools & Technologies

- **Power BI Desktop**
- **PostgreSQL**
- **SQL** (data preparation, transformation, and joins)
- **Kaggle Dataset**: [Grocery Sales Dataset](https://www.kaggle.com/datasets/155a87ba8d7e92c5896ddc7f3ca3e3fa9c799207ed8dbf9a1cedf2e2e03e3c14)

---

## 📁 Repository Structure

```bash
power-bi-grocery-sales/
├── README.md
├── PowerBI_Report.pbix
├── /images
│   └── dashboard-preview.png
└── (Optional) Link to SQL repo

