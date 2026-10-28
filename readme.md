# Smart Waste Collection Management System

## 1. Introduction

The Smart Waste Collection Management System is a database project developed using Oracle SQL and PL/SQL. It helps manage waste collection records, collection locations, waste categories, and recycling information.

The system stores waste collection data and generates reports to calculate total waste and the percentage of recyclable waste. It uses database constraints, triggers, procedures, functions, and cursors to maintain data accuracy and simplify waste management.

## 2. Objectives

- To maintain records of waste collection locations.
- To store different types of waste and their recycling status.
- To record the quantity of waste collected at different locations.
- To validate waste quantities and prevent invalid entries.
- To calculate the recycling percentage.
- To generate waste collection reports.
- To calculate the total quantity of collected waste and category-wise waste.

## 3. Technologies Used

- **Database:** Oracle Database
- **Language:** SQL and PL/SQL
- **Database Tool:** Oracle SQL Developer or Oracle SQL*Plus

## 4. Database Tables

The project contains three main tables.

### A. Collection_Locations

Stores information about waste collection locations.

| Column | Description |
|---|---|
| Location_ID | Unique ID of the location |
| Location_Name | Name of the collection location |
| Area_Name | Area where the location is situated |

### B. Waste_Categories

Stores waste categories and their recycling status.

| Column | Description |
|---|---|
| Category_ID | Unique ID of the waste category |
| Category_Name | Name of the waste category |
| Is_Recyclable | Y for recyclable and N for non-recyclable |

### C. Waste_Collections

Stores individual waste collection records.

| Column | Description |
|---|---|
| Collection_ID | Unique ID of the collection record |
| Location_ID | ID of the collection location |
| Category_ID | ID of the waste category |
| Quantity_Kg | Quantity of waste collected in kilograms |
| Collection_Date | Date of waste collection |

## 5. Main Features

### 1. Waste Collection Management

The system records waste collection details, including the location, category, quantity, and collection date.

### 2. Data Validation Trigger

The trigger `trg_validate_waste` checks the waste quantity before inserting or updating a record. It prevents quantities that are zero or negative.

### 3. Add Waste Collection Procedure

The procedure `Add_Waste_Collection` inserts new waste collection records. It validates the quantity and handles duplicate collection IDs and invalid location or category references.

### 4. Recycling Percentage Function

The function `Calculate_Recycling_Percentage` calculates the percentage of recyclable waste using the following formula:

**Recycling Percentage = (Recyclable Waste / Total Waste) × 100**

The result is rounded to two decimal places.

### 5. Waste Collection Report

The procedure `Display_Waste_Collections` uses a cursor to display collection IDs, locations, waste categories, and quantities.

### 6. Total Waste Calculation

The SQL query calculates the total quantity of waste collected across all records.

### 7. Category-Wise Waste Report

The system groups waste by category and displays the total quantity collected for each category in descending order.

## 6. Sample Data

The initial records include the following locations:

- Green Park — North Area
- City Market — Central Area
- College Road — South Area

The waste categories include Plastic, Paper, Metal, Organic, and Mixed Waste.

The initial collection records contain different waste quantities collected between October 20 and October 22, 2026. The project also adds an additional collection record using the `Add_Waste_Collection` procedure.

## 7. How to Run the Project

1. Open Oracle SQL Developer or Oracle SQL*Plus.
2. Connect to your Oracle database.
3. Enable output using `SET SERVEROUTPUT ON;`.
4. Execute the table creation statements.
5. Insert the sample locations, categories, and collection records.
6. Execute the `COMMIT;` statement.
7. Create the validation trigger.
8. Create the `Add_Waste_Collection` procedure and execute its sample call.
9. Create the `Calculate_Recycling_Percentage` function and run the percentage calculation block.
10. Create the `Display_Waste_Collections` procedure and execute it.
11. Run the final SQL queries to display total waste and category-wise waste.

**Important:** Execute the statements in the correct order because foreign keys depend on the parent tables. If you run the script again, existing tables and records may cause errors.

## 8. Expected Output

The project displays:

- A message confirming successful insertion of a waste collection record.
- The calculated recycling percentage.
- A report containing collection IDs, locations, waste types, and quantities.
- The total quantity of waste collected.
- The total waste quantity for each category.

The exact results depend on the records stored in the database.

## 9. Advantages

- Improves the organization of waste collection records.
- Reduces invalid data entry.
- Helps monitor recyclable and non-recyclable waste.
- Generates useful waste collection reports.
- Demonstrates database programming concepts using PL/SQL.

## 10. Future Scope

- Add a graphical user interface using HTML, CSS, and JavaScript.
- Create dashboards showing waste collection statistics.
- Add monthly and yearly waste collection reports.
- Track collection vehicles and pickup schedules.
- Introduce user authentication and role-based access.

## 11. Conclusion

The Smart Waste Collection Management System demonstrates how Oracle SQL and PL/SQL can be used to manage waste collection information efficiently. The project uses relational tables, constraints, triggers, stored procedures, functions, cursors, and aggregate queries to maintain records, validate data, calculate recycling statistics, and generate reports.

It provides a basic database solution that can be extended into a more comprehensive smart waste management application.
