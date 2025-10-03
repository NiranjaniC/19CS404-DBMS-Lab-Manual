# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:

<img width="617" height="479" alt="Screenshot 2025-09-26 105209" src="https://github.com/user-attachments/assets/ce4456f9-ca41-411c-82a2-d57f94506836" />


### Entities and Attributes

| **Entity** | **Attributes (PK, FK)**                                            | **Notes**                              |
| ---------- | ------------------------------------------------------------------ | -------------------------------------- |
| Member     | MemberID (PK), Name, MembershipType, StartDate                     | Each member unique by MemberID         |
| Program    | ProgramID (PK), ProgramName, Description                           | Programs like Yoga, Zumba              |
| Trainer    | TrainerID (PK), Name, Specialization                               | A trainer can handle multiple programs |
| Session    | SessionID (PK), SessionDate, Type (Personal/Group), TrainerID (FK) | Sessions can be booked individually    |
| Attendance | AttendanceID (PK), SessionID (FK), MemberID (FK), Status           | Tracks who attended                    |
| Payment    | PaymentID (PK), MemberID (FK), Amount, Date, Purpose               | Membership fee or session fee          |

### Relationships and Constraints

| **Relationship**         | **Cardinality** | **Participation**   | **Notes**                                      |
| ------------------------ | --------------- | ------------------- | ---------------------------------------------- |
| Member–Program           | M:N             | Total on Member     | A member may join many programs                |
| Program–Trainer          | M:N             | Partial             | A trainer may be assigned to multiple programs |
| Member–Session (Booking) | M:N             | Partial             | Members book personal/group sessions           |
| Session–Attendance       | 1:M             | Total on Attendance | Tracks per session attendance                  |
| Member–Payment           | 1:M             | Total               | Each payment linked to a member                |

### Assumptions
- Membership types are predefined (e.g., Monthly, Yearly).

- A session is always handled by at least one trainer.

- Payments can be for membership renewal or personal training.

- Attendance is only recorded for booked sessions.


---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:

<img width="807" height="615" alt="image" src="https://github.com/user-attachments/assets/7214039b-8c4a-44cd-b26b-ecefee11cd15" />


### Entities and Attributes

| **Entity** | **Attributes (PK, FK)**                                       | **Notes**                |
| ---------- | ------------------------------------------------------------- | ------------------------ |
| **Member** | MemberID (PK), Name, Contact                                  | Library users            |
| **Book**   | BookID (PK), Title, Author, Category                          | Books available for loan |
| **Loan**   | LoanID (PK), MemberID (FK), BookID (FK), LoanDate, ReturnDate | Tracks borrowing         |
| **Event**  | EventID (PK), EventName, EventDate                            | Library events           |
| **Room**   | RoomID (PK), RoomName, Capacity                               | Rooms for study/events   |


### Relationships and Constraints

| **Relationship**   | **Cardinality** | **Notes**                                |
| ------------------ | --------------- | ---------------------------------------- |
| Member–Book (Loan) | M:N (via Loan)  | Members borrow books                     |
| Loan–Member        | M:1             | Each loan belongs to one member          |
| Event–Room         | M:1             | Each event is booked in one room         |
| Member–Event       | M:N             | Members can register for multiple events |


### Assumptions
- One book can only be borrowed by one member at a time.

- Events always occur in exactly one room.

- Each loan must be associated with a member.

- A member may attend zero or more events.

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
