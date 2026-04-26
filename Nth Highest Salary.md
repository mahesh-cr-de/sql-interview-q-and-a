# 📊 SQL Interview Series: Nth Highest Salary

## ❓ Interview Question
Write a SQL query to find the **Nth highest salary** from an `Employees` table.

---

## 🗂️ Table Structure

```sql
CREATE TABLE Employees (
    EmployeeID INT NOT NULL PRIMARY KEY,
    Name NVARCHAR(100) NOT NULL,
    Salary DECIMAL(10, 2) NOT NULL
);

INSERT INTO Employees (EmployeeID, Name, Salary)
VALUES
    (1, N'Alice', 90000),
    (2, N'Bob', 80000),
    (3, N'Charlie', 80000),
    (4, N'David', 70000),
    (5, N'Eve', 60000);

WITH RankedSalaries 
AS 
( 
SELECT *, 
DENSE_RANK() OVER (ORDER BY Salary DESC) as rnk 
FROM Employees 
) 
SELECT * 
FROM RankedSalaries 
WHERE rnk = 3;
