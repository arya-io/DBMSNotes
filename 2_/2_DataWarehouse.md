# 🏢 Data Warehouse

A **Data Warehouse** is designed for **high-volume data storage** and is used to **combine data from multiple and often heterogeneous sources** into one unified and query-optimized system.

---

### ✅ What is Data Warehousing?

> Data warehousing is combining data from multiple and usually varied sources into one comprehensive and easily manipulated database.

---

### 📦 Real-World Example:

Suppose different automobile companies store their data as follows:

| Company         | Storage Format         |
|----------------|------------------------|
| Maruti Suzuki  | CSV Files              |
| Hyundai Motors | Oracle Database (SQL)  |
| Honda          | Azure Cloud (CosmosDB) |
| Mahindra       | JSON Format            |

Now, **our company has chosen SQL Server** as the target system — which none of them use.

- ✅ Migration from Hyundai’s Oracle DB to SQL Server is smoother, as they belong to the **same database family**.
- 📊 We are importing **50 Lakh records** from each source = **200 Lakh total**.

---

## ⚠️ Challenges with Heterogeneous Data Sources:

When data comes from **different heterogeneous sources**, the following issues arise:

1. 🏷️ **Column names differ** across source databases.
2. 🔢 **Data types for the same columns vary**.
3. 🧾 **Number of columns** is inconsistent.
4. 📈 **Volume of rows** is uneven (some companies have more data than others).
5. 📋 **Constraints & Business Rules differ.**  
   - Example: Downpayment rules vary by brand/model.  
   - ➕ This falls under **Domain Knowledge**, unlike the first four which are **Technical** issues.
6. 🔁 Entire rows get duplicated.
7. 🔁 Rows are duplicated **except for unique IDs**.
8. 🗺️ **Synonyms used** in data values (e.g., *USA, US, America, States*).
9. 🚫 **Missing values** in important columns.
10. 🗑️ **Junk/Invalid values** are present.

> 🧠 And still more challenges may arise — data warehousing is complex but critical for robust analytics.

# 🔄 ETL (Extract Transform Load)

**ETL** is the process used to populate a **Data Warehouse** by moving and transforming data from multiple sources into a centralized repository.

---

### 🔹 E: Extract
- Extracting data from various sources (e.g., CSV, Oracle DB, Cloud Storage, JSON, etc.)

### 🔹 T: Transform
- This step covers **data cleaning and standardization**:
  1. Renaming inconsistent column names
  2. Converting data types
  3. Standardizing formats
  4. Filtering data
  5. Removing nulls
  6. Eliminating duplicates
  7. Handling synonyms
  8. Applying business rules

> 🧠 All the transformation challenges discussed earlier fall under this phase.

### 🔹 L: Load
- Loading clean, transformed data into the **Data Warehouse** (e.g., SQL Server)

---

## ⚙️ ETL Can Be Done In Two Ways:

1. **By Coding**  
   - Using SQL, Python, Shell scripts, etc.
2. **By GUI Tools (Graphical User Interface)**  
   - No heavy coding required  
   - Supports drag & drop operations  
   - Only moderate formula writing needed

---

## 🛠️ Popular ETL Tools

| Tool Name                | Description                         |
|--------------------------|-------------------------------------|
| **Informatica**          | Widely used enterprise ETL tool     |
| └─ Power Center          | On-Premises version                 |
| └─ IICS                  | Cloud-based (Informatica Cloud)     |
| **SQL Server Integration Services (SSIS)** | Microsoft’s ETL tool |
| **IBM DataStage**        | ETL tool by IBM                     |
| **Oracle Data Integrator** | Oracle’s enterprise ETL solution  |
| **Alteryx**              | Drag-drop workflow-based ETL        |
| **Azure Data Factory (ADF)** | Microsoft Azure’s cloud ETL tool |
| **Ab Initio**            | High performance enterprise tool    |

---

> ⚡ These tools allow for **faster execution** and **visual workflow design** — making ETL scalable and manageable even for non-programmers.

# 🏗️ Data Warehouse Architecture

| Component         | Description                     |
|-------------------|---------------------------------|
| **Data Sources**      | Databases, APIs, Files, etc.      |
| **ETL Process**       | Extract → Transform → Load        |
| **Data Warehouse**    | Centralized repository of data    |
| **Staging Area**      | Temporary/intermediate storage    |
| **Data Marts**        | Specific subsets of warehouse data |
| **OLAP**              | Online Analytical Processing       |
| **End-Users**         | Reporting, BI Tools, Dashboards   |

---

## 🧩 Designs of ETL

1. **I Design**  
   ▸ One Source → One Destination

2. **Y Design**  
   ▸ Multiple Sources → One Destination

3. **Inverted Y Design**  
   ▸ One Source → Multiple Destinations  
   ▸ ✅ Contains Data Marts

4. **X Design**  
   ▸ Multiple Sources → Multiple Destinations  
   ▸ ✅ Contains Data Marts

---

## 📦 Data Mart

- A **Data Mart** is a **subset of a Data Warehouse**, designed for a specific business unit or purpose.

- 🔄 Instead of pushing all ETL output to one destination (Data Warehouse), **data is split and delivered to different destinations** (Data Marts) based on the need.

> 📌 This allows better performance, faster access, and more focused analytics for specific teams (e.g., Sales, HR, Finance).

### 🔁 Example of Full Load and Incremental Load:

- `S1` is the **source** having 100 rows.
- `D1` is the **SQL Server destination**.
- ETL was performed **yesterday**, and all 100 rows from `S1` were loaded into `D1`.
- ✅ This first-time ETL process is known as **Full Load**.
- **Full Load** happens:
  - Only once
  - Usually at the beginning of the project

---

