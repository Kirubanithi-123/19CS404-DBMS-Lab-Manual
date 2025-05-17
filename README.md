# DBMS Laboratory Manual Submission

# AIM:
   Write a SQL query to find the salespeople who had more than one customer, returning salesman_id and name.

# THEORY:

JOIN: Combines rows from two or more tables based on a related column.

GROUP BY: Groups rows that have the same values into summary rows.

HAVING: Filters groups based on a condition (unlike WHERE which filters rows).

COUNT(): Returns the number of input rows matching a condition.

We will:

Join the salesman and customer tables using salesman_id.

Group the result by salesman_id and name.

Use HAVING COUNT(*) > 1 to find salespeople with more than one customer.

# SQL PROGRAM
```
SELECT s.salesman_id, s.name
FROM salesman s
JOIN customer c ON s.salesman_id = c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(DISTINCT c.customer_id) > 1;
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/3f452719-fd8d-4b76-aba1-452bca75db3f)

# RESULT:
These are the salespeople who are associated with more than one customer in the customer table.
Let me know if you want to see the sample data that leads to this result or need help generating test data.
