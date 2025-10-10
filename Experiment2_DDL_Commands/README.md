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

<img width="1011" height="263" alt="image" src="https://github.com/user-attachments/assets/7f25da54-9bcc-474a-9dcb-e884e6e37e94" />

**SQL Code**
```
CREATE TABLE Invoices (InvoiceID INT PRIMARY KEY,InvoiceDate DATE,DueDate DATE CHECK(DueDate >InvoiceDate),Amount REAL CHECK(Amount>0));
```

**Output:**

<img width="1293" height="265" alt="image" src="https://github.com/user-attachments/assets/7ad24bd8-b5db-4674-8a0f-506c06230f99" />


**Question 2**
 <img width="950" height="364" alt="image" src="https://github.com/user-attachments/assets/b0f53157-6525-4140-8b2f-76d96ccdc6c4" />

**SQL Code**
```
CREATE TABLE Customers(CustomerID INTEGER,Name TEXT,Email TEXT,JoinDate DATETIME);
```

**Output:**

<img width="1298" height="363" alt="image" src="https://github.com/user-attachments/assets/a350f343-67c7-4d16-af57-bf78a3dff753" />

**Question 3**

<img width="1074" height="186" alt="image" src="https://github.com/user-attachments/assets/03981992-ad13-4936-8e72-bc99b4f021cb" />

**SQL Code**
```
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary) VALUES (001,'Sarah Parker','Manager','HR',60000);
```

**Output:**
<img width="1279" height="230" alt="image" src="https://github.com/user-attachments/assets/659e3ec1-17d8-4fe5-9220-a8d95a558f8f" />


**Question 4**
<img width="1266" height="387" alt="image" src="https://github.com/user-attachments/assets/2f881137-1ab2-4433-ac7b-86a78e458b34" />

**SQL Code**
```
INSERT INTO Student_details(RollNo,Name,Gender)  
VALUES(205,'Olivia Green','F');
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)  
VALUES(207,'Liam Smith','M','Mathematic',85);
INSERT INTO Student_details(RollNo,Name,Gender,Subject)  
VALUES(208,'Sophia Johns','F','Science');
```

**Output:**
<img width="1279" height="248" alt="image" src="https://github.com/user-attachments/assets/46313ec7-4dc0-4d40-87a9-2f0b17449cf1" />


**Question 5**
<img width="1247" height="251" alt="image" src="https://github.com/user-attachments/assets/04a940a1-d0bc-4bc5-b684-2fb369c622be" />

**SQL Code**
```
CREATE TABLE ProjectAssignments (AssignmentID INTEGER PRIMARY KEY,
EmployeeID INTEGER ,
ProjectID INTEGER ,AssignmentDate NOT NULL,
FOREIGN KEY(EmployeeID) REFERENCES Employees(EmployeeID),
FOREIGN KEY(ProjectID) REFERENCES Projects(ProjectID));
```

**Output:**
<img width="1270" height="264" alt="image" src="https://github.com/user-attachments/assets/3d029b4d-1b65-49ab-98e7-eee213370a65" />


**Question 6**
<img width="1263" height="372" alt="image" src="https://github.com/user-attachments/assets/c5f54ecc-4a80-4bc8-9a2d-7c8a3e0bc4a6" />

**SQL Code**
```
ALTER TABLE employee ADD COLUMN department_id  INTEGER ;
ALTER TABLE employee ADD COLUMN  manager_id INTEGER DEFAULT NULL;
```

**Output:**
<img width="1270" height="277" alt="image" src="https://github.com/user-attachments/assets/1eb0185b-c3a4-4df0-b134-39914c9ad157" />


**Question 7**
<img width="722" height="269" alt="image" src="https://github.com/user-attachments/assets/37459246-5339-42f2-a810-a983714a7d1b" />

**SQL Code**
```
INSERT INTO Employee
SELECT EmployeeID, Name, Department, Salary
FROM Former_employees ;
```

**Output:**

<img width="1196" height="236" alt="image" src="https://github.com/user-attachments/assets/afedd95a-dd65-40f8-a107-080fd515215b" />


**Question 8**
<img width="1094" height="248" alt="image" src="https://github.com/user-attachments/assets/150203c7-0b1a-4fe4-81e9-57c7da9d66c3" />

**SQL Code**
```
CREATE TABLE Shipments(ShipmentID INTEGER PRIMARY KEY,ShipmentDate DATE,SupplierID INTEGER,OrderID INTEGER,FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),FOREIGN KEY (OrderID) REFERENCES Orders(OrderID));
```

**Output:**

<img width="1273" height="213" alt="image" src="https://github.com/user-attachments/assets/9b7acc2f-fb4e-4e06-9b23-361c77ab1469" />


**Question 9**
<img width="1279" height="361" alt="image" src="https://github.com/user-attachments/assets/3e08d08c-bf21-4a81-9627-0fd5a7feda34" />

**SQL Code**
```
CREATE TABLE Bonuses
(BonusID INTEGER PRIMARY KEY,EmployeeID INTEGER,BonusAmount REAL CHECK(BonusAmount>0),BonusDate DATE,Reason TEXT NOT NULL,FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID));
```

**Output:**

<img width="1268" height="262" alt="image" src="https://github.com/user-attachments/assets/2d8ec917-9289-4882-bdc1-a9a972130aa2" />


**Question 10**
<img width="959" height="457" alt="image" src="https://github.com/user-attachments/assets/11babcef-7e4e-4b23-ac8f-cb7ec187c59c" />

**SQL Code**
```
ALTER TABLE Student_details ADD COLUMN mobilenumb number;
```

**Output:**

<img width="1273" height="322" alt="image" src="https://github.com/user-attachments/assets/fa335af7-3ee8-4110-bcc8-a5164d23d733" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
