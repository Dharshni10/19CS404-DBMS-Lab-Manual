# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

### Submission:
Dharshni V M - 212223240029

**Question 1**

![Q1](https://github.com/user-attachments/assets/86f0f82b-f296-41e9-a8e8-ce16d5b96cd2)

```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE o.ord_date > '2012-08-17';
```

**Output:**

![A1](https://github.com/user-attachments/assets/f8516f54-7094-45b6-bbb8-db76f1dedc33)

**Question 2**

![Q2](https://github.com/user-attachments/assets/039b1231-5e4c-4a79-b72a-b7d75fefa618)

```sql
SELECT o.ord_no, o.purch_amt, c.cust_name, c.city
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

![A2](https://github.com/user-attachments/assets/2bee1d92-7d8a-4693-b624-4737f655a5f7)

**Question 3**

![Q3](https://github.com/user-attachments/assets/523b4482-a604-47b7-9955-f7ab804a9492)

```sql
SELECT p.first_name, p.last_name
FROM patients p
INNER JOIN surgeries s ON p.patient_id = s.patient_id
WHERE s.surgery_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

![A3](https://github.com/user-attachments/assets/40e61828-d821-4109-9f7e-a19473c7d99c)

**Question 4**

![Q4](https://github.com/user-attachments/assets/c7597e3b-107a-4a30-9bc5-5aac862bedf1)

```sql
SELECT n.*, d.department_name
FROM nurses n
INNER JOIN departments d ON n.department_id = d.department_id;
```

**Output:**

![A4](https://github.com/user-attachments/assets/9903cd85-3a34-4435-a54c-22d7ad0d1686)

**Question 5**

![Q5](https://github.com/user-attachments/assets/a6311c8a-204a-4f4f-933d-6ac02c806f8b)

```sql
SELECT s.name AS Salesman, c.cust_name, s.city
FROM salesman s
JOIN customer c ON s.city = c.city;
```

**Output:**

![A5](https://github.com/user-attachments/assets/f9cf70a2-2799-4a1d-a8e5-92bed1dce11b)

**Question 6**

![Q6](https://github.com/user-attachments/assets/3ca1ad4d-c485-4c16-818b-084875bfe1e8)

```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount",
    s.name,
    s.commission
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
LEFT JOIN salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

![A6](https://github.com/user-attachments/assets/5b0b4ad7-0ca4-4fc3-9d8b-d9539fcdd4b8)

**Question 7**

![Q7](https://github.com/user-attachments/assets/3990de9e-a9d1-46b4-a232-b505aa7a5260)

```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
JOIN salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

![A7](https://github.com/user-attachments/assets/187549b3-f3bd-4628-8941-1c1bc005fae7)

**Question 8**

![Q8](https://github.com/user-attachments/assets/4ec79e6e-4167-4a7d-adcd-db3eaa0316fd)

```sql
SELECT s.name
FROM customer c
LEFT JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city = 'New York';
```

**Output:**

![A8](https://github.com/user-attachments/assets/06f28e23-d372-4a9c-b680-307a2c5f8019)

**Question 9**

![Q9](https://github.com/user-attachments/assets/7e13f3e0-d35e-4eda-9157-9c871c6fee66)

```sql
SELECT 
    c.cust_name AS "Customer Name", 
    c.city, 
    s.name AS "Salesman", 
    s.commission
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
WHERE 
    s.commission > 0.12;
```

**Output:**

![A9](https://github.com/user-attachments/assets/95251a85-96fc-4710-b27d-8da20ee3b819)

**Question 10**

![Q10](https://github.com/user-attachments/assets/07f1e53e-1ab6-44b2-93ad-e7f3dba1502b)

```sql
SELECT 
    p.* 
FROM 
    patients p
INNER JOIN 
    appointments a ON p.patient_id = a.patient_id
WHERE 
    a.appointment_date BETWEEN '2024-02-01' AND '2024-02-28';
```

**Output:**

![A10](https://github.com/user-attachments/assets/68c2edeb-c5d6-403e-9aa2-771210efac88)

### Module-5 Grade:

![WhatsApp Image 2025-04-30 at 22 54 50_4bc07a42](https://github.com/user-attachments/assets/2a409833-2a19-48fa-8ebc-e9c735e1468d)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
