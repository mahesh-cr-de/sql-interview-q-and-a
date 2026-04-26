# sql-interview-q-and-a
# 📊 SQL Interview Questions & Answers

A curated collection of **top SQL interview questions with clear answers and explanations**, focused on real-world scenarios using **SQL Server and MySQL**.

---

## 🎯 Who is this for?

- Data Engineers  
- Data Analysts  
- SQL Developers  
- Anyone preparing for SQL interviews (Beginner → Advanced)

---

## 🧠 Topics Covered

- Window Functions (RANK, DENSE_RANK, ROW_NUMBER)
- Joins (including duplicates & NULL handling)
- Subqueries & Correlated Queries
- CTEs (Common Table Expressions)
- Aggregations & Grouping
- Real-world SQL problems

---

# 🧾 Questions & Answers

---

## 1. Nth Highest Salary

### ❓ Question
Find the Nth highest salary from the Employees table.

### ✅ Answer
```sql
SELECT Salary
FROM (
    SELECT Salary, DENSE_RANK() OVER (ORDER BY Salary DESC) AS rnk
    FROM Employees
) t
WHERE rnk = N;
