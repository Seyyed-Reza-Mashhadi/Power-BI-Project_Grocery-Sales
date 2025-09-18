<h1 align="center"> Grocery Sales Dashboard in Power BI </h1>  
 
<p align="center">
  <img src="https://github.com/user-attachments/assets/ca97d374-f68d-454a-b81f-26ce11a1042a" width="1000">
</p>


## 🧩 About Project 

This project showcases a Power BI dashboard built to analyze a grocery sales dataset from Kaggle, reflecting over 6.7 million real-world transactional activities. The dataset spans 128 days, capturing key entities such as sales, customers, products, employees, and geographic regions. The dashboard uses intuitive visualizations — including KPIs, charts, tables, and maps — to explore business questions related to revenue trends, product performance, and regional market insights.

🔗 **Dataset:** The data is available on [Kaggle](https://www.kaggle.com/datasets/155a87ba8d7e92c5896ddc7f3ca3e3fa9c799207ed8dbf9a1cedf2e2e03e3c14). However, this Power BI dashboard is powered by a custom PostgreSQL database I designed in a related [SQL project](https://github.com/Seyyed-Reza-Mashhadi/SQL-Project_Grocery-Sales), which includes full data modeling and analytical queries.

## 💡 Objectives

Here is the list of project objectives to answer key business questions:

| Objective | Description |
|:-----------:|-------------|
| **Q1**    | Track sales performance over time, including total revenue, number of transactions, and monthly trends |
| **Q2**    | Identify high- and low-performing products based on revenue contribution and demand across product categories |
| **Q3**    | Display customer spending metrics such as Average Order Value (AOV) and Average Basket Size |
| **Q4**    | Highlight top-performing employees based on monthly revenue |
| **Q5**    | Analyze sales performance across cities using tables and maps |

## 🛠️ Model Preparation Workflow

### 📥 Data Import and Model Inspection
- Data was imported from a local PostgreSQL database using Power BI’s *Import* mode to allow faster performance and offline exploration. The main tables (`sales`, `employees`, `customers`, etc.) were loaded into Power BI. 
- Using the Model View, all primary and foreign key relationships were inspected and confirmed to match the original database schema. 

### ⚙️ Final ETL Steps in Query Editor

Several lightweight transformations were done in Power BI’s Query Editor to prepare the data for visualization:
- The original schema included normalized `cities` and `countries` tables. To avoid potential ambiguity, location details were merged into the `customers` and `employees` tables using the Merge Queries feature.
- Redundant or unused columns were removed to keep the model clean.
- New columns like `full_name` were created for easier display and slicing.
- Duplicate rows were removed to ensure data integrity for subsequent analysis.
- Data types were preserved correctly during import, as defined in the PostgreSQL schema.
These steps resulted in a clear and effecient **star schema** structure, with one **fact table** (`sales`) and three **dimension tables** (`products`,`customers`, and `employees`). This simplified yet rich model supports flexible, performant, and intuitive reporting in Power BI.

<p align="center">
  <img src="https://github.com/user-attachments/assets/0bb9ca2d-c10b-4e0f-9529-1c7ab7ca4f28" width="600">
</p>

## 🎨 Dashboard Design and Interactivity

The dashboard layout and visuals were designed with clarity, consistency, and usability in mind.

- A muted, cohesive color palette was chosen to ensure professional presentation and reduce visual fatigue.
- The homepage contains KPI cards, trend lines, and breakdown charts that offer an overview of business performance across revenue, orders, and product categories.
- Most visuals and tables on the homepage support cross-filtering, allowing users to interactively explore different dimensions of the data.
- Tooltips are used to display additional context without cluttering the main visuals. Hovering over product category bars reveals the top 5 products (by revenue) within that category.

<br>
<p align="center"><em>Play the gif image to see a demonstration of the designed tooltip</em></p> 
<p align="center">
  <img src="https://github.com/user-attachments/assets/fe9480d9-e171-4875-8b4e-db964a9301c9" alt="Tooltip Demo" width="700"/>
</p>

<br>

- A drill-through page enables deeper exploration while keeping the main page clean. Clicking on a specific month in the revenue bar chart opens a dedicated monthly view showing:
  - The top-performing employee  
  - Revenue and order trends  
  - Top 10 cities by revenue (in table and map formats)  
  - Most in-demand products based on units sold  

<br>
<br>
<p align="center"><em>Play the gif image to see a demonstration of the designed drill-through</em></p> 
<p align="center">
  <img src="https://github.com/user-attachments/assets/0578a1c9-0c28-41c6-920b-4d3e3cd8f995" alt="Drillthrough Demo" width="700"/>
</p>

<br>

This design strikes a balance between high-level clarity and detailed interactivity—helping users extract key business insights while exploring the data at their own pace.

## 🔑 Summary of Key Findings & Business Insights
This Power BI dashboard enabled a comprehensive, interactive exploration of grocery sales performance over 128 days. Key insights include:
- **Total revenue** reached approximately **$4.3 billion** from about 6.7 million transactions and 87.9 million items ordered.
- The **Average Order Value (AOV)** was **$641** with an average basket size of 13 items, indicating strong cross-selling performance and opportunities for further bundling strategies.
- **Monthly revenue peaked in March** at around $1.03 billion, with an average monthly revenue close to $1 billion. These fluctuations could suggest capacity or demand limits within this dataset’s timeframe (4 months), warranting further investigation to confirm seasonal effects or operational constraints.
- **Revenue is evenly distributed across low-, medium-, and high-tier classes**, each contributing roughly one-third of total revenue, showing a balanced portfolio.
- The **Confections category** emerged as **the top revenue generator** with about $557 million, while the Seafood category generated the least revenue at around $300 million.
- The **highest generated revenue** is from "**Bread - Calabrese Baguette**" product.
- Regional sales analysis reveals that top revenue-generating cities are dispersed across the United States, indicating broad geographic market engagement rather than concentration in specific regions.

## 🚀 Strategic Recommendations

- **Plan inventory and promotions around the March peak** to maximize sales during high-demand periods.
- **Focus on boosting sales in top categories** like Confections, especially popular items such as Hot Chocolate.
- **Explore ways to improve performance of lower-revenue categories** like Seafood.
- **Encourage cross-selling and product bundling** to increase average order value and basket size.
- **Review operational capacity and demand trends** to identify potential growth limitations and opportunities.

## 🔁 Related Project
- 📊 [**SQL Project**](https://github.com/Seyyed-Reza-Mashhadi/SQL-Project_Grocery-Sales): This companion project presents the PostgreSQL database design and extensive analytical SQL queries underpinning the Power BI dashboard insights. It provides deep dives into revenue trends, customer segmentation, product performance, and employee effectiveness.
- ☁️ [**Azure Data Factory Project**](https://github.com/Seyyed-Reza-Mashhadi/Azure-Data-Factory-Project): Implements a complete ETL pipeline for data orchestration using Azure Data Factory, ADLS, and Azure SQL Database.
- 📊 [**Tableau Dashboard**](https://github.com/Seyyed-Reza-Mashhadi/Tableau-Project_Grocery-Sales): Interactive two-page dashboard built on the same dataset to showcase Tableau features, including Tableau Prep Builder workflows, interactivity, navigation, and cross-dashboard linking.
  
## 📦 Power BI File Availability
The Power BI project file is not included in the repository due to its large size (~400 MB) exceeding GitHub’s upload limits. Please contact me if you would like access to the file.
