# Topic 4: File Organization

## Simplest Case: Fixed-Length Records

### Free Lists

* Stores the address of the first **deleted** record.
* Each deleted record stores the address of the next deleted record, forming a linked list.

---

## Variable-Length Records

* Used for data types such as `varchar`.
* Suitable for storing multiple record types in a single file.
* Useful for record types with repeating fields, such as arrays.

---

## Heap File (aka "Pile File")

* Records are inserted at the **end of the file** with no sorting.
* Requires a **linear search** due to the lack of sorting.
* Commonly used when populating a table for future use with undefined requirements.
* If frequent retrieval is needed, the table should later be optimized.

---

## Sequential File (aka "Ordered File")

* Records are stored in **search-key order**.

### Trade-Offs

* **Slow insertion**:

  * Requires computing the correct position for the new record.
  * Shifting existing records to maintain order.
* **Fast search**:

  * Search speed is quick due to the sorted nature of the file.

### Insertion Process

1. Locate the position for the new record.
2. If space is available, insert the record at that position.
3. If no space is available, insert the record in an **overflow block**.
4. Update the pointer chain in either case.

---

## Factors to Consider for File Organization

Suppose we have these tables:

* `student(id, name, address)`
* `course(course_id, coursename, location)`
* `enroll(id, course_id)`
* `dept(dept_name, budget)`

And the following queries:

1. Insert a new student and associate them with a course (1/day).
2. Insert a new course (100/month).
3. Find all students taking courses 1, 2, or 3 (10/day).
4. Insert a department (1/year).
5. Find all departments with budgets between 1 million and 10 million (6/month).

---

## Tools

### Hashing

* Ideal for **random search**.

#### When to Use Static vs. Dynamic Hashing

* **Static Hashing**:

  * Best for files with minimal growth and few insertions.
* **Dynamic Hashing**:

  * Handles frequent insertions efficiently.
  * Example: *Dynamic hashing with hash key `<attribute>`.*

#### Special Cases

* **No Searching Required**:

  * Use a **heap file**, especially when there are many insertions.
* **Range Search Required**:

  * Use a **B+ tree** for frequent insertions.
  * Use an **index-sequential file** for infrequent insertions.

---

### Approach to File Organization

For each table, evaluate:

1. Query types and their frequency.
2. The **search key**.
3. Whether the table is referenced in other queries.

The decision for file organization depends not only on operations involving the table itself but also on operations where the table is related to others.

#### Example: `Student` Table

* **Query Types**:

  * Insertions (e.g., adding a new student).
  * Random searches (e.g., finding students in specific courses).
* **Decision**: Use **dynamic hashing** to support frequent insertions and efficient random searches.
