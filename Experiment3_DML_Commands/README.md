# Experiment 3: DML Commands

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
### Submission:
Dharshni V M - 212223240029

**Question 1**

![Q1](https://github.com/user-attachments/assets/116a6853-79bd-41ca-92a3-707ac528d0b4)

```sql
UPDATE Products
SET sell_price = sell_price*1.15
WHERE quantity < 50;
```

**Output:**

![A1](https://github.com/user-attachments/assets/0b1eedf1-837b-4a02-a992-84ed5c2a6584)

**Question 2**

![Q2](https://github.com/user-attachments/assets/e77e7edc-d891-4bd0-8c79-03ad27fec8a8)

```sql
UPDATE Employees 
SET email = 'not available',
commission_pct = 0.55
WHERE department_id = 110;
```

**Output:**

![A2](https://github.com/user-attachments/assets/45ca420e-310b-4b3e-844b-9835d10c183c)

**Question 3**

![Q3](https://github.com/user-attachments/assets/0ea27e46-4672-4a30-98da-719c260ff3b2)

```sql
UPDATE Products
SET sell_price = sell_price*1.10
WHERE category = 'Bakery';
```

**Output:**

![A3](https://github.com/user-attachments/assets/66bd1e40-6caa-4130-a62d-bece57fc2536)

**Question 4**

![Q4](https://github.com/user-attachments/assets/38f71cd6-c19b-4602-b98b-04d1b2f8faa6)

```sql
DELETE FROM customer
WHERE GRADE % 2 != 0;
```

**Output:**

![A4](https://github.com/user-attachments/assets/82df8eff-6f91-46cf-8b7c-9f5adee6b7a9)

**Question 5**

![Q5](https://github.com/user-attachments/assets/30f84bdc-3c0b-457b-925f-8ffcdf2373a8)

```sql
DELETE FROM Doctors 
WHERE specialization = 'Cardiology';
```

**Output:**

![A5](https://github.com/user-attachments/assets/8adcea18-084e-445d-a6d0-457d36854428)

**Question 6**
---
![Q6](https://github.com/user-attachments/assets/03a1f1fc-33e5-4759-bad8-4adad668f59c)

```sql
DELETE FROM Customer
WHERE CUST_COUNTRY = 'UK'
AND WORKING_AREA = 'London'
AND GRADE < 3;
```

**Output:**

![A6](https://github.com/user-attachments/assets/28212a0c-8093-4c19-b549-3fdd9ce445b8)

**Question 7**
---
![Q7](https://github.com/user-attachments/assets/6bf3e31e-67ff-4464-8124-856a7c45bd6c)

```sql
SELECT CategoryName, Description
FROM categories
ORDER BY CategoryName;
```

**Output:**

![A7](https://github.com/user-attachments/assets/cc35947d-5cbb-4d86-9f5c-a20b6d27a35c)

**Question 8**

![Q8](https://github.com/user-attachments/assets/f2b07159-bbc0-41e3-a81d-1d211b456311)

```sql
SELECT *
FROM Employeeinfo
WHERE EmpLname LIKE '____A';
```

**Output:**

![A8](https://github.com/user-attachments/assets/f9cceba5-1d73-4f5e-aa3c-5f7b67f0ca6f)

**Question 9**

![Q9](https://github.com/user-attachments/assets/68e64c6f-0e29-4000-a81e-ea2323cab7ab)

```sql
SELECT salesman_id, name, city, commission
FROM salesman
WHERE city != 'Paris'
AND city != 'Rome';
```

**Output:**

![A9](https://github.com/user-attachments/assets/adfa70f0-a1bd-4047-94f4-61ea922761d9)

**Question 10**

![Q10](https://github.com/user-attachments/assets/5410ceeb-52d4-4ecd-9ccc-cbffe05047b4)

```sql
SELECT 
ename,
job,
(substr(ename,1,3) || substr(job,length(job)-2,3))
AS ConcatenatedString
FROM emp;
```

**Output:**

![A10](https://github.com/user-attachments/assets/c5fe27ed-7963-4e94-b1da-9a19a7ab528f)

### Module-2 Grade:

![M2](https://github.com/user-attachments/assets/855b0021-0928-4117-ab86-4d2fb7347adb)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
