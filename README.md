# ⚽ Football Ticket Booking System - Database Design & SQL Queries

## 📌 Project Overview

This project is a **Football Ticket Booking System Database** designed using PostgreSQL.  
It manages users, football matches, and ticket bookings with proper relationships, constraints, and real-world SQL queries.

The goal of this project is to demonstrate **database design principles, normalization, and advanced SQL query skills**.

---

## 🧩 Database Structure

The system consists of **3 main tables**:

### 👤 Users Table
Stores information about platform users (fans and ticket managers).

- user_id (Primary Key)
- full_name
- email (Unique)
- role (Football Fan / Ticket Manager)
- phone_number

---

### ⚽ Matches Table
Stores football match details and ticket pricing.

- match_id (Primary Key)
- fixture (Team vs Team)
- tournament_category
- base_ticket_price
- match_status (Available, Sold Out, etc.)

---

### 🎫 Bookings Table
Stores ticket booking transactions.

- booking_id (Primary Key)
- user_id (Foreign Key → Users)
- match_id (Foreign Key → Matches)
- seat_number
- payment_status
- total_cost

---

## 🔗 Relationships

- One User → Many Bookings  
- One Match → Many Bookings  
- Bookings acts as a junction table between Users and Matches

---

## 🛠️ Technologies Used

- PostgreSQL
- SQL (DDL & DML)
- Database Constraints (PK, FK, UNIQUE, CHECK)
- JOIN Operations
- Aggregate Functions
- Subqueries

---

## 📊 Key SQL Concepts Practiced

- CREATE TABLE with constraints
- PRIMARY KEY & FOREIGN KEY relationships
- CHECK constraints for validation
- LEFT JOIN / INNER JOIN
- LIKE / ILIKE search queries
- COALESCE for NULL handling
- Subqueries (AVG, filtering)
- OFFSET & LIMIT (pagination)
- ORDER BY sorting

---

## 📌 Sample Queries Included

### 🔍 Available Champions League Matches
```sql
SELECT *
FROM Matches
WHERE tournament_category = 'Champions League'
AND match_status = 'Available';
