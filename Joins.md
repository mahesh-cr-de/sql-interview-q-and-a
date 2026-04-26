# 🔗 SQL Joins Explained with Duplicates & NULLs

## 🎯 Problem Statement
Given two tables with duplicate values and NULLs, explain how different SQL joins behave.

---

## 🗂️ Input Tables

### Table1 (tabl1)

| c1   |
|------|
| 1    |
| 1    |
| 1    |
| 2    |
| NULL |

---

### Table2 (table2)

| c1   |
|------|
| 1    |
| 1    |
| 2    |
| 3    |
| NULL |
| NULL |

---

## ⚠️ Important Concepts

- Joins work on **matching conditions**
- `NULL = NULL` → ❌ FALSE (does NOT match)
- Duplicates → multiply results (**Cartesian effect within join condition**)

---
# Table creation scripts
```sql
--create table tbl1
CREATE TABLE tbl1 (
    c1 INT NULL
);

INSERT INTO tbl1 (c1)
VALUES
    (1),
    (1),
    (1),
    (2),
    (NULL);

-- create table tbl2
CREATE TABLE tbl2 (
    c1 INT NULL
);

INSERT INTO tbl2 (c1)
VALUES
    (1),
    (1),
    (2),
    (3),
    (NULL),
    (NULL);

-- INNER JOIN

SELECT t1.c1, t2.c1
FROM tabl1 t1
INNER JOIN table2 t2
ON t1.c1 = t2.c1;
