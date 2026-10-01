# 🍽️ Restaurant Management System

## 📌 About the Project

The **Restaurant Management System** is a DBMS project developed to manage important restaurant operations using a centralized relational database.

The system stores and manages information related to:

* 👨‍💼 Employees
* 👨‍💼 Managers
* 🧑‍🍳 Chefs
* 🧑‍💼 Waiters
* 👥 Customers
* 🍔 Menu Items
* 🧾 Restaurant Orders
* 💳 Payments
* 📦 Order Items

The project is implemented using **Oracle Database and SQL** and demonstrates important DBMS concepts such as ER modeling, relational schema, primary keys, foreign keys, constraints, normalization, and SQL queries.

---

## 🎯 Objectives

* Store and manage customer information
* Manage restaurant menu items
* Record customer orders
* Maintain payment details
* Manage employee information
* Establish relationships between database tables
* Maintain data integrity using primary and foreign keys
* Reduce data redundancy through normalization
* Retrieve useful information using SQL queries

---

## 🛠️ Technologies Used

| Technology           | Purpose                                |
| -------------------- | -------------------------------------- |
| Oracle Database      | Database Management                    |
| SQL                  | Creating and manipulating data         |
| Oracle SQL Developer | SQL execution and database development |
| ER Model             | Database design                        |
| Normalization        | Reducing data redundancy               |

---

## 🗂️ Database Tables

The project contains the following major tables:

1. `EMPLOYEE`
2. `MANAGER`
3. `WAITER`
4. `CHEF`
5. `CUSTOMER_NEW`
6. `CUSTOMER_LOCATION`
7. `MENU`
8. `RESTAURANT_ORDERS`
9. `PAYMENT`
10. `ORDER_ITEM`

### 🔗 Main Relationships

* Customer → Restaurant Orders
* Restaurant Orders → Payment
* Restaurant Orders → Order Item
* Menu → Order Item
* Employee → Manager
* Employee → Waiter
* Employee → Chef
* Employee → Employee (Supervisor relationship)

The `ORDER_ITEM` table connects orders and menu items, resolving the many-to-many relationship between orders and menu items.

---

## 🔑 Keys and Constraints

The project uses:

* **Primary Keys (PK)**
* **Foreign Keys (FK)**
* **UNIQUE constraints**
* **NOT NULL constraints**
* **CHECK constraints**

These constraints help maintain data integrity and consistency.

---

## 📊 Normalization

The database is normalized up to **Third Normal Form (3NF)**.

### Normalization Process

```text
UNF
 ↓
1NF
 ↓
2NF
 ↓
3NF
```

### 1NF

* Repeating groups are removed.
* Each attribute contains atomic values.
* Each order item is represented separately.

### 2NF

* Partial dependencies are removed.
* Customer and order information are separated.
* Order-specific attributes depend on `ORDER_ID`.

### 3NF

* Transitive dependencies are removed.
* Customer and location information are separated.
* `CUSTOMER_NEW` and `CUSTOMER_LOCATION` are used to organize customer and location data.

Normalization helps reduce redundancy and modification anomalies.

---

## 💻 SQL Concepts Implemented

The project demonstrates different SQL operations, including:

* `CREATE TABLE`
* `INSERT`
* `SELECT`
* `WHERE`
* `LIKE`
* `GROUP BY`
* `HAVING`
* `ORDER BY`
* Aggregate Functions

  * `SUM()`
  * `COUNT()`
  * `MIN()`
  * `MAX()`
  * `AVG()`
* `JOIN`
* `LEFT JOIN`
* Subqueries
* Filtering and reporting

The documentation includes SQL queries for employee analysis, customer orders, payments, revenue, menu items, and order analysis.

---

## 📁 Project Files

```text
Restaurant-Management-System/
│
├── README.md
│
├── DBMS Documentation.pdf
│
├── Restaurant Management System PPT.pptx
│
├── SQL/
│   ├── create_tables.sql
│   ├── insert_data.sql
│   └── queries.sql
│
├── ER-Diagram/
│   └── ER-Diagram.png
│
└── Normalization/
    ├── 1NF
    ├── 2NF
    └── 3NF
```

> Add the SQL files and ER diagram to the repository if you have them separately.

---

## 📈 Sample SQL Query

### Find the Minimum and Maximum Employee Salary

```sql
SELECT MIN(salary) AS minimum_salary,
       MAX(salary) AS maximum_salary
FROM employee;
```

### Find Total Salary by Employee Role

```sql
SELECT role,
       SUM(salary) AS total_salary
FROM employee
GROUP BY role;
```

### Find Highest-Priced Menu Item

```sql
SELECT *
FROM menu
WHERE price = (
    SELECT MAX(price)
    FROM menu
);
```

---

## 👩‍💻 Team Members

* **Kinthada Akshaya Sri Mahalakshmi**
* **Matta Pravallika**
* **Pachadi Jaya Sirisha**
* **Gali Prasanna Puja**

## The project documentation identifies Akshaya and Pravallika as project members and the presentation lists the four team members above.

## 🎓 Academic Project

**Department:** Computer Science and Engineering
**University:** Aditya University, Surampalem
**Academic Year:** 2026–2027
**Project:** DBMS Cornerstone Project

---

## 🚀 Future Enhancements

The system can be extended with:

* Online food ordering
* Table reservation
* Inventory management
* Automatic billing
* Employee attendance
* Sales reports
* Role-based access
* Mobile application
* Graphical User Interface

These extensions are also identified in the project documentation.

---

## 📌 Conclusion

The **Restaurant Management System** demonstrates the practical application of relational database concepts using Oracle Database and SQL.

The project organizes restaurant information into related tables, applies primary and foreign keys, uses normalization up to 3NF, and demonstrates SQL queries for retrieving and analyzing restaurant data.

---
