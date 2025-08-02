<h1 align="center">Grocery Sales Dashboard in Power BI</h1>  
 
<p align="center">
  <img src="https://github.com/user-attachments/assets/ca97d374-f68d-454a-b81f-26ce11a1042a" width="1000">
</p>


## 🧩 About Project 

This project showcases a Power BI dashboard built to analyze a grocery sales dataset originally sourced from Kaggle. The dataset reflects real-world transactional activity over a span of 128 days, capturing key entities such as sales, customers, products, employees, and geographic regions. The dashboard uses intuitive visualizations — such as KPIs, charts, tables, and maps — to explore business questions related to revenue trends, product performance, and regional market insights.
While the raw dataset is available on [Kaggle](https://www.kaggle.com/datasets/155a87ba8d7e92c5896ddc7f3ca3e3fa9c799207ed8dbf9a1cedf2e2e03e3c14), this Power BI dashboard is powered by a custom PostgreSQL database I designed in a related [SQL project](https://github.com/Seyyed-Reza-Mashhadi/SQL-Project_Grocery-Sales), which includes full data modeling and analytical queries.

## 💡 Project Objectives

Here is the list of project objectives to answer key business questions:

| Objective | Description |
|-----------|-------------|
| **Q1**    | Track sales performance over time, including total revenue, number of transactions, and monthly trends |
| **Q2**    | Identify high- and low-performing products based on revenue contribution and demand across product categories |
| **Q3**    | Display customer spending metrics such as Average Order Value (AOV) and Average Basket Size |
| **Q4**    | Highlight top-performing employees based on monthly revenue |
| **Q5**    | Analyze sales performance across cities using tables and maps |

## 🛠️ Model Preparation Workflow

### Data Import and Model Inspection
- Data was imported from a local PostgreSQL database using Power BI’s *Import* mode to allow faster performance and offline exploration. The main tables (`sales`, `employees`, `customers`, etc.) were loaded into Power BI. 
- Using the Model View, all primary and foreign key relationships were inspected and confirmed to match the original database schema. This ensured a functional star-schema-like structure that supports clean aggregation and filtering.

### Final ETL Steps in Query Editor

Several lightweight transformations were done in Power BI’s Query Editor to prepare the data for visualization:
- The original schema included normalized `cities` and `countries` tables. To avoid potential ambiguity, location details were merged into the `customers` and `employees` tables using the Merge Queries feature.
- Redundant or unused columns were removed to keep the model lean.
- New columns like `full_name` were created for easier display and slicing.
- Data types were preserved correctly during import, as defined in the PostgreSQL schema.
These steps resulted in a simplified yet rich data model that supports a flexible and efficient reporting experience.

<p align="center">
  <img src="https://github.com/user-attachments/assets/bff00377-5442-4822-833b-78488a1349f1" width="600">
</p>

## 🎨 Dashboard Design and Interactivity

The dashboard layout and visuals were designed with clarity, consistency, and usability in mind.

- A muted, cohesive color palette was chosen to ensure professional presentation and reduce visual fatigue.
- The homepage contains KPI cards, trend lines, and breakdown charts that offer an overview of business performance across revenue, orders, and product categories.
- Most visuals and tables on the homepage support cross-filtering, allowing users to interactively explore different dimensions of the data.
- *Tooltips* are used to display additional context without cluttering the main visuals. Hovering over product category bars reveals the top 5 products (by revenue) within that category.

<br>

<p align="center">
  <img src="https://github.com/user-attachments/assets/fe9480d9-e171-4875-8b4e-db964a9301c9" alt="Tooltip Demo" width="700"/>
</p>

<br>
- A *drill-through page* enables deeper exploration while keeping the main page clean. Clicking on a specific month in the revenue bar chart opens a dedicated monthly view showing:
  - The top-performing employee  
  - Revenue and order trends  
  - Top 10 cities by revenue (in table and map formats)  
  - Most in-demand products based on units sold  

<br>
<br>

<p align="center">
  <img src="https://github.com/user-attachments/assets/0578a1c9-0c28-41c6-920b-4d3e3cd8f995" alt="Drillthrough Demo" width="700"/>
</p>

<br>

This design strikes a balance between high-level clarity and detailed interactivity—helping users extract key business insights while exploring the data at their own pace.
