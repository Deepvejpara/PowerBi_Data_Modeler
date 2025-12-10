# 📊 Data Modeler -- Normalized Star Schema (Power BI)

This project demonstrates the construction of a **relational star-schema
data model** in Power BI using multiple Excel-based dimension and fact
tables.
The primary objective is to showcase your understanding of:

-   Table relationships
-   Cardinality & cross-filter directions
-   Star vs. Snowflake modeling
-   Handling inactive/ambiguous relationships
-   Data categories & hierarchies
-   Model View + Power Query logic

## 📁 Dataset Overview

### 1. Sales_Fact.xlsx

-   SalesID (PK)
-   CustomerID (FK)
-   ProductID (FK)
-   RegionID (FK)
-   DateKey (FK)
-   Quantity
-   Revenue
-   Discount

### 2. Customer_Dim.xlsx

-   CustomerID (PK)
-   FullName
-   Age
-   Gender
-   Segment

### 3. Product_Dim.xlsx

-   ProductID (PK)
-   ProductName
-   Category
-   Subcategory
-   Brand

### 4. Region_Dim.xlsx

-   RegionID (PK)
-   Country
-   State
-   City

### 5. Date_Dim.xlsx

-   DateKey (PK)
-   Date
-   Month
-   Quarter
-   Year
-   Fiscal Year

### 6. Returns_Fact.xlsx

-   ReturnID (PK)
-   SalesID (FK → Sales_Fact)
-   ReturnDateKey (FK → Date_Dim)
-   Reason

## 📌 Project Tasks

### 1. Model Construction & Relationships

-   Import all files using **Power Query**.
-   Apply correct data types and remove null/blank rows.
-   Load cleaned tables into the **Data Model**.
-   Define **Primary Keys** and **Foreign Keys** manually.

#### Create the following relationships:

-   Sales_Fact → Customer_Dim
-   Sales_Fact → Product_Dim
-   Sales_Fact → Region_Dim
-   Sales_Fact → Date_Dim
-   Returns_Fact → Sales_Fact
-   Returns_Fact → Date_Dim *(inactive relationship for ReturnDateKey)*

## ⚙️ Advanced Model Settings

-   Set correct **relationship cardinality** and **cross-filter
    direction** (mostly single).
-   Enable **bidirectional filters** only where necessary.
-   Simulate **inactive relationships** using Returns_Fact.
-   Resolve **filter ambiguity**.

## ✨ Data Model Enhancements

### ✔ Data Formatting

-   Apply correct data types (currency, whole numbers, dates).
-   Set **Data Categories** (City, Country, ProductName).

### ✔ Build Hierarchies

-   **Date_Dim:** Year → Quarter → Month → Date
-   **Region_Dim:** Country → State → City
-   **Product_Dim:** Category → Subcategory → ProductName

## 🧪 Verification Step

Use a **Matrix Table** to verify:

-   Sales grouped by Product Category and Region
-   Return reasons by Fiscal Year
-   Revenue by Customer Segment
