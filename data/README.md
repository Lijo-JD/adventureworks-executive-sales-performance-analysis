# AdventureWorks Sales Dataset

This directory contains documentation for the dataset used in the **AdventureWorks Sales Executive Report** Power BI project.

The project uses the AdventureWorks sample data provided by Microsoft for learning, training and demonstration purposes.

---

## 📊 Dataset Overview

AdventureWorks represents a fictional bicycle manufacturer that sells bicycles and accessories to markets around the world.

The dataset contains information related to:

- Customers
- Dates
- Products
- Resellers
- Sales transactions
- Sales orders
- Sales territories

The data is structured using a dimensional-model approach, making it suitable for practicing:

- Data modeling
- Star schemas
- Relationships
- Hierarchies
- DAX
- Power BI reporting
- Business intelligence analysis

---

## 📥 Dataset Source

The primary source for this Power BI project is the **AdventureWorks Sales sample Excel workbook** provided through Microsoft Learn.

### Microsoft Learn Tutorial

[From dimensional model to stunning report in Power BI Desktop](https://learn.microsoft.com/en-us/power-bi/create-reports/desktop-dimensional-model-report)

The tutorial provides the sample Excel workbook used to create the report.

---

## 🔗 Alternative Microsoft Sources

Microsoft also provides AdventureWorks sample databases for SQL Server and related environments.

[AdventureWorks Sample Databases — Microsoft Learn](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure)

Microsoft's Power BI Desktop Samples repository also contains AdventureWorks-related Power BI sample files.

[AdventureWorks Power BI Samples — Microsoft GitHub](https://github.com/microsoft/powerbi-desktop-samples/tree/main/DAX)

---

## 🗂️ Tables Used

The AdventureWorks Power BI model used in this project contains the following major tables.

| Table | Purpose |
|---|---|
| **Customer** | Customer information and geographic details |
| **Date** | Date and fiscal calendar information |
| **Product** | Product, model, subcategory and category information |
| **Reseller** | Reseller information and geographic details |
| **Sales** | Sales transaction/fact data |
| **Sales Order** | Sales order information |
| **Sales Territory** | Geographic sales territory information |

---

## 📐 Data Model

The dataset follows a dimensional/star-schema design.

The **Sales** table acts as the central fact table, while dimension tables provide descriptive information used to analyze the sales transactions.

Conceptually:

```text
                  Customer
                     │
                     │
Product ────────── Sales ────────── Reseller
                     │
                     │
                    Date
                     │
                     │
              Sales Territory
                     │
                     │
                Sales Order
```

The exact relationships are defined in the Power BI `.pbix` file.

---

## 🔑 Important Columns

### Customer

Examples include:

- `CustomerKey`
- `Country-Region`
- `State-Province`
- `City`
- `Postal Code`
- `Customer`

---

### Date

Examples include:

- `DateKey`
- `Date`
- `Year`
- `Quarter`
- `Month`
- Fiscal year fields
- Fiscal quarter fields

The AdventureWorks reporting model uses a fiscal year beginning on **July 1**.

---

### Product

Examples include:

- `ProductKey`
- `Category`
- `Subcategory`
- `Model`
- `Product`
- `Standard Cost`
- `List Price`

---

### Reseller

Examples include:

- `ResellerKey`
- `Business Type`
- `Country-Region`
- `State-Province`
- `City`
- `Postal Code`
- `Reseller`

---

### Sales

Important transaction fields include:

- `SalesOrderLineKey`
- `ResellerKey`
- `CustomerKey`
- `ProductKey`
- `OrderDateKey`
- `DueDateKey`
- `ShipDateKey`
- `SalesTerritoryKey`
- `Order Quantity`
- `Unit Price`
- `Extended Amount`
- `Unit Price Discount Pct`
- `Product Standard Cost`
- `Total Product Cost`
- `Sales Amount`

---

### Sales Territory

Examples include:

- `SalesTerritoryKey`
- `Group`
- `Country-Region`
- `Region`

---

### Sales Order

Examples include:

- `SalesOrderLineKey`
- `Sales Order`
- `Sales Order Line`

---

## 🧹 Data Preparation

Before creating the report, the data was prepared in Power BI using Power Query.

The preparation process included:

1. Importing the AdventureWorks workbook.
2. Selecting the required tables.
3. Checking column data types.
4. Setting appropriate data types.
5. Loading the transformed data into Power BI.
6. Creating relationships between tables.
7. Hiding technical key columns from the report view.
8. Creating business-friendly hierarchies.

---

## 🏗️ Hierarchies

The Power BI model contains several hierarchies.

### Customer — Geography

```text
Country-Region
→ State-Province
→ City
→ Postal Code
→ Customer
```

### Date — Fiscal

```text
Year
→ Quarter
→ Month
→ Date
```

### Product — Products

```text
Category
→ Subcategory
→ Model
→ Product
```

### Reseller — Geography

```text
Country-Region
→ State-Province
→ City
→ Postal Code
→ Reseller
```

### Sales Order — Sales Orders

```text
Sales Order
→ Sales Order Line
```

### Sales Territory — Sales Territories

```text
Group
→ Country-Region
→ Region
```

These hierarchies make it possible to drill from higher-level business information into more detailed records.

---

## 📊 Dataset Usage in the Report

The dataset is used to answer three primary business questions:

### 1. Which day had the most sales in February 2019?

Sales Amount is analyzed by date to identify the highest-sales day.

### 2. Which country/region is seeing the most success?

Order Quantity is analyzed geographically to identify the strongest country/region.

### 3. Which product category and reseller business types should the company continue to invest in?

Sales Amount is analyzed by product category and reseller business type.

---

## 📈 Important Fields Used in Report Visuals

| Analysis | Fields |
|---|---|
| Sales trend | Date, Sales Amount |
| Geographic performance | Country-Region, Order Quantity |
| Product performance | Category, Sales Amount |
| Reseller performance | Business Type, Sales Amount |
| Time filtering | Fiscal Year, Month |
| Detailed geographic analysis | Country-Region, State-Province, City, Postal Code |

---

## 📦 Raw Dataset Files

The raw AdventureWorks dataset is **not included in this repository by default**.

This is intentional because the project uses Microsoft's sample data rather than redistributing the source dataset.

To reproduce the project:

1. Open the Microsoft Learn AdventureWorks Power BI tutorial.
2. Download the **AdventureWorks Sales sample Excel workbook**.
3. Place the workbook in a local data directory if desired.
4. Open the Power BI project.
5. Update the data source path if necessary.
6. Refresh the dataset.

---

## 🔄 Reproducibility

To reproduce the report from the original source:

```text
Microsoft AdventureWorks Excel Workbook
                ↓
          Power Query
                ↓
        Data Preparation
                ↓
       Power BI Data Model
                ↓
        Relationships
                ↓
          Hierarchies
                ↓
          DAX Measures
                ↓
         Report Visuals
                ↓
      Executive Sales Report
```

---

## 📚 References

### Microsoft Learn — Power BI AdventureWorks Tutorial

[From dimensional model to stunning report in Power BI Desktop](https://learn.microsoft.com/en-us/power-bi/create-reports/desktop-dimensional-model-report)

### Microsoft Learn — AdventureWorks Sample Databases

[AdventureWorks sample databases](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure)

### Microsoft Power BI Desktop Samples

[Power BI Desktop Samples — AdventureWorks](https://github.com/microsoft/powerbi-desktop-samples/tree/main/DAX)

### Microsoft DAX Sample Model Documentation

[DAX sample model — Microsoft Learn](https://learn.microsoft.com/en-us/dax/dax-sample-model)

---

## ⚖️ Attribution & Licensing

AdventureWorks is a Microsoft-provided sample dataset intended for learning, training and demonstration.

The original dataset and associated materials remain the property of their respective owners.

This project does not claim ownership of the AdventureWorks dataset.

For the most current licensing and usage information, refer to the original Microsoft source.

---

## 📝 Notes

- The dataset represents a fictional company.
- Sales figures should not be interpreted as real-world financial information.
- Dataset versions may differ depending on which AdventureWorks sample is downloaded.
- Microsoft may update or change sample files over time.
- If the source workbook changes, visual results may differ from those documented in the main project README.

---

## 👤 Project

**AdventureWorks Sales Executive Report**

**Author:** Lijo John Daniel

**Purpose:** Data Analytics / Power BI Portfolio Project

**Primary tools:** Power BI • Power Query • DAX • Excel