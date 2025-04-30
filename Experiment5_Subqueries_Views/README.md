# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```
### Submission:

Dharshni V M - 212223240029

**Question 1**

![Q1](https://github.com/user-attachments/assets/97f90fab-1c6c-4749-9d54-c35cd1d286c0)

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM orders
    WHERE customer_id = 3007
);
```

**Output:**

![A1](https://github.com/user-attachments/assets/c6b4b708-d329-4cff-9b92-5018f83d3e64)

**Question 2**

![Q2](https://github.com/user-attachments/assets/efc4d49a-46f5-4d13-8a49-807de614b872)

```sql
SELECT *
FROM GRADES g
WHERE grade = (
    SELECT MAX(grade)
    FROM GRADES
    WHERE subject = g.subject
);
```

**Output:**

![A2](https://github.com/user-attachments/assets/5d9be0ef-4003-4130-845d-b6d719318fb1)

**Question 3**

![Q3](https://github.com/user-attachments/assets/7ead818b-f9f1-403d-af54-035675af6782)

```sql
SELECT *
FROM Medications
WHERE CAST(REPLACE(dosage, 'mg', '') AS INT) = (
    SELECT MIN(CAST(REPLACE(dosage, 'mg', '') AS INT))
    FROM Medications
);
```

**Output:**

![A3](https://github.com/user-attachments/assets/f0303c57-f11b-4045-96ee-e36ce122dc50)

**Question 4**

![Q4](https://github.com/user-attachments/assets/0ca2757b-19eb-4537-bd95-419e109ea0f3)

```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM ORDERS o
JOIN SALESMAN s ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';
```

**Output:**

![A4](https://github.com/user-attachments/assets/2e8365ae-8e00-45d5-81ee-f23f0c2069e9)

**Question 5**

![Q5](https://github.com/user-attachments/assets/20f7fe8b-65cf-4873-94c8-eb9c86d934c7)

```sql
SELECT *
FROM CUSTOMERS
WHERE AGE < 30;
```

**Output:**

![A5](https://github.com/user-attachments/assets/e52e19a0-9d13-4df2-b02b-62384067520c)

**Question 6**

![Q6](https://github.com/user-attachments/assets/702f885c-db8e-42db-80a7-e92dcf0a30b1)

```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam';
```

**Output:**

![A6](https://github.com/user-attachments/assets/bce81ba8-2675-419e-92a3-20671a9e4c79)

**Question 7**

![Q7](https://github.com/user-attachments/assets/b9d32099-11b7-41b6-ae78-1ab6e1c295b8)

```sql
SELECT g.student_name, g.grade
FROM GRADES g
JOIN (
    SELECT subject, MIN(grade) as min_grade
    FROM GRADES
    GROUP BY subject
) subq ON g.subject = subq.subject AND g.grade = subq.min_grade
ORDER BY g.student_name;
```

**Output:**

![A7](https://github.com/user-attachments/assets/c0701887-0bdf-4ee6-ba63-5c3771700fa9)

**Question 8**

![Q8](https://github.com/user-attachments/assets/2ff96b0b-d6f5-4087-a2dc-bc17ed5352ad)

```sql
SELECT s.salesman_id, s.name
FROM salesman s
JOIN (
    SELECT salesman_id, COUNT(customer_id) as customer_count
    FROM customer
    GROUP BY salesman_id
    HAVING COUNT(customer_id) > 1
) c ON s.salesman_id = c.salesman_id
ORDER BY s.salesman_id;
```

**Output:**

![A8](https://github.com/user-attachments/assets/816abc91-e77c-4a19-8cc5-57847024395d)

**Question 9**

![Q9](https://github.com/user-attachments/assets/7d97c734-2746-4a63-8b13-ce70ba3f23bc)

```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 4500
ORDER BY ID;
```

**Output:**

![A9](https://github.com/user-attachments/assets/10bff39f-3e2d-4197-a9b5-544c6eb000c8)

**Question 10**

![Q10](https://github.com/user-attachments/assets/366882ff-295b-4ae9-9247-e4ab56245843)

```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(*) = 1
)
ORDER BY id;
```

**Output:**

![A10](https://github.com/user-attachments/assets/c6a49bc4-52ad-4b6c-ae65-ca7f222acddc)

### Module-4 Grade:

![M4](https://github.com/user-attachments/assets/b232084d-0a46-49d6-b209-3a39d8b973f9)

## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
