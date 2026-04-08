📊 Power BI Data Modeler Project

 📌 Project Title
 Data Modeler – Building a Normalized Star Schema Data Model**
---

 🎯 Project Objective

The objective of this project is to build a well-structured **relational data model in Power BI** using normalized tables.
This project focuses on:

* Table Relationships
* Cardinality (1:Many, Many:1, Many:Many)
* Star Schema vs Snowflake Schema
* Active & Inactive Relationships

---

 📂 Dataset Overview

The project uses the following datasets:

 1. Sales_Fact

* SalesID (Primary Key)
* CustomerID (Foreign Key)
* ProductID (Foreign Key)
* RegionID (Foreign Key)
* DateKey (Foreign Key)
* Quantity
* Revenue
* Discount

---

2. Customer_Dim

* CustomerID (Primary Key)
* FullName
* Age
* Gender
* Segment

---

 3. Product_Dim

* ProductID (Primary Key)
* ProductName
* Category
* Subcategory
* Brand

---

 4. Region_Dim

* RegionID (Primary Key)
* Country
* State
* City

---

5. Date_Dim

* DateKey (Primary Key)
* Date
* Month
* Quarter
* Year
* Fiscal Year

---

 6. Returns_Fact

* ReturnID (Primary Key)
* SalesID (Foreign Key)
* ReturnDateKey (Foreign Key)
* Reason

---

🔗 Data Model Relationships

The following relationships are created:

* Sales_Fact → Customer_Dim (CustomerID)
* Sales_Fact → Product_Dim (ProductID)
* Sales_Fact → Region_Dim (RegionID)
* Sales_Fact → Date_Dim (DateKey)
* Returns_Fact → Sales_Fact (SalesID)
* Returns_Fact → Date_Dim (Inactive Relationship using ReturnDateKey)

---

 ⭐ Schema Design

🔷 Star Schema

* Central Fact Table: **Sales_Fact**
* Connected Dimension Tables:

  * Customer_Dim
  * Product_Dim
  * Region_Dim
  * Date_Dim

---

 ❄️ Snowflake Schema

* Product_Dim further normalized into:

  * Category
  * Subcategory

---

 🔁 Relationship Types

* **One-to-Many (1:*)** → Product to Sales
* **Many-to-One (*:1)** → Sales to Customer
* **Many-to-Many (*:*)** → Salesperson to Region (if implemented)

---

🔄 Active vs Inactive Relationships

* Active Relationship → Used by default (solid line)
* Inactive Relationship → Requires DAX (dashed line)

Example:

```DAX
CALCULATE(
    SUM(Sales_Fact[Revenue]),
    USERELATIONSHIP(Date_Dim[DateKey], Returns_Fact[ReturnDateKey])
)
```

---

⚙️ Data Preparation

Performed in **Power Query**:

* Removed null/blank values
* Ensured correct data types
* Cleaned and formatted columns

---

📊 Data Model Enhancements

* Applied Data Categories (City, Country, etc.)
* Created Hierarchies:

  * Date → Year > Quarter > Month > Date
  * Region → Country > State > City
  * Product → Category > Subcategory > ProductName

---

 ✅ Verification

Used **Matrix Visual** to verify:

* Sales by Product Category & Region
* Returns by Fiscal Year
* Revenue by Customer Segment

---

