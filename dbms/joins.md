In relational databases, **joins** are used to combine rows from two or more tables based on a related column. The key difference between **inner join** and **outer join** lies in how they handle unmatched rows between the tables.

---

### **1. Inner Join**
An **inner join** returns only the rows where there is a match in both tables based on the join condition. If no match is found, the row is excluded from the result.

#### Characteristics:
- Only matching rows are included.
- If there’s no match, the rows are dropped.
  
#### Syntax:
```sql
SELECT * 
FROM TableA 
INNER JOIN TableB 
ON TableA.column = TableB.column;
```

#### Example:
Consider two tables:

**TableA**  
| ID | Name  |
|----|-------|
| 1  | Alice |
| 2  | Bob   |
| 3  | Carol |

**TableB**  
| ID | Age |
|----|-----|
| 1  | 25  |
| 2  | 30  |
| 4  | 35  |

**Inner Join Query**:
```sql
SELECT * 
FROM TableA 
INNER JOIN TableB 
ON TableA.ID = TableB.ID;
```

**Result**:
| ID | Name  | Age |
|----|-------|-----|
| 1  | Alice | 25  |
| 2  | Bob   | 30  |

Unmatched rows (e.g., \( ID = 3 \) in TableA and \( ID = 4 \) in TableB) are excluded.

---

### **2. Outer Join**
An **outer join** includes rows that do not have matching rows in the other table. Depending on the type of outer join, unmatched rows are still included, with null values filling in where data is missing.

#### Types of Outer Join:
1. **Left Outer Join**: Returns all rows from the left table, and matched rows from the right table. If no match, NULLs are added for the right table's columns.
2. **Right Outer Join**: Returns all rows from the right table, and matched rows from the left table. If no match, NULLs are added for the left table's columns.
3. **Full Outer Join**: Returns all rows from both tables. Rows with no match in one table have NULLs for the missing columns.

#### Syntax:
- **Left Outer Join**:
  ```sql
  SELECT * 
  FROM TableA 
  LEFT JOIN TableB 
  ON TableA.column = TableB.column;
  ```
- **Right Outer Join**:
  ```sql
  SELECT * 
  FROM TableA 
  RIGHT JOIN TableB 
  ON TableA.column = TableB.column;
  ```
- **Full Outer Join**:
  ```sql
  SELECT * 
  FROM TableA 
  FULL OUTER JOIN TableB 
  ON TableA.column = TableB.column;
  ```

#### Example (Left Join):
Using the same tables as above:

**Left Join Query**:
```sql
SELECT * 
FROM TableA 
LEFT JOIN TableB 
ON TableA.ID = TableB.ID;
```

**Result**:
| ID | Name  | Age  |
|----|-------|------|
| 1  | Alice | 25   |
| 2  | Bob   | 30   |
| 3  | Carol | NULL |

Here, \( ID = 3 \) from TableA is included even though it has no match in TableB, with NULL for missing values.

#### Example (Full Outer Join):
```sql
SELECT * 
FROM TableA 
FULL OUTER JOIN TableB 
ON TableA.ID = TableB.ID;
```

**Result**:
| ID | Name  | Age  |
|----|-------|------|
| 1  | Alice | 25   |
| 2  | Bob   | 30   |
| 3  | Carol | NULL |
| 4  | NULL  | 35   |

---

### **Summary of Differences**
| Aspect           | Inner Join                          | Outer Join                                      |
|-------------------|-------------------------------------|------------------------------------------------|
| **Matching Rows** | Only matching rows are included.   | Includes both matching and non-matching rows. |
| **Unmatched Rows**| Excluded from the result.          | Included with NULLs for missing data.         |
| **Types**         | One type (just inner join).        | Left, Right, and Full outer joins.            |
| **Result Size**   | Smaller or equal to source tables. | Larger or equal to source tables.             |

Understanding the use case will help determine which join to use. For instance, **inner joins** are ideal for filtering matched records, while **outer joins** are better when you need a complete view of both datasets.