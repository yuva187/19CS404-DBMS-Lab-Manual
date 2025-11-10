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

**Question 1**
--
<img width="1309" height="769" alt="image" src="https://github.com/user-attachments/assets/bacd4161-0c9f-42c1-a0ce-38d89e68651e" />

```
SELECT 
    c.cust_name, 
    c.city , 
    c.grade, 
    s.name AS Salesman, 
    s.city AS city
FROM customer c
JOIN salesman s
ON c.salesman_id = s.salesman_id
WHERE c.grade < 300
ORDER BY c.customer_id ASC;
```

**Output:**

<img width="1334" height="690" alt="image" src="https://github.com/user-attachments/assets/ea717ece-23ec-44fe-a8cb-0b926aed9e9a" />


**Question 2**
---
<img width="843" height="713" alt="image" src="https://github.com/user-attachments/assets/f3ce031f-76a8-42ac-8d18-f86777bfc4f5" />


```
SELECT
    s.name AS Salesman,
    c.cust_name,
    s.city
FROM
    salesman s 
INNER JOIN
    customer c 
ON
    s.city = c.city;
```

**Output:**

<img width="1331" height="627" alt="image" src="https://github.com/user-attachments/assets/c37ff877-041c-4052-97b0-27ec90beda77" />


**Question 3**
---
<img width="1324" height="287" alt="image" src="https://github.com/user-attachments/assets/a4af46d2-9034-4cea-8db1-2ca63e4ec383" />


```
SELECT s.name
FROM salesman s
LEFT JOIN customer c 
    ON s.salesman_id = c.salesman_id
WHERE c.city = 'New York';

```

**Output:**

<img width="1330" height="378" alt="image" src="https://github.com/user-attachments/assets/de34a3c7-80fb-4ce8-83f5-78127c60ac16" />


**Question 4**
---
<img width="542" height="607" alt="image" src="https://github.com/user-attachments/assets/1bf3239a-54ab-41c0-b99b-b67d7d492563" />


```
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM orders o
JOIN customer c 
    ON o.customer_id = c.customer_id
JOIN salesman s 
    ON o.salesman_id = s.salesman_id;

```

**Output:**

<img width="1378" height="775" alt="image" src="https://github.com/user-attachments/assets/1709f997-e00f-4c72-900d-4f567d51b9ad" />


**Question 5**
---
<img width="1344" height="473" alt="image" src="https://github.com/user-attachments/assets/a1419bdb-38d1-4c41-9c9c-aa250fb8a2e3" />


```
SELECT 
    p.*
FROM patients p
INNER JOIN doctors d 
    ON p.doctor_id = d.doctor_id
WHERE d.first_name = 'John'
  AND d.last_name = 'Smith';

```

**Output:**

<img width="1389" height="285" alt="image" src="https://github.com/user-attachments/assets/8c104522-a04b-47a3-9131-af77c7a2d455" />


**Question 6**
---
<img width="1347" height="551" alt="image" src="https://github.com/user-attachments/assets/eae70f60-96c6-49f7-8059-c1d0bdcefcce" />

```
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.city AS "city",
    s.commission
FROM customer c
JOIN salesman s 
    ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
  AND s.commission > 0.12;
```

**Output:**

<img width="1378" height="423" alt="image" src="https://github.com/user-attachments/assets/71c34f17-f517-4a3b-8f91-27820c55f4dc" />


**Question 7**
---
<img width="1209" height="716" alt="image" src="https://github.com/user-attachments/assets/94f0c566-b187-4a1a-9c2b-7441c182625b" />


```
SELECT 
    c.cust_name AS "cust_name",
    c.city AS "city",
    o.ord_no AS "ord_no",
    o.ord_date AS "ord_date",
    o.purch_amt AS "Order Amount"
FROM customer c
LEFT JOIN orders o 
    ON c.customer_id = o.customer_id
ORDER BY o.ord_date ASC;

```

**Output:**

<img width="1381" height="778" alt="image" src="https://github.com/user-attachments/assets/9d0b6b35-d71d-48b8-bee4-ccd150c14a94" />


**Question 8**
---
<img width="1353" height="421" alt="image" src="https://github.com/user-attachments/assets/957bd56e-bf7d-4c4c-aeac-dcd8db333f57" />

```
SELECT 
    n.nurse_id,
    d.department_name
FROM nurses n
INNER JOIN departments d 
    ON n.department_id = d.department_id
WHERE n.first_name = 'David'
  AND n.last_name = 'Moore';

```

**Output:**

<img width="1379" height="286" alt="image" src="https://github.com/user-attachments/assets/08835c03-67b0-42c8-a34d-4dcaa50c23e4" />


**Question 9**
---
<img width="1215" height="415" alt="image" src="https://github.com/user-attachments/assets/b4a9f4f4-c22b-49e2-a7d1-e6231f5d7232" />


```
SELECT 
    n.*, 
    d.department_name
FROM nurses n
INNER JOIN departments d 
    ON n.department_id = d.department_id;

```

**Output:**

<img width="1377" height="375" alt="image" src="https://github.com/user-attachments/assets/293ef9b7-81ec-4537-ac75-b800e0f12632" />


**Question 10**
---
<img width="1356" height="250" alt="image" src="https://github.com/user-attachments/assets/3f65d26d-1e82-4aa5-9e2e-62ba680d8348" />


```
SELECT 
    c.*
FROM customer c
LEFT JOIN orders o 
    ON c.customer_id = o.customer_id
WHERE o.ord_date BETWEEN '2012-08-01' AND '2012-08-30';

```

**Output:**

<img width="1376" height="336" alt="image" src="https://github.com/user-attachments/assets/c40fbbf4-849f-45c1-bcae-bc14018c57a7" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
