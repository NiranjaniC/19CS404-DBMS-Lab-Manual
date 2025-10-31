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

<img width="763" height="342" alt="image" src="https://github.com/user-attachments/assets/6bf3cffe-734a-45c8-be9e-a57b98527cab" />

**SQL CODE**
```
SELECT medication_id AS  medic,medication_name,dosage FROM Medications WHERE dosage=(SELECT MIN(dosage) FROM Medications);
```

**Output:**

<img width="614" height="298" alt="image" src="https://github.com/user-attachments/assets/6caf7474-4944-4b4c-83d2-a2a0c8202e88" />

**Question 2**

<img width="525" height="429" alt="image" src="https://github.com/user-attachments/assets/fdead0b8-2da2-4dfa-9344-8f29e25f130d" />

**SQL Code**
```
SELECT * FROM CUSTOMERS WHERE ADDRESS='Delhi' AND AGE <30 ORDER BY ID;
```

**Output:**


<img width="865" height="283" alt="image" src="https://github.com/user-attachments/assets/b00bef6d-e54b-4763-bc40-cc7e3dbd8a14" />


**Question 3**

<img width="974" height="420" alt="image" src="https://github.com/user-attachments/assets/0472f281-fd66-4ad7-9d92-e02c8eb42fd5" />

**SQL CODE**
```
SELECT student_name,grade FROM GRADES g WHERE grade=(SELECT MIN(grade) FROM GRADES WHERE subject=g.subject);
```

**Output:**

<img width="540" height="348" alt="image" src="https://github.com/user-attachments/assets/bf13df6e-2606-465f-8ee8-bc88ae220718" />

**Question 4**


<img width="520" height="424" alt="image" src="https://github.com/user-attachments/assets/a6e3e97a-2c7a-47ff-9243-45a10890098e" />

**SQL CODE**
```
SELECT * FROM Employee  WHERE age <(SELECT AVG(age) from Employee WHERE income >1000000);
```

**Output:**


<img width="1092" height="316" alt="image" src="https://github.com/user-attachments/assets/5d2bb0ab-e27e-439f-8b80-4bcc6139f4ac" />


**Question 5**


<img width="530" height="509" alt="image" src="https://github.com/user-attachments/assets/3fd0dcca-6546-4280-bea8-a339cb4d5e1d" />

**SQL CODE**
```
SELECT * FROM CUSTOMERS WHERE AGE<30;
```

**Output:**


<img width="1001" height="436" alt="image" src="https://github.com/user-attachments/assets/e4b1f066-e84b-484e-94de-b55a00e08079" />


**Question 6**

<img width="538" height="464" alt="image" src="https://github.com/user-attachments/assets/b9b19c65-cc97-4dfc-b884-24b6c37ff842" />

**SQL CODE**
```
SELECT * FROM CUSTOMERS WHERE SALARY>4500;
```

**Output:**

<img width="896" height="341" alt="image" src="https://github.com/user-attachments/assets/6ce966aa-c51e-4072-bdc8-b493cf3fbf00" />

**Question 7**

<img width="499" height="542" alt="image" src="https://github.com/user-attachments/assets/1a9264fc-bd71-4717-b848-3f43b1525fd8" />

**SQL CODE**
```
SELECT o.ord_no AS ord_no,o.purch_amt AS purch_amt,o.ord_date AS ord_date,o.salesman_id AS salesman_id FROM orders o where o.salesman_id IN(SELECT salesman_id FROM salesman WHERE commission=(SELECT MAX(commission) FROM salesman))ORDER BY o.ord_no;
```

**Output:**

<img width="830" height="363" alt="image" src="https://github.com/user-attachments/assets/5e956952-e729-45f6-a899-23a8b0996f80" />


**Question 8**


<img width="1001" height="519" alt="image" src="https://github.com/user-attachments/assets/42eff42f-3ca6-4c79-be43-0d91a7dcbb06" />

**SQL CODE**
```
select * from orders o where salesman_id IN (select salesman_id from salesman where city="New York");
```

**Output:**


<img width="924" height="351" alt="image" src="https://github.com/user-attachments/assets/2c19ce68-6ea1-46f9-a2d5-eee222793649" />


**Question 9**

<img width="855" height="321" alt="image" src="https://github.com/user-attachments/assets/61592fad-a7bc-41fe-aa9d-21e725ccacf5" />

**SQL CODE**
```
SELECT department_id as depar,department_name from Departments where LENGTH(department_name)>(SELECT AVG(LENGTH(department_name)) FROM Departments);
```

**Output:**

<img width="472" height="315" alt="image" src="https://github.com/user-attachments/assets/be447a26-1b52-4187-b808-d4e1a89f288b" />

**Question 10**


<img width="542" height="436" alt="image" src="https://github.com/user-attachments/assets/82885027-6015-4eaf-9b0b-332e6f4932b8" />


**SQL CODE**
```
SELECT student_name,grade FROM GRADES g WHERE grade=(SELECT MAX(grade) FROM GRADES where subject=g.subject);
```

**Output:**

<img width="529" height="352" alt="image" src="https://github.com/user-attachments/assets/c8c82331-a4ef-4c03-9206-41d7d94e196b" />





## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
