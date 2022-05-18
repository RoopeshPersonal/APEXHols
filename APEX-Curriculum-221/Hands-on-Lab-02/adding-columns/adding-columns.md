# Add columns to the products table

## Introduction

The **PRODUCTS** table includes some columns such as image, price, and details. But there are other characteristics that customers would appreciate knowing about a  product, such as color, type of clothing, and department. For the same reason, you add these columns to the Products table.
To avoid data redundancy, you need to create three additional tables to normalize the data. Instead of creating these three tables for yourself, you'll use the **Create Lookup Table** feature.

In this lab, you learn how to add these three new columns to the **PRODUCTS** table and then create lookup tables for those new columns.

Estimated Time: 10 minutes

<!--
Watch the video below for a quick walk through of the lab.

[](youtube:klrFD971TtI)-->

### Objectives
In this lab, you will:
- Add new columns to the existing Products table
- Populate the new columns
- Create lookup tables

## Task 1: Add Columns to the Products Table

1. From your APEX workspace home page, click **SQL Workshop**.

2. Click **Object Browser**.

    ![](images/navigate-to-object-browser1.png " ")

3. Navigate to **PRODUCTS** Table. Click **Add Column** button.

    ![](images/products-add-column1.png " ")

4. For Color column, enter the following:

    * Add Column - enter **COLOR**
    * Type - select **VARCHAR2**
    * Length - enter **200**.  
    
    Click **Next**.

    ![](images/add-color-column.png " ")

6. Click **Finish**.

    ![](images/add-color-column2.png " ")

7. Click **Add Column** button.

    ![](images/add-department-column1.png " ")

8.  For Department column, enter the following:

    * Add Column - enter **DEPARTMENT**
    * Type - select **VARCHAR2**
    * Length - enter **200**.
    
    Click **Next**.

    ![](images/add-department-column2.png " ")

10. Click **Finish**.

    ![](images/add-department-column3.png " ")

11. Click **Add Column** button.

    ![](images/add-clothing-column1.png " ")

12. For Clothing column, enter the following:

    * Add Column - enter **CLOTHING**
    * Type - select **VARCHAR2**
    * Length - enter **200**.
    
    Click **Next**.

    ![](images/add-clothing-column2.png " ")

14. Click **Finish**.

    ![](images/add-clothing-column3.png " ")

## Task 2: Populate the new columns

1. From the Oracle APEX Home, click **SQL Workshop**.

2. Click **SQL Scripts**.

    ![](images/navigate-to-sql-scripts1.png " ")

3. Click **Create**.

    ![](images/click-create-sql-scripts1.png " ")

4. For Script Name, enter **Populating new columns**.

5. Copy the following script and paste into the editor.
    ```
    <copy>
    UPDATE
        (
                SELECT p.product_id,
                        p.product_name,
                        p.clothing,
                        p.color,
                        p.department,
                        p.product_details
                FROM   products p ) p
    SET    p.clothing = Substr(product_name, Instr(product_name, ' ',1,1)+1, Instr(product_name, ' ',1, 2)+1 - Instr(product_name, ' ',1,1)- 2),
        p.color =
        (
                SELECT c.color
                FROM   json_table (p.product_details, '$' COLUMNS ( color VARCHAR2(4000) path '$.colour') ) c),
        p.department =
        (
                SELECT g.department
                FROM   json_table (p.product_details, '$' COLUMNS ( department VARCHAR2(4000) path '$.gender') ) g)
    ```

    This script inserts the unique product type values (e.g. Shirt, Jacket, Skirt, etc.) into the CLOTHING column in the **Products** table. Similary, it inserts the unique department names (e.g. Boy's, Girl's, Men's, Women's) and color names into the DEPARTMENT and COLOR columns respectively based on information found in the JSON product details column in the **Products** table.

5. Click **Run**.

    ![](images/populate-column-data1.png " ")

6. Click **Run Now**.

    ![](images/run-script1.png " ")

7. The Script Results page is displayed listing the statements processed, successful, and with errors.

    ![](images/sql-scripts-results1.png " ")

8. To check the values in the Products table, click **SQL Workshop** and click **SQL Commands**.

    ![](images/open-sql-commands.png " ")

