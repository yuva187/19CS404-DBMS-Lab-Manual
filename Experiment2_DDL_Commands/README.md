# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
Create a table named Shipments with the following constraints:
ShipmentID as INTEGER should be the primary key.
ShipmentDate as DATE.
SupplierID as INTEGER should be a foreign key referencing Suppliers(SupplierID).
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).

<img width="1836" height="294" alt="image" src="https://github.com/user-attachments/assets/2d140661-27cf-4780-ae48-461dc9eeef31" />

```
CREATE TABLE Shipments
( ShipmentID INTEGER PRIMARY KEY,
ShipmentDATE INTEGER,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY(SupplierID) REFERENCES Suppliers(SupplierID),
FOREIGN KEY(OrderID) REFERENCES Orders(OrderID)
); 
```
**Output:**

<img width="1747" height="256" alt="image" src="https://github.com/user-attachments/assets/ce320075-74ba-4a7f-aa03-d768d1cc5fa7" />

**Question 2**
---
Create a table named Products with the following constraints:

ProductID should be the primary key.
ProductName should be NOT NULL.
Price is of real datatype and should be greater than 0.
Stock is of integer datatype and should be greater than or equal to 0.

<img width="783" height="223" alt="image" src="https://github.com/user-attachments/assets/4d25373a-34af-4e08-a351-a4829a628c39" />

```
CREATE TABLE Products
( ProductID INTEGER PRIMARY KEY,
ProductName TEXT NOT NULL,
Price REAL CHECK (Price > 0),
Stock INTEGER CHECK (Stock >= 0)
);
```
**Output:**

<img width="1551" height="343" alt="image" src="https://github.com/user-attachments/assets/f49b0a9b-0376-4d43-8b88-43004c6134ac" />


**Question 3**
---
Insert all books from Out_of_print_books into Books

Table attributes are ISBN, Title, Author, Publisher, YearPublished

<img width="1037" height="309" alt="image" src="https://github.com/user-attachments/assets/88a0447b-9624-4b69-97e9-023e0301e1d7" />

```
INSERT INTO Books(ISBN, Title, Author, Publisher, YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished
FROM Out_of_print_books;

```

**Output:**

<img width="1897" height="344" alt="image" src="https://github.com/user-attachments/assets/158de74c-47d0-4c17-9c03-f872404bea21" />

**Question 4**
---
Create a table named Departments with the following columns:

DepartmentID as INTEGER
DepartmentName as TEXT
<img width="1057" height="284" alt="image" src="https://github.com/user-attachments/assets/e357a228-13bd-4a7d-9ba1-ebc1177ac8b9" />

```
CREATE TABLE Departments(
DepartmentID INTEGER,
DepartmentName TEXT
);
```
**Output:**

<img width="1857" height="410" alt="image" src="https://github.com/user-attachments/assets/51c9f524-828f-4faf-b0d3-86cd9036ba13" />


**Question 5**
---
Write a SQL query to Add a new column mobilenumber as number in the Student_details table.

Sample table: Student_details

```
 cid              name             type   notnull     dflt_value  pk
---------------  ---------------  -----  ----------  ----------  ----------
0                RollNo           int    0                       1
1                Name             VARCH  1                       0
2                Gender           TEXT   1                       0
3                Subject          VARCH  0                       0
4                MARKS            INT (  0                       0
```

<img width="1088" height="390" alt="image" src="https://github.com/user-attachments/assets/7a54af8e-7ec0-4d0e-a2a3-8b3dfd12b260" />



```
ALTER TABLE Student_details ADD mobilenumb number;

```

**Output:**

<img width="1872" height="433" alt="image" src="https://github.com/user-attachments/assets/605549c2-7366-4ce8-8e4b-90196b5c69fe" />


**Question 6**
---
Create a new table named item with the following specifications and constraints:
item_id as TEXT and as primary key.
item_desc as TEXT.
rate as INTEGER.
icom_id as TEXT with a length of 4.
icom_id is a foreign key referencing com_id in the company table.
The foreign key should set NULL on updates and deletes.
item_desc and rate should not accept NULL.


<img width="1098" height="267" alt="image" src="https://github.com/user-attachments/assets/d49d0160-b793-455d-ae8d-bac92286d7f5" />


```
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),
FOREIGN KEY (icom_id) REFERENCES company(com_id)
ON UPDATE SET NULL
ON DELETE SET NULL
);
```

**Output:**
<img width="1653" height="431" alt="image" src="https://github.com/user-attachments/assets/cfece7f9-8372-488b-9037-4ffd474cfdb8" />



**Question 7**
---
Insert the below data into the Employee table, allowing the Department and Salary columns to take their default values.
```
EmployeeID  Name         Position
----------  -----------  ----------
4           Emily White  Analyst
```
Note: The Department and Salary columns will use their default values.


<img width="726" height="260" alt="image" src="https://github.com/user-attachments/assets/611ba4c0-aa20-443e-926c-bc7e6f004261" />


```
INSERT INTO Employee (EmployeeID, Name, Position)
VALUES(4, 'Emily White', 'Analyst');
```

**Output:**

<img width="1227" height="399" alt="image" src="https://github.com/user-attachments/assets/7be447f2-c085-4954-9bfa-b2485707343f" />


**Question 8**
---
Insert the following employees into the Employee table:
```
EmployeeID  Name        Position    Department  Salary
----------  ----------  ----------  ----------  ----------
2           John Smith  Developer   IT          75000
3           Anna Bell   Designer    Marketing   68000
```


<img width="843" height="286" alt="image" src="https://github.com/user-attachments/assets/8f45dbd1-d286-4aa9-bb3b-ba83aa1aa8d4" />


```
INSERT  INTO Employee(EmployeeID, Name, Position, Department, Salary)
VALUES (2,'John Smith', 'Developer', 'IT', 75000),
(3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

<img width="1873" height="397" alt="image" src="https://github.com/user-attachments/assets/600aa83f-8e4f-492e-a403-3dd27aea8202" />


**Question 9**
---
Create a table named Bonuses with the following constraints:
BonusID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
BonusAmount as REAL should be greater than 0.
BonusDate as DATE.
Reason as TEXT should not be NULL.


<img width="1829" height="227" alt="image" src="https://github.com/user-attachments/assets/557a081a-746f-48ee-b89e-37ef71bf0976" />


```
CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
BonusAmount REAL CHECK (BonusAmount>0),
BonusDate INTEGER,
Reason TEXT NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```

**Output:**

<img width="1409" height="179" alt="image" src="https://github.com/user-attachments/assets/a46baf6e-77f0-4b09-a641-dfc08099a55d" />


**Question 10**
---
Write a SQL query to Add a new column Country as text in the Student_details table.

Sample table: Student_details
```
 cid              name             type   notnull     dflt_value  pk
---------------  ---------------  -----  ----------  ----------  ----------
0                RollNo           int    0                       1
1                Name             VARCH  1                       0
2                Gender           TEXT   1                       0
3                Subject          VARCH  0                       0
4                MARKS            INT (  0                       0
```


<img width="1169" height="423" alt="image" src="https://github.com/user-attachments/assets/47eb70f0-0de2-4f7f-be6a-626626e7e919" />

```
ALTER TABLE Student_details ADD COLUMN Country TEXT;
```

**Output:**

<img width="1621" height="374" alt="image" src="https://github.com/user-attachments/assets/6d6beae2-99d9-4f81-8e8f-ea72517a19f6" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
