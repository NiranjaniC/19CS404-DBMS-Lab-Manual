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

<img width="1271" height="487" alt="image" src="https://github.com/user-attachments/assets/018e95a4-c18b-44e9-9c6d-a1200d704454" />

**SQL Code**
```
UPDATE Employees SET email="not available",commission_pct=0.55 WHERE department_id=110;
```

**Output:**

<img width="1281" height="310" alt="image" src="https://github.com/user-attachments/assets/12195507-b38d-428b-a1cd-f9ffebc1013b" />



**Question 2**
<img width="1163" height="539" alt="image" src="https://github.com/user-attachments/assets/5fe7916b-c254-4034-a0b3-20d249771d72" />

**SQL Code**
```
UPDATE Employees SET salary=salary+500,email='updated' WHERE  job_id='SA_REP' and commission_pct>0.15;
```

**Output:**
<img width="1269" height="432" alt="image" src="https://github.com/user-attachments/assets/fcb000ca-e7db-454b-af83-a9c4327eac6d" />



**Question 3**

<img width="853" height="380" alt="image" src="https://github.com/user-attachments/assets/e3ecd012-9a11-447c-b463-230566267ca3" />

**SQL Code**
```
UPDATE Suppliers SET address="58 Lakeview, Magnolia" WHERE supplier_id=5;
```

**Output:**

<img width="1283" height="318" alt="image" src="https://github.com/user-attachments/assets/644e7285-637f-42b5-a9a7-0a9b9e141170" />



**Question 4**

<img width="949" height="390" alt="image" src="https://github.com/user-attachments/assets/04751082-2202-4b87-98aa-4b77f5681ea5" />

**SQL Code**
```
UPDATE Sales SET total_sell_price=quantity*sell_price WHERE product_id=10;
```

**Output:**
<img width="1288" height="437" alt="image" src="https://github.com/user-attachments/assets/09287569-1815-4918-8c76-4095ea8bd822" />



**Question 5**

<img width="702" height="179" alt="image" src="https://github.com/user-attachments/assets/48ac1c5b-f426-4dfc-bda6-a3741ad52de8" />

**SQL Code**
```
UPDATE products SET availability=2*availability WHERE product_id=1;
```

**Output:**
<img width="1279" height="202" alt="image" src="https://github.com/user-attachments/assets/583b76df-c65b-4471-b9b0-22a6ab5966ae" />


**Question 6**

<img width="1275" height="375" alt="image" src="https://github.com/user-attachments/assets/7050a8b1-fc27-4054-9011-c6c2325d717a" />

**SQL Code**
```
DELETE FROM Customer WHERE CUST_CITY IS NOT ('New York') AND OUTSTANDING_AMT >5000;
```
**Output:**

<img width="1276" height="489" alt="image" src="https://github.com/user-attachments/assets/43c26326-772b-496d-aa0c-19f5ce2a1672" />


**Question 7**

<img width="997" height="385" alt="image" src="https://github.com/user-attachments/assets/26d352d1-9307-4928-a81f-bad7ef527832" />

**SQL Code**
```
DELETE FROM Surgeries WHERE surgery_date='2024-02-28';
```

**Output:**
<img width="1271" height="310" alt="image" src="https://github.com/user-attachments/assets/80ae6318-ee40-49a8-a465-cb8636b8b00e" />


**Question 8**

<img width="1192" height="432" alt="image" src="https://github.com/user-attachments/assets/72533224-aa3f-4a19-b4ec-a4b7ac8e1104" />

**SQL Code**
```
DELETE FROM doctors WHERE specialization IS NULL;
```

**Output:**
<img width="1154" height="796" alt="image" src="https://github.com/user-attachments/assets/f7df8da8-9dbf-4b5f-8d6f-7860e98e7527" />


**Question 9**

<img width="1314" height="701" alt="image" src="https://github.com/user-attachments/assets/ea781c13-e883-4c84-8d21-b37ce1dcda55" />

**SQL Code**
```
DELETE FROM Customer WHERE AGENT_CODE IN ('A003','A008');
```

**Output:**

<img width="964" height="721" alt="image" src="https://github.com/user-attachments/assets/3cc972ff-dc9b-41f7-a867-5e9dca5d66de" />


**Question 10**

<img width="1227" height="292" alt="image" src="https://github.com/user-attachments/assets/c4f400f4-2b15-4afe-90fe-d6bbf240d3da" />

**SQL Code**
```
DELETE FROM Customer WHERE CUST_COUNTRY='UK'AND WORKING_AREA='London' AND GRADE<3;
```

**Output:**

<img width="1302" height="342" alt="image" src="https://github.com/user-attachments/assets/0111b6ff-d5bc-4f9f-969b-d106b2027705" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
