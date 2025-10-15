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
**Question 1**
--
<img width="1193" height="585" alt="image" src="https://github.com/user-attachments/assets/9dd7ff70-7fbb-43f4-8dc8-3e25f2db5dbf" />


```
UPDATE employees
SET salary=salary*2
WHERE department_id=20 AND job_id LIKE '%MAN';
```

**Output:**

<img width="1124" height="246" alt="image" src="https://github.com/user-attachments/assets/a17d3e7d-d41d-4bd0-b0b7-83e6241b6b17" />


**Question 2**
---
<img width="1066" height="405" alt="image" src="https://github.com/user-attachments/assets/3623a099-9107-45d5-8333-f81a1cfb914a" />


```
UPDATE products
SET quantity=quantity*1.10;
```

**Output:**

<img width="1306" height="409" alt="image" src="https://github.com/user-attachments/assets/dc6913fc-a6b9-4df3-a182-9babe0b05e23" />

**Question 3**
---
<img width="829" height="589" alt="image" src="https://github.com/user-attachments/assets/94e82952-2c5a-4ad2-b803-0fcaa5e31b44" />


```
UPDATE employees
SET hire_date='2024-01-24'
WHERE department_id=50;
```

**Output:**

<img width="1194" height="318" alt="image" src="https://github.com/user-attachments/assets/09378c26-4798-45f4-b916-d136d5be5353" />


**Question 4**
---
<img width="887" height="285" alt="image" src="https://github.com/user-attachments/assets/e5ffa909-e5aa-4e0e-9066-a346a33a2e3c" />


```
UPDATE products 
SET product_name='Premium Bread'
WHERE product_id=5;
```

**Output:**

<img width="953" height="185" alt="image" src="https://github.com/user-attachments/assets/def0cda6-bac6-47c5-b416-8aa94a9125da" />


**Question 5**
---
<img width="595" height="394" alt="image" src="https://github.com/user-attachments/assets/d3168330-a8c0-4308-b426-fd0a9a9b88d7" />


```
DELETE FROM surgeries WHERE surgeon_id=3;
```

**Output:**

<img width="1029" height="361" alt="image" src="https://github.com/user-attachments/assets/325a3117-837a-4c3c-90a7-802040244997" />


**Question 6**
---
<img width="1232" height="535" alt="image" src="https://github.com/user-attachments/assets/84a661bd-0829-4e9f-94ce-b45e3179f48b" />

```
DELETE FROM customer
WHERE grade>=2;
```

**Output:**

<img width="568" height="491" alt="image" src="https://github.com/user-attachments/assets/7d51c2c8-6df5-4d6d-a1d9-98a30b7a543b" />


**Question 7**
---
<img width="1234" height="377" alt="image" src="https://github.com/user-attachments/assets/326d30dd-6484-4bd0-ae38-78873ed4c6a8" />

```
DELETE FROM customer
WHERE cust_country NOT IN ('India','USA');
```

**Output:**

<img width="1257" height="247" alt="image" src="https://github.com/user-attachments/assets/4c8cf0ab-686d-44db-9c1c-ca8bff292436" />


**Question 8**
---
<img width="582" height="438" alt="image" src="https://github.com/user-attachments/assets/c053dd36-d11f-4eb1-94b6-348fa9dafd52" />


```
DELETE FROM Doctors
WHERE last_name IS NULL;
```

**Output:**

<img width="1032" height="623" alt="image" src="https://github.com/user-attachments/assets/e2697318-bc24-4bcb-9f62-e3b571649df2" />

**Question 9**
---
<img width="707" height="513" alt="image" src="https://github.com/user-attachments/assets/26b4572c-2c62-4037-9da3-43c529d1ac72" />


```
DELETE FROM surgeries
WHERE surgery_id=3 OR surgeon_id=4;
```

**Output:**

<img width="1020" height="791" alt="image" src="https://github.com/user-attachments/assets/1ebf3fad-41dc-4e6a-ad99-bda075dd26cb" />


**Question 10**
---
<img width="647" height="321" alt="image" src="https://github.com/user-attachments/assets/b16e9711-2bac-430a-9b69-4ed94c849963" />


```
SELECT CategoryName,Description
FROM categories
ORDER BY CategoryName;
```

**Output:**

<img width="965" height="482" alt="image" src="https://github.com/user-attachments/assets/93525270-1cc1-479f-a647-4216d3d953e9" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
