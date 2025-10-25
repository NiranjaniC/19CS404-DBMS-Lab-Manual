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

<img width="923" height="376" alt="image" src="https://github.com/user-attachments/assets/fc5d82a3-6641-46d4-b9b9-008c87cbd421" />

**SQL Code**

```
SELECT Frequency, COUNT(*) AS TotalPrescriptions FROM Prescriptions GROUP BY  Frequency;
```

**Output:**

<img width="854" height="419" alt="image" src="https://github.com/user-attachments/assets/b3292846-3bd0-474a-85c8-71b23f16535e" />

**Question 2**

<img width="588" height="427" alt="image" src="https://github.com/user-attachments/assets/c6597226-2cb9-4652-bbe6-3cbc5db4f37d" />

**SQL Code**

```
SELECT InsuranceCompany,COUNT(PatientID) AS TotalPatients FROM Insurance GROUP BY InsuranceCompany;
```

**Output:**

<img width="842" height="496" alt="image" src="https://github.com/user-attachments/assets/0f56a107-92ff-4ec5-b310-00d0677bf3bb" />

**Question 3**

<img width="963" height="424" alt="image" src="https://github.com/user-attachments/assets/fd0a47c9-8312-4465-ac76-9bda5e7aef38" />

**SQL Code**

```
SELECT Medication,COUNT(*) AS TotalPrescriptions FROM Prescriptions GROUP BY Medication;
```

**Output:**

<img width="771" height="540" alt="image" src="https://github.com/user-attachments/assets/b2f5c58b-f8eb-4136-8ab3-e0bb97f39d12" />

**Question 4**

<img width="651" height="337" alt="image" src="https://github.com/user-attachments/assets/1c290617-f84c-4a98-bb76-fca3385427a9" />

**SQL Code**

```
SELECT COUNT(*) AS COUNT FROM customer;
```

**Output:**

<img width="419" height="269" alt="image" src="https://github.com/user-attachments/assets/49eaabae-6d23-493f-975f-27a82f336223" />

**Question 5**

<img width="670" height="369" alt="image" src="https://github.com/user-attachments/assets/b72dde0f-c355-4aa6-80f1-71b7200090fc" />

**SQL Code**

```
SELECT name AS fruit_name,MIN(inventory) AS lowest_quantity FROM fruits GROUP BY name ORDER BY inventory ASC LIMIT 1;
```

**Output:**

<img width="686" height="260" alt="image" src="https://github.com/user-attachments/assets/821239a8-13f0-4518-81cc-33e112ca9cd2" />

**Question 6**

<img width="764" height="330" alt="image" src="https://github.com/user-attachments/assets/ca2cfe6b-958f-40d0-9b15-de6c5cf14f04" />

**SQL Code**

```
SELECT AVG(LENGTH(email)) AS avg_email_length_below_30 FROM customer WHERE  city='Mumbai';
```

**Output:**

<img width="538" height="250" alt="image" src="https://github.com/user-attachments/assets/58e3fe0f-b06d-45a1-a299-1224b20b9454" />

**Question 7**

<img width="654" height="312" alt="image" src="https://github.com/user-attachments/assets/67e8ee6c-d513-48ed-a3e0-3d808ab01581" />

**SQL Code**

```
SELECT name,max(length(name)) as length FROM customer;
```

**Output:**

<img width="640" height="245" alt="image" src="https://github.com/user-attachments/assets/d5edfb5f-becc-4778-8122-9ec713f5e3f6" />

**Question 8**

<img width="1310" height="333" alt="image" src="https://github.com/user-attachments/assets/4865adab-89d7-466d-b337-4bc7eaefdcc6" />

**SQL Code**

```
SELECT occupation,MIN(workhour) FROM employee1 GROUP BY occupation;
```

**Output:**

<img width="699" height="372" alt="image" src="https://github.com/user-attachments/assets/876c3a0a-877c-4c42-9e56-e229a579d1b9" />

**Question 9**
<img width="1301" height="342" alt="image" src="https://github.com/user-attachments/assets/3282c363-9c16-4d90-a118-5ef8de8c2502" />

**SQL Code**

```
SELECT occupation,SUM(workhour) FROM employee1 GROUP BY occupation;
```

**Output:**

<img width="754" height="346" alt="image" src="https://github.com/user-attachments/assets/b830f4ea-5f79-4425-b469-06a694ce2339" />

**Question 10**

<img width="1235" height="292" alt="image" src="https://github.com/user-attachments/assets/7e68c4d5-cd77-42af-8159-3996527ea6ea" />

**SQL Code**

```
SELECT category_id,AVG(Price) FROM products GROUP BY category_id HAVING AVG(Price) BETWEEN 10 AND 15;
```

**Output:**

<img width="858" height="266" alt="image" src="https://github.com/user-attachments/assets/f1a1b7b6-c011-4f2a-93b4-c5873eb8d322" />

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
