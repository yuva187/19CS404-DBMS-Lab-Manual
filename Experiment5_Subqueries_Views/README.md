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

**Question 1**
--
<img width="1213" height="692" alt="image" src="https://github.com/user-attachments/assets/05034d6f-39e9-46e6-abec-fc614075c0ca" />


```
SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);

```

**Output:**

<img width="1244" height="650" alt="image" src="https://github.com/user-attachments/assets/76ea8b87-f576-44c0-9f90-cb2eb7e58b22" />


**Question 2**
---
<img width="1095" height="733" alt="image" src="https://github.com/user-attachments/assets/4ace0e68-f4b6-4d2d-bd00-293c0c7d6faf" />


```
SELECT *
FROM CUSTOMERS
WHERE SALARY > 4500;

```

**Output:**

<img width="1179" height="490" alt="image" src="https://github.com/user-attachments/assets/6abbf610-d3a4-4f46-912f-deaf70b9a972" />


**Question 3**
---
<img width="1270" height="607" alt="image" src="https://github.com/user-attachments/assets/32a23f11-7700-4df6-afc7-a3f0fd208e35" />


```
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE purch_amt > (
    SELECT AVG(purch_amt)
    FROM orders
    WHERE ord_date = '2012-10-10'
);

```

**Output:**

<img width="1231" height="513" alt="image" src="https://github.com/user-attachments/assets/7e49b82c-d2c1-4737-8529-0279ba3b99e2" />


**Question 4**
---
<img width="927" height="716" alt="image" src="https://github.com/user-attachments/assets/93a7d15f-39a1-4b37-bd08-06316938372c" />


```
SELECT *
FROM CUSTOMERS
WHERE AGE < 30;
```

**Output:**

<img width="1184" height="634" alt="image" src="https://github.com/user-attachments/assets/6ad9b555-d794-486a-b034-08f708cb42b9" />


**Question 5**
---
<img width="1080" height="641" alt="image" src="https://github.com/user-attachments/assets/d81ca754-da00-429d-a477-b10135db9b35" />


```
SELECT id, name, age, city, income
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 250000
);

```

**Output:**

<img width="1307" height="531" alt="image" src="https://github.com/user-attachments/assets/9ce71043-17fa-4dbe-b1cb-81c0b2440698" />


**Question 6**
---
<img width="916" height="565" alt="image" src="https://github.com/user-attachments/assets/87024af2-7b4c-4e76-9927-7485b4a2282f" />


```
SELECT *
FROM CUSTOMERS
WHERE SALARY = 1500;

```

**Output:**

<img width="1100" height="366" alt="image" src="https://github.com/user-attachments/assets/fb8b00b0-6f56-43da-af3a-2ac1c529c07a" />


**Question 7**
---
<img width="896" height="612" alt="image" src="https://github.com/user-attachments/assets/671ecc39-7d5b-4777-914f-a8a5ef91ceb2" />


```
SELECT *
FROM CUSTOMERS
WHERE SALARY < 2500;

```

**Output:**

<img width="1117" height="477" alt="image" src="https://github.com/user-attachments/assets/0280ef37-0118-4423-9d88-bfabab5fac18" />


**Question 8**
---
<img width="887" height="458" alt="image" src="https://github.com/user-attachments/assets/0d6e188a-e03b-442f-b7a1-90507759c825" />


```
SELECT medication_id, medication_name, dosage
FROM Medications
WHERE dosage = (
    SELECT MAX(dosage)
    FROM Medications
);

```

**Output:**

<img width="801" height="426" alt="image" src="https://github.com/user-attachments/assets/267fb3ad-ec0c-4770-b38c-f5ae383fec1c" />


**Question 9**
---
<img width="1030" height="547" alt="image" src="https://github.com/user-attachments/assets/1bda67c5-2cac-4d7b-9c15-48e119e72338" />


```
SELECT id, name, age, city, income
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 1000000
);
```

**Output:**

<img width="1258" height="439" alt="image" src="https://github.com/user-attachments/assets/e6865fbf-87ea-4765-b1c0-9a3ff6b830d6" />


**Question 10**
---
<img width="1238" height="563" alt="image" src="https://github.com/user-attachments/assets/8deea8ea-c272-428a-9451-340bd14ee3ca" />


```
SELECT student_name, grade
FROM GRADES g
WHERE grade = (
    SELECT MIN(g2.grade)
    FROM GRADES g2
    WHERE g2.subject = g.subject
);

```

**Output:**

<img width="696" height="460" alt="image" src="https://github.com/user-attachments/assets/9a134e2d-4319-4e6e-9c9f-584ddab60340" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
