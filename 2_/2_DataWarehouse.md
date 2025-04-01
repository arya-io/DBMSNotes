# Data Warehouse

High Volume of Storage.
Data warehousing is combining data from multiple and usually varied sources into one comprehensive and easily manipulated database.

Example:
Suppose Maruti Suzuki stores the car data in CSV Files.
On the other hand, Hyundai Motors says that they store the data in SQL database, let say Oracle Database.
Honda stores the data in Azure Cloud (Cosmos DB).
Mahindra stores the same data in JSON format.

And our company has decided to work with SQL Server, which none of the above companies are using to store their data.

Smooth Migration from Hyundai Motors' Oracle Database to SQL Server is efficient as they belong to same Database family.

50 Lakh records are to be imported from all 4 databases towards SQL Server that amounts to 200 Lakh.
---

There's a problem where we are going to stuck.

Data comes from different sources.
#### When data comes from different heterogenous sources then following challenges are there:
1. Column Names are different for each of these company's database.
2. **Data types of the same columns are different.**
3. Number of columns will vary.
4. **Number of rows, means volume of data will vary a lot.**
5. **Constraints and business rules will also differ.**
   Downpayment criteria may be different for every model, i.e., constraints and rules vary with sources.
   This rule comes under domain knowledge. Above four are technical aspects.
6. Entire row getting duplicated.
7. With unique ids the remaining entire row getting duplicated.
8. Synomyms entered of the data values(USA, US, America, States).
9. Missing values.
10. Junk values.
And still more..

**ETL (Extract Transform Load)** is the process to populate Data Warehouse.
E: Extracting from different sources.
T: Above 5 points discussed so far, comes under Transform. Filtering, Removing Null, Eliminating Duplicates, etc.

## ETL can be done in two ways:
- By Coding
- By GUI (Graphical User Interface)

In order to fast execute ETL and without coding, ETL tools are already available (GUI). A moderate formula writing is required.

## ETL Tools:
1. Informatica
    a. Informatica Power Centre (On Premises)
    b. IICS(Informatica Intelligent Cloud Services)
2. SQL Server Integration Services (SSIS)
3. Data Stage (IBM)
4. Oracle Data Integrator
6. Alteryx
7. Azure Data Factory (ADF)
8. Ab Initio

## Data Warehouse Architecture

| Component         | Description                     |
|-------------------|---------------------------------|
| Data Sources      | (Databases, APIs)              |
| ETL Process       | Extract -> Transform -> Load   |
| Data Warehouse    | (Centralized Repository)       |
| Staging Area      | Intermediate data storage      |
| Data Marts        | Specific subsets of data       |
| OLAP              | Online Analytical Processing   |
| End-Users         | (Reports, BI & Dashboards)     |

## Designs of ETL:
1. I Design: One Source and One Destination
2. Y Design: Multiple Sources and One Destination
3. Inverted Y Design: One Source Multiple Destinations
4. X Design: Multiple Sources and Multiple Destinations

Above third and fourth contains Data Marts.

## Data Mart

1. Data Mart is a subset of Data Warehouse.
2. Instead of populating the entire output of ETL into one single destination, the different output are given to different destinations.

### Example of Full Load and Incremental Load:
- S1 is the source having 100 rows.
- D1 is the SQL Server destination.
- ETL is done yesterday. So D1 has all 100 rows till yesterday.
- The first time ETL done is known as "Full Load".
- Full Load is first time and one time.
- Now, today 10 new rows got added in the Oracle S1 source.
- That means the source has 110 rows.
- This will also be added in the destination.
- In this case, only 10 new rows need to be added in D1.
- This is known as "Incremental Load".
- Incremental Load is generally scheduled.

## Data Staging
- The logic of "Incremental Load" is done using "Staging Tables".

## Data Warehouse with Staging Area Architecture

```
Data Sources --> Staging Area --> Data Warehouse --> Users

Data Sources:
- Transactional Databases
- External Sources
- Flat Files
- IoT Devices

Staging Area:
- Data Cleaning
- Data Transformation
- Data Integration

Data Warehouse:
- Subject-Oriented
- Integrated
- Non-volatile
- Time-Variant
  - Fact Tables
  - Dimension Tables

Users:
- Business Analysts
- Data Scientists
- Executives
- Applications
```

