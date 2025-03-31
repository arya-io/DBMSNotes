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











