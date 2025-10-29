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

**Question 1**
--
<img width="1182" height="607" alt="image" src="https://github.com/user-attachments/assets/342973a5-170f-4cfc-9a57-44ed36599265" />


```
SELECT PatientID,COUNT(Medications) AS AvgMedications
FROM MedicalRecords
GROUP BY PatientID
```

**Output:**

<img width="1213" height="753" alt="image" src="https://github.com/user-attachments/assets/69d50cd1-fc70-43c1-8fff-c3b056ba3175" />


**Question 2**
---
<img width="1078" height="693" alt="image" src="https://github.com/user-attachments/assets/0c1076cd-74d0-4525-a7aa-c7c43d191a2c" />


```
SELECT PatientID,COUNT(*) AS TotalMedications
FROM Prescriptions
GROUP BY PatientID
```

**Output:**

<img width="785" height="792" alt="image" src="https://github.com/user-attachments/assets/51b97cc6-fa45-42bc-9402-20a232b2b258" />


**Question 3**
---
<img width="955" height="534" alt="image" src="https://github.com/user-attachments/assets/cb0fa6e0-7217-4787-8da4-21c1369a8a77" />


```
SELECT SUM(INVENTORY) AS total_available_amount
FROM fruits
WHERE price>0.5
```

**Output:**

<img width="598" height="366" alt="image" src="https://github.com/user-attachments/assets/f867664f-e508-4a6a-a9cf-48ddc846483f" />


**Question 4**
---
<img width="635" height="496" alt="image" src="https://github.com/user-attachments/assets/55a6d08a-8a00-488a-8ccf-54bbe7686c3f" />


```
SELECT COUNT(id) AS employees_in_california
FROM employee
WHERE city='California';
```

**Output:**

<img width="613" height="376" alt="image" src="https://github.com/user-attachments/assets/127f0f32-2757-4594-ac09-0d473628ea32" />


**Question 5**
---
<img width="550" height="486" alt="image" src="https://github.com/user-attachments/assets/4aa8fbdb-0f96-4000-90e8-4035e754b2f9" />


```
SELECT MIN(purch_amt) AS MINIMUM
FROM orders
```

**Output:**

<img width="581" height="360" alt="image" src="https://github.com/user-attachments/assets/05adba06-a564-4e4f-9be7-34a4f97a0117" />


**Question 6**
---
<img width="1048" height="473" alt="image" src="https://github.com/user-attachments/assets/6dfc4445-56dd-4f52-9c1d-2850baa8db42" />


```
SELECT SUM(workhour) AS 'Total working hours'
FROM employee1
```

**Output:**

<img width="648" height="371" alt="image" src="https://github.com/user-attachments/assets/c5c1939c-a9d0-450e-8bd1-b4aeb9689964" />


**Question 7**
---
<img width="1235" height="495" alt="image" src="https://github.com/user-attachments/assets/e108a4d5-e3e5-45f7-8207-eb832adae484" />


```
SELECT age, MIN(income) AS 'MIN(income)'
FROM employee
WHERE income<=400000
group by age
```

**Output:**

<img width="678" height="439" alt="image" src="https://github.com/user-attachments/assets/430ec9d0-75a4-45cd-a5aa-c61cf27ad1f8" />


**Question 8**
---
<img width="1177" height="476" alt="image" src="https://github.com/user-attachments/assets/517bc0df-93c0-4c78-b175-f7ee674066b2" />


```
SELECT category_id,MIN(price) AS Price
FROM products 
WHERE price<10
GROUP BY category_id
```

**Output:**

<img width="661" height="426" alt="Screenshot 2025-10-29 103102" src="https://github.com/user-attachments/assets/531fd14e-7d0e-488e-bcd7-7fa9561a42e4" />


**Question 9**
---
<img width="1234" height="566" alt="image" src="https://github.com/user-attachments/assets/9f2e632e-67a2-411e-8c2c-440d40993bea" />


```
SELECT city,SUM(Income) AS Income
FROM employee
GROUP BY city
HAVING SUM(Income)>200000;
```

**Output:**

<img width="659" height="586" alt="image" src="https://github.com/user-attachments/assets/cf7d956a-0f46-403d-8ec4-c52889fd0b15" />


**Question 10**
---
<img width="994" height="504" alt="image" src="https://github.com/user-attachments/assets/609f0177-c78d-49a8-a9d4-1db24056a4e8" />


```
SELECT DoctorID,COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY DoctorID
ORDER BY DoctorID;
```

**Output:**

<img width="788" height="668" alt="image" src="https://github.com/user-attachments/assets/44aa61e8-7f5b-43a5-af0d-91dedfce1a0c" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