## Multiple Inputs and Multiple Outputs via Data Warehouse

```
Multiple Inputs:
Legacy System 1
Legacy System 2
Legacy System N
       ↓
     Data Warehouse
       ↓
Multiple Outputs:
- OLAP (Online Analytical Processing)
- Report Writers
- EIS/DSS (Executive Information Systems/Decision Support Systems)
- Data Mining
- Alert System
- Exception Reporting
```

## OLTP

- OLTP comes before OLAP.
- Operational Data Store or Operational Systems
- The **OLTP Database** records transactions in real time and aims to **automate clerical data entry processes** of a business entity.
- **Addition, modification and deletion of data** in the OLTP database is essential and the semantics of the application used in the front end impact on the organization of the data in the database.

### Applications of OLTP
- RDBMS softwares are primarily useful for creating the OLTP designs.
- OLTP has also been used to refer to procesing in which the system responds immediately.

### Drawbacks of OLTP
- Concurrency gets created.
    Multiple users are not able to make multiple changes simultaneously.
- Tables get locked by which report generation gets delayed.
- Not suitable for getting summary results especially when high volume of data is there.

## OLAP (Online Analytical Processing)
- OLAP is computer processing that enables a user to easily and selectively extract and view data from different points of view.
- OLAP is actually a **multi-dimensional database** which considers each data attribute (such as **product, geographic sales region, and time period**) as a separate **"dimension"**. OLAP software can locate the intersection of dimensions (all products sold in the Eastern region above a certain price during a certain time period) and display them. Attributes such as time periods can be broken down into sub attributes.
- For example, **a user can request that data be analyzed to display a spreadsheet showing all of a company's beach ball products sold in Florida in the month of July, compare revenue figures with those for the same products in September, and then see a comparison of other product sales in Florida in the same time period**. To facilitate this kind of analysis, OLAP data is stored in a multidimensional database.
- Data Refresh happens from OLTP to OLAP.
- OLAP tool gives you GUI.
- Excel Pivot Table is the greatest example of OLAP.

### OLAP for a Business Man
- For people on the business side, the key feature within interrelated data is "Multidimensional". In other words, the ability to analyze metrics in different dimensions such as time, geography, gender, product, etc.
- For example, sales for the company is up.
  Which region is most responsible for this increase?
  Which store in this region is most responsible for the increase?
  What particular product category or categories contributed the most to the increase?
  Answering these types of questions, **in order**, means that you are performing an **OLAP** analysis.
  OLAP is more suitable or relevant for top management team like CEO, MD, Board of Directors and Investors.

### Major Vendors of OLAP
- Oracle -- Essbase (Hyperion)
- OBIEE
- SAS
- Microstrategy
- Business Objects
- SSAS
- And Many More.......

## OLAP and Data Visualization
- All the analysis done through OLAP tools can be seen visually using Data Visualization tools.
- **Power BI, Tableau** are Data Visualization tools for this purpose.

## Difference between OLTP and OLAP
```
| **Aspect**                | **OLTP**                                                                     | **OLAP**                                              |
|---------------------------|------------------------------------------------------------------------------|------------------------------------------------------|
| **Purpose**               | Real-Time Data Entry                                                        | Read and Analyze Historical Data                    |
| **Perform Updates**       | Yes                                                                         | No, Read-Only mostly                                 |
| **Perform Deletes**       | Yes                                                                         | No, NEVER                                            |
| **Perform Inserts**       | Yes                                                                         | Yes, BUT periodically                                |
| **Perform Selects**       | Generally for non-summary (detailed) rows                                   | Mostly for summary rows                             |
| **Source of Data**        | Data Entry generally by a single data source                                | Historical summary data from multiple data sources  |
| **Associated Database**   | Only Operational                                                            | Analytical, may be operational                      |
| **Validation Factor**     | Optimized for validation of incoming data during transactions; uses validation data tables | Loaded with consistent, valid data; requires no real-time validation |
| **Optimized for**         | A common set of transactions, usually adding or retrieving a single row at a time per table | Bulk loads and large, complex, unpredictable queries that access many rows per table |
| **Support for Users**     | Thousands of concurrent users                                               | Few concurrent users                                |
| **Language for Report Generation** | SQL                                                                 | MDX and DAX (Data Analysis Expression)              |
```





