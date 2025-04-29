# Experiment 4: Aggregate Functions, Group By and Having Clause

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
### Submission:
Dharshni V M - 212223240029

**Question 1**

![Q1](https://github.com/user-attachments/assets/4cdabff1-9c2d-4684-ac3c-c2577e1fd193)

```sql
SELECT PatientID, COUNT(*) AS
TotalAppointments
FROM Appointments
GROUP BY PatientID;
```

**Output:**

![A1](https://github.com/user-attachments/assets/031fff63-165f-4cf1-96cb-e1b394bb8602)

**Question 2**

![Q2](https://github.com/user-attachments/assets/76bc8f06-3c2b-4472-bb9e-94af3f81f850)

```sql
SELECT Gender, COUNT(*) AS TotalPatients
FROM Patients
GROUP BY Gender;
```

**Output:**

![A2](https://github.com/user-attachments/assets/d46c2269-a2a2-4951-a491-a7dc5dd5cd80)


**Question 3**

![Q3](https://github.com/user-attachments/assets/a6599ef0-15e3-41e4-bd18-eca85c9413e5)

```sql
SELECT Specialty,COUNT(*) AS TotalDoctors
FROM Doctors
GROUP BY Specialty;
```

**Output:**

![A3](https://github.com/user-attachments/assets/0d7e9ded-aeca-4109-a0e2-68a757261d21)

**Question 4**

![Q4](https://github.com/user-attachments/assets/1404b837-8f57-4d71-ac0f-fd33d53679bb)

```sql
SELECT name, max(income)
FROM employee
WHERE city = 'California'
ORDER BY income DESC
LIMIT 1;
```

**Output:**

![A4](https://github.com/user-attachments/assets/667cfab3-813e-4e27-bbd6-4d92aa5b09ac)

**Question 5**

![Q5](https://github.com/user-attachments/assets/eaf32067-5f11-4d62-9cb8-ad476ab6e5e7)

```sql
SELECT AVG(income) AS avg_income
FROM employee
WHERE name LIKE 'A%';
```

**Output:**

![A5](https://github.com/user-attachments/assets/ed3fef57-7d57-4d11-a483-0a53d1c196b5)

**Question 6**

![Q6](https://github.com/user-attachments/assets/e0a51703-3887-42a8-b64f-203115cef8b2)

```sql
SELECT SUM(purch_amt) AS TOTAL
FROM orders;
```

**Output:**

![A6](https://github.com/user-attachments/assets/0aa0457f-3e52-4203-ab99-22a4808f864e)

**Question 7**

![Q7](https://github.com/user-attachments/assets/fcb2caa2-1b6e-40f8-bde7-eaa35da6002c)

```sql
SELECT COUNT(*) AS employees_count
FROM employee
WHERE income > 50000;
```

**Output:**

![A7](https://github.com/user-attachments/assets/5016a8c6-6bb4-49e4-8698-009fa8408175)

**Question 8**

![Q8](https://github.com/user-attachments/assets/aa2c8bc7-c73f-4a54-861b-752ce08ec236)

```sql
SELECT category_id, MIN(price) AS Price
FROM products
GROUP BY category_id
HAVING MIN(price) < 10;
```

**Output:**

![A8](https://github.com/user-attachments/assets/c924862a-9907-4fea-9803-5d51c5012e03)

**Question 9**

![Q9](https://github.com/user-attachments/assets/394541bb-2973-4711-93a5-bdcef5e35c1c)

```sql
SELECT age, MAX(income)
FROM employee
GROUP BY age
HAVING MAX(income) > 2000000;
```

**Output:**

![A9](https://github.com/user-attachments/assets/dfea7b09-17a1-4007-9f4a-fe5d14088d9b)

**Question 10**

![Q10](https://github.com/user-attachments/assets/40b89150-5d76-4ca3-8cc3-0f3550868069)

```sql
SELECT city, AVG(income)
FROM employee
GROUP BY city
HAVING AVG(income) > 500000;
```

**Output:**

![A10](https://github.com/user-attachments/assets/7c8154c3-c706-402c-9efb-c7d9041be345)

### Module-3 Grade:

![M3](https://github.com/user-attachments/assets/7fd7f33a-0c11-47cc-8ba7-936f4529a783)

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
