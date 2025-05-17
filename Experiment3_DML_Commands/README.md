# Experiment 3: DML Commands
## Name:KIRUBANITHI.S
## Reg.no:212223220047
## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
Write a SQL statement to update the product_name as 'Grapefruit' whose product_id is 4 in the products table.
```sql
update products
set product_name='Grapefruit'
where product_id=4;
```
**Output:**

![image](https://github.com/user-attachments/assets/7ab52d73-90fd-4248-811c-0a73081d6409)


**Question 2**
---
Write a SQL query to reduce the reorder level by 30% where cost price is more than 50 and quantity in stock is less than 100 in the products table.

```sql
update Products
set reorder_lvl=reorder_lvl*0.7
where cost_price>50 and quantity<100;
```

**Output:**

![image](https://github.com/user-attachments/assets/d3655583-9bf8-4b01-81c6-4d7f09a8ab1f)

**Question 3**
---
Write a SQL query to Delete a Specific Surgery which was made on 28th Feb 2024.

```sql
delete from Surgeries 
where surgery_date='2024-02-28';
```

**Output:**

![image](https://github.com/user-attachments/assets/7d3c2e09-199b-4a52-a773-b7ff278d4d62)


**Question 4**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is not equal to 3.

```sql
delete from customer
where GRADE!=3;
```

**Output:**

![image](https://github.com/user-attachments/assets/a16166ae-e70d-4dbb-b54b-1fb4c6fc7f46)


**Question 5**
---
 Write a query to fetch details of employees whose EmpLname ends with an alphabet ‘A’ and contains five alphabets.

```sql
select * from EmployeeInfo 
where EmpLname like '%A' and length(EmpLname)=5;
```

**Output:**

![image](https://github.com/user-attachments/assets/c89f1590-cf96-44d1-98ae-f1311b872bc0)

**Question 6**
---
Write a SQL query to classify base in the Calculations table as 'Provided' if it is not NULL, otherwise 'Not Provided'.

```sql
select id,base,
case when base is not NULL then 'Provided'
else 'Not Provided'
end as base_status
from Calculations;
```

**Output:**

![image](https://github.com/user-attachments/assets/4f58787b-ed34-4a47-891d-9a6d9b76e608)


**Question 7**
---
Write a SQL query to calculate the final price after applying both the discount and the tax. Return product_id, original_price, discount_percentage, tax_rate, and final_price.

```sql
select product_id,original_price,discount_percentage,tax_rate,(original_price*(1-discount_percentage))*(1+tax_rate) as final_price
from products;
```

**Output:**

![image](https://github.com/user-attachments/assets/7f750be9-fc15-4fb8-9f3c-469e66e4685d)

**Question 8**
---
Create a report that shows the capitalized FirstName and capitalized LastName renamed as FirstName and Lastname respectively and EmployeeId from the employees table sorted by EmployeeId in descending order.
```sql
select upper(FirstName) AS FirstName,upper(LastName) AS LastName,EmployeeId
from employees
order by EmployeeID desc;
```

**Output:**

![image](https://github.com/user-attachments/assets/9c849936-cec8-42bc-8232-cbfa3000a412)

**Question 9**
---
Write a SQL statement to retrieve city(column name) of all customers from customers table without any repeats.
```sql
select distinct city from customers;
```

**Output:**

![image](https://github.com/user-attachments/assets/8ee1e2c0-f61f-4004-b296-10d05a65beb2)

**Question 10**
---
Write a SQL statement to Double the salary for employees in department 20 who have a job_id ending with 'MAN'
```sql
update EMPLOYEES
SET SALARY= SALARY *2
WHERE JOB_ID like'%MAN';
```

**Output:**

![image](https://github.com/user-attachments/assets/b64a955b-c8db-4950-b89a-46c6b0936cb4)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
