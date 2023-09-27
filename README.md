# Pentaho_ETL
The project involves using Pentaho software for ETL (Extract, Transform, Load) to process data from two Excel files: one containing order information and the other containing client information. The goal is to join these tables, perform various data transformations, and export two separate files, one for on-time orders and the other for late orders.

**Result Explanation:**
At the end of this ETL project, you will have two output files:
1. **Regular Orders File:** This file will contain information about orders that were delivered on time.
2. **Late Orders File:** This file will contain information about orders that were delivered late.

Now, let's break down the steps involved in this ETL project:

**Step 1: Reading Two Excel Files**
- In this step, you'll configure Pentaho to read two Excel files, one containing order data and another containing client data.

**Step 2: Sorting and Column Selection**
- After reading the files, sort the data as needed.
- Select only the relevant columns from both files. These columns may include order_id, customer_id, order_date, require_date, shipped_date, and client_country, among others.

**Step 3: Joining Tables on customer_id Field**
- Perform an inner join between the order data and client data using the customer_id field. This step links orders to their respective clients.

**Step 4: Selecting Specific Fields**
- After the join, select specific fields from the combined data, including order_date, require_date, and shipped_date.

**Step 5: Joining with Order Details Table**
- Integrate the selected data from the previous step with a table containing order details. Join these tables on the order_id field to combine order information with product details.

**Step 6: Data Transformation**
- Implement transformations to clean and enhance the data. For example:
    - Replace "UK" with "United Kingdom" and "USA" with "United States" in the client_country column.
    - Handle null values as per your business requirements (e.g., filling null values with appropriate defaults or removing records with null values).

**Step 7: Calculating Total Revenue and Time Difference**
- Create two new fields:
    - Calculate the total revenue for each order by aggregating product-level data.
    - Calculate the amount of time between the order date and shipping date, possibly as a new field representing the order processing time.

**Step 8: Exporting Data**
- Finally, export the transformed data into two separate files:
    - One file for regular orders (orders delivered on time).
    - Another file for late orders (orders delivered late).

These exported files can then be used for further analysis or reporting, and they will help you identify and manage orders that were delivered late. The ETL process in Pentaho ensures that the data is cleaned, transformed, and structured according to your business requirements before being exported for analysis or reporting purposes.
