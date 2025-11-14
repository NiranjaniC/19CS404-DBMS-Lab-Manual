## Experiment 6: Joins

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

<img width="1315" height="620" alt="image" src="https://github.com/user-attachments/assets/933ad3c6-e8ec-4ccd-a7b1-4b590d2eaaa1" />

**SQL CODE**
```
SELECT 
    p.first_name AS patient_name,
    d.specialization AS Doctor_specialization
FROM 
    patients p
INNER JOIN 
    doctors d
ON 
    p.doctor_id = d.doctor_id
WHERE 
    p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

<img width="707" height="383" alt="image" src="https://github.com/user-attachments/assets/9fc9a564-2111-40f8-8bc4-a60f52568948" />

**Question 2**

<img width="1026" height="704" alt="image" src="https://github.com/user-attachments/assets/1d11f1bb-5156-4e2b-876e-272d6e03e9dd" />

**SQL CODE**
```
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission AS "commission"
FROM 
    customer c
INNER JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id;
```

**Output:**

<img width="1196" height="729" alt="image" src="https://github.com/user-attachments/assets/275462a3-5601-499d-9cc9-766b91f7aca1" />

**Question 3**

<img width="578" height="450" alt="image" src="https://github.com/user-attachments/assets/24012adf-fe32-420b-af42-db577614ef5b" />

**SQL CODE**
```
SELECT s.name AS Salesman, c.cust_name, s.city
FROM salesman s
INNER JOIN customer c ON s.city = c.city;
```
**Output:**

<img width="591" height="382" alt="image" src="https://github.com/user-attachments/assets/8d95f1e9-b26d-4cd6-8d40-2976eca1d4f7" />

**Question 4**

<img width="621" height="473" alt="image" src="https://github.com/user-attachments/assets/6b6c09be-82d8-4be8-8018-94ae21589ec4" />

**SQL CODE**
```
SELECT 
    c.cust_name,
    c.city,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM 
    customer c
JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
WHERE 
    c.grade < 300
ORDER BY 
    c.customer_id ASC;
```

**Output:**

<img width="918" height="417" alt="image" src="https://github.com/user-attachments/assets/900b8592-dd0b-4cd5-b56c-3fb7b66b36e0" />



**Question 5**

<img width="614" height="350" alt="image" src="https://github.com/user-attachments/assets/1d41a8fd-ba87-4295-9534-3fa5f25e3398" />

**SQL CODE**
```
SELECT 
    p.first_name AS patient_name,
    t.result_id,
    t.patient_id,
    t.test_name,
    t.result,
    t.test_date
FROM 
    patients AS p
INNER JOIN 
    test_results AS t
ON 
    p.patient_id = t.patient_id
WHERE 
    t.test_name = 'Blood Pressure';
```

**Output:**

<img width="968" height="240" alt="image" src="https://github.com/user-attachments/assets/16f307ef-012e-48d8-ad2a-002b0069f654" />


**Question 6**

<img width="614" height="207" alt="image" src="https://github.com/user-attachments/assets/cfffa984-2fe0-4483-8479-dacb28885329" />

**SQL CODE**
```
SELECT 
    c.cust_name
FROM 
    customer AS c
LEFT JOIN 
    orders AS o
ON 
    c.customer_id = o.customer_id
WHERE 
    o.purch_amt < 100;

```

**Output:**

<img width="369" height="268" alt="image" src="https://github.com/user-attachments/assets/b4ee2f0a-57ff-41db-9ec7-ba95bdda3485" />

**Question 7**

<img width="612" height="340" alt="image" src="https://github.com/user-attachments/assets/66eb9b1e-305f-42e0-bc14-43de488f575a" />

**SQL CODE**
```
SELECT p.*
FROM patients AS p
INNER JOIN appointments AS a
    ON p.patient_id = a.patient_id
WHERE a.appointment_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

<img width="1141" height="228" alt="image" src="https://github.com/user-attachments/assets/e3b54d25-1898-4b80-9c03-074cd60d9969" />

**Question 8**

<img width="634" height="748" alt="image" src="https://github.com/user-attachments/assets/d548314e-0c77-49f8-802f-068bfb2d5ecb" />

**SQL CODE**
```
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM orders AS o
INNER JOIN customer AS c
    ON o.customer_id = c.customer_id
INNER JOIN salesman AS s
    ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1320" height="639" alt="image" src="https://github.com/user-attachments/assets/23ac21d8-351c-4da5-890b-a806c5c54237" />

**Question 9**

<img width="1197" height="302" alt="image" src="https://github.com/user-attachments/assets/b84ea431-1685-4439-8634-b127facd3b78" />

**SQL CODE**
```
SELECT 
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM customer AS c
LEFT JOIN orders AS o
    ON c.customer_id = o.customer_id;
```

**Output:**

<img width="814" height="637" alt="image" src="https://github.com/user-attachments/assets/80a69ba1-b679-4a78-bbec-37354ea8b887" />


**Question 10**

<img width="1149" height="726" alt="image" src="https://github.com/user-attachments/assets/6c5b1f03-7ecf-4cd8-93dc-f9901dbe900d" />

**SQL CODE**
```
SELECT o.ord_no,o.purch_amt,o.ord_date,c.cust_name,c.city as 'customer_city',c.grade,s.name as'salesman_name',s.city as 'salesman_city',s.commission from orders o inner join customer c on o.customer_id=c.customer_id inner join salesman s on c.salesman_id=s.salesman_id;
```
**Output:**

<img width="1374" height="635" alt="image" src="https://github.com/user-attachments/assets/1400f08b-a241-4751-a6a8-cb976fe9554f" />

## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