9. Copy the following SQL Query.
    ```
    <copy>
    SELECT p.product_name,
           p.unit_price,
           p.color,
           p.department,
           p.clothing
    FROM   products p;
    ```

10. Click **Run**.

    ![](images/run-sql-query1.png " ")

## Task 3: Create Lookup Tables
Since multiple products may have the same values for Color, Department, and Clothing, to avoid repetition and make updates easy, you can create a lookup table for each. A lookup table stores the value of the available colors, departments, or clothing in a single place, and then each product can reference the value from the lookup table.

In this lab, you create lookup tables based on the new three columns. After you create a lookup table, you will notice that a new table was created and the column in the PRODUCTS table has been renamed and the data type was changed to NUMBER.

1. From your APEX workspace home page, click **SQL Workshop**.

2. Click **Object Browser**.

    ![](./images/navigate-to-object-browser2.png " ")

3. Navigate to **PRODUCTS** Table.

4. Click **Create Lookup Table** button.

    ![](./images/create-lookup-tables1.png " ")

5. For Column, select **COLOR - varchar2**.
   Click **Next**.

    ![](./images/create-color-lookup.png " ")

7. Leave the table and sequence name by default:

    * New Table Name: **COLOR_LOOKUP**
    * New Sequence: **COLOR\_LOOKUP\_SEQ**

    Click **Next**.

    ![](./images/create-color-lookup1.png " ")

9. Click **Create Lookup Table**.

    ![](./images/create-color-lookup2.png " ")

    *Note: Click the **Create Lookup Table** button only once. Then you will find the new table listed in the Object Browser.*

10. To create **Department** lookup table, navigate back to the **Products** table and Click **Create Lookup Table** button.

    ![](./images/create-lookup-tables2.png " ")

11. For Column, select **DEPARTMENT - varchar2**.

    Click **Next**.

    ![](./images/create-department-lookup.png " ")

13. Leave the table and sequence name by default:

    * New Table Name: **DEPARTMENT_LOOKUP**
    * New Sequence: **DEPARTMENT\_LOOKUP\_SEQ**

    Click **Next**.

    ![](./images/create-department-lookup1.png " ")

15. Click **Create Lookup Table**.

    ![](./images/create-department-lookup2.png " ")
    *Note: Click the **Create Lookup Table** button only once. Then you will find the new table listed in the Object Browser.*

16. To create **Clothing** lookup table, navigate back to the **Products** table and Click **Create Lookup Table** button.

    ![](./images/create-lookup-tables3.png " ")

17. For Column, select **CLOTHING - varchar2**.

    Click **Next**.

    ![](./images/create-clothing-lookup.png " ")

19. Leave the table and sequence name by default:

    * New Table Name: **CLOTHING_LOOKUP**
    * New Sequence: **CLOTHING\_LOOKUP\_SEQ**

    Click **Next**.

    ![](./images/create-clothing-lookup1.png " ")

21. Click **Create Lookup Table**.

    ![](./images/create-clothing-lookup2.png " ")
    *Note: Click the **Create Lookup Table** button only once. Then you will find the new table listed in the Object Browser.*

22. The columns COLOR, DEPARTMENT, and CLOTHING in the **Products** table are renamed to COLOR\_ID, DEPARTMENT\_ID, and CLOTHING\_ID respectively, and their data type changed to NUMBER. Also, there are new tables containing the values of the products:
    - COLOR_LOOKUP
    - DEPARTMENT_LOOKUP
    - CLOTHING_LOOKUP

The numeric value of the COLOR\_ID column will now store a reference to the system-assigned unique id of a particular color, whose name is stored in the new COLOR\_LOOKUP table. Similarly, the DEPARTMENT\_ID column references the id of a row in the DEPARTMENT\_LOOKUP table and CLOTHING\_ID references the id of a row in the CLOTHING\_LOOKUP table.    


![](./images/lookup-table-results.png " ")

You now know how to add new columns to your existing tables, how to create lookup tables for reference information, and how to create and run a SQL script to populate your tables. You may now **proceed to the next lab**.

## **Acknowledgments**

- **Author** - Roopesh Thokala, Product Manager
- **Last Updated By/Date** - Roopesh Thokala, Product Manager, March 2022