- Today, 10 new rows were added to the Oracle source `S1`.
- So now, `S1` has **110 rows**.
- But the destination `D1` already has the first 100.
- We **only need to add the new 10 rows** to `D1`.

✅ This process is known as **Incremental Load**.

- **Incremental Load**:
  - Adds only the **new or changed** records
  - Is typically **scheduled regularly** (e.g., daily, hourly)
  - Saves time and system resources compared to full reload

---

## 🗃️ Data Staging

- The logic for **Incremental Load** is implemented using **Staging Tables**.
- These staging tables temporarily hold the incoming data from the source before comparing with the destination.
- From here, new or changed rows are identified and passed into the final destination.

## 🏗️ Data Warehouse with Staging Area Architecture

Data Sources --> Staging Area --> Data Warehouse --> Users


### 📥 Data Sources:
- Transactional Databases  
- External Sources  
- Flat Files  
- IoT Devices  

### 🛠️ Staging Area:
- **Data Cleaning**  
- **Data Transformation**  
- **Data Integration**  

### 🏢 Data Warehouse:
- **Subject-Oriented**
- **Integrated**
- **Non-volatile**
- **Time-Variant**

🧱 Components:
- **Fact Tables**
- **Dimension Tables**

### 👥 Users:
- Business Analysts  
- Data Scientists  
- Executives  
- Applications  

## 🔄 Multiple Inputs and Multiple Outputs via Data Warehouse

## 🔄 Multiple Inputs and Multiple Outputs via Data Warehouse

**Multiple Inputs:**
- Legacy System 1  
- Legacy System 2  
- Legacy System N  

⬇️  

**Data Warehouse**

⬇️  

**Multiple Outputs:**
- OLAP (Online Analytical Processing)  
- Report Writers  
- EIS/DSS (Executive Information Systems / Decision Support Systems)  
- Data Mining  
- Alert System  
- Exception Reporting  

## 🧾 OLTP (Online Transaction Processing)

- OLTP comes **before** OLAP.
- Also known as **Operational Data Store** or **Operational Systems**.
- The **OLTP Database** records transactions in real time and aims to **automate clerical data entry processes** of a business entity.
- **Addition, modification, and deletion of data** in the OLTP database is essential, and the semantics of the application used in the front end impact the organization of data in the database.

### ✅ Applications of OLTP
- RDBMS software is primarily useful for creating OLTP systems.
- OLTP refers to processing in which the system **responds immediately** to user requests.

### ❌ Drawbacks of OLTP
- **Concurrency issues**: Multiple users may face problems making simultaneous changes.
- **Table locking** can delay report generation.
- Not suitable for generating **summary results**, especially with large volumes of data.

## 📊 OLAP (Online Analytical Processing)

- OLAP is computer processing that enables a user to **easily and selectively extract and view data** from different points of view.
- OLAP is a **multi-dimensional database** that considers each attribute (e.g., **product, geographic region, time period**) as a separate **dimension**.
- OLAP software can locate intersections of dimensions (e.g., *all products sold in the Eastern region above a certain price during a certain time*) and display them.
- Attributes like time can be **broken into sub-attributes** (e.g., month, quarter, year).
- Example:
  > A user can request a spreadsheet showing all beach ball products sold in Florida in July, compare revenue with September, and then see other product sales in Florida during that same time.
- Data in OLAP is **refreshed from OLTP**.
- OLAP tools provide a **GUI** for users.
- 📌 **Excel Pivot Table** is a classic example of OLAP.

---

### 👔 OLAP for Business Users

- For business users, OLAP means the ability to analyze data **multi-dimensionally** (by time, geography, gender, product, etc.).
- Example:
  > Sales are up — which region is responsible?  
  > Which store contributed the most?  
  > Which product category drove the increase?

- These layered, drill-down questions define **OLAP Analysis**.
- 💼 OLAP is mostly used by **CEOs, MDs, Board Members, and Investors**.

---

### 🏢 Major OLAP Vendors

- **Oracle Essbase (Hyperion)**
- **OBIEE**
- **SAS**
- **MicroStrategy**
- **Business Objects**
- **SSAS**
- ...and many more.

---

## 🎨 OLAP + Data Visualization

- All OLAP analysis can be visually represented using **Data Visualization tools**.
- Examples:
  - 📊 **Power BI**
  - 📈 **Tableau**

## 🆚 Difference between OLTP and OLAP

| **Aspect**                      | **OLTP**                                                                                     | **OLAP**                                                        |
|---------------------------------|----------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| **Purpose**                     | Real-Time Data Entry                                                                         | Read and Analyze Historical Data                               |
| **Perform Updates**             | ✅ Yes                                                                                        | ❌ No, Read-Only mostly                                         |
| **Perform Deletes**             | ✅ Yes                                                                                        | ❌ No, NEVER                                                    |
| **Perform Inserts**             | ✅ Yes                                                                                        | ✅ Yes, BUT periodically                                        |
| **Perform Selects**             | For non-summary (detailed) rows                                                              | Mostly for summary rows                                        |
| **Source of Data**              | Data Entry from a single source                                                              | Historical data from multiple sources                          |
| **Associated Database**         | Operational                                                                                  | Analytical (may be a replica of operational data)              |
| **Validation Factor**           | Optimized for validation during transactions using validation tables                        | Loaded with clean, validated data (no real-time validation)    |
| **Optimized For**               | Common transactions (Insert/Retrieve single row per table)                                  | Complex, bulk queries accessing many rows per table            |
| **Support for Users**           | Thousands of concurrent users                                                                | Few concurrent users                                            |
| **Language for Reporting**      | SQL                                                                                          | MDX (Multidimensional Expressions), DAX (Data Analysis eXpr.)   |
