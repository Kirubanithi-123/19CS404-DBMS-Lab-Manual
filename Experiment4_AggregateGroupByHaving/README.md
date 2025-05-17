# Experiment 4: Aggregate Functions, Group By and Having Clause
## Name:KIRUBANITHI.S
## Reg.no:212223220047
## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
How many prescriptions were written by each doctor?

Sample tablePrescriptions Table
```sql
SELECT DoctorID, COUNT(*)AS
TotalPrescriptions
FROM Prescriptions
GROUP BY DoctorID;
```

**Output:**

![image](https://github.com/user-attachments/assets/c167dabc-c2c9-4106-bcca-c18880150f56)

**Question 2**
---
How many patients are covered by each insurance company?

Sample table:Insurance Table

name               type
-----------------  ----------
InsuranceID        INTEGER
PatientID          INTEGER
InsuranceCompany   TEXT
PolicyNumber       TEXT
PolicyHolder       TEXT
ValidityPeriod     TEXT
```sql
SELECT InsuranceCompany,
COUNT ( DISTINCT PatientID )AS
TotalPatients
FROM Insurance
GROUP BY InsuranceCompany;
```

**Output:**

![image](https://github.com/user-attachments/assets/c25145e6-49b7-449f-af07-c62908d2d9d3)

**Question 3**
---
How many patients are there in each city?
```sql
SELECT Address, COUNT(*)AS
TotalPatients
FROM Patients
GROUP BY Address;
```

**Output:**

![image](https://github.com/user-attachments/assets/d7bd7d51-a58b-4e14-8c60-17d30e3ee46a)

**Question 4**
---
Write a SQL query to find the minimum purchase amount.

Sample table: orders

ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001

 
```sql
SELECT MIN(purch_amt)AS
MINIMUM
FROM orders;
```

**Output:**

![image](https://github.com/user-attachments/assets/15e134e8-bbc2-41e6-ba4b-1e62b8ca8687)

**Question 5**
---
Write a SQL query to return the total number of rows in the 'customer' table where the city is not Noida.
```sql
SELECT COUNT(*)AS 
COUNT
FROM customer
WHERE city!='Noida';
```

**Output:**
![image](https://github.com/user-attachments/assets/09cc58d4-df2d-42ce-94e1-8f3ffeb6e0fb)

**Question 6**
---
Write a SQL query to find the maximum purchase amount.

Sample table: orders

ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001
```sql
SELECT MAX (purch_amt)AS MAXIMUM
FROM orders;
```

**Output:**

![image](https://github.com/user-attachments/assets/9c2da4d5-7495-4340-9dfa-0e4cbebd9bb9)


**Question 7**
---
Write a SQL query to Calculate the average email length (in characters) for people who lives in Mumbai city

Table: customer

name        type
----------  ----------
id          INTEGER
name        TEXT   
city        TEXT
email       TEXT
phone       INTEGER
```sql
SELECT AVG(LENGTH(email))AS
avg_email_length_below_30
FROM customer
WHERE city='Mumbai';
```

**Output:**

![image](https://github.com/user-attachments/assets/e25ac842-d61f-4e94-8de2-07c87a75b5f4)

**Question 8**
---
Write the SQL query that achieves the grouping of data by age intervals using the expression (age/5)5, calculates the average age for each group, and excludes groups where the average age is not less than 24.
```sql
SELECT
  (age/5)*5 AS age_group ,
   AVG(age)
FROM customer1
GROUP BY age_group 
HAVING AVG(age)<24;
```

**Output:**

![image](https://github.com/user-attachments/assets/283efdf3-2a68-4c5c-b260-4d469e16ade8)

**Question 9**
---
Write the SQL query that achieves the selection of category and calculates the sum of the product of price and category ID as Revenue for each category from the "products" table, and includes only those products where the total revenue is greater than 25.
```sql
SELECT CATEGORY_ID, SUM(price*category_id) AS Revenue
FROM products
GROUP BY category_id
HAVING SUM(price *category_id)>25;
```

**Output:**

![image](https://github.com/user-attachments/assets/512114e8-146d-418e-92e8-bc86577a68c6)

**Question 10**
---
How many medical records are there for each patient?
```sql
select PatientID, count(RecordID) as 'TotalRecords'
from MedicalRecords
group by PatientID;
```

**Output:**

![image](https://github.com/user-attachments/assets/0db0e008-2675-4ff1-adb6-8552b4fc9f75)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
