---

# Topic 4: File Organization

## Simplest Case: Fixed-Length Records

### Free Lists
- Stores the address of the first **deleted** record.
- Each address points to the next deleted record, forming a linked list.

---

## Variable-Length Records
- Used for data types such as `varchar`.
- Suitable for storing multiple record types in a single file.
- Useful for record types with repeating fields, such as arrays.

---

## Heap File (aka "Pile File")
- Records are inserted at the **end of the file** with no sorting.
- Requires a **linear search** due to lack of sorting.
- Commonly used when populating a table for future use with undefined requirements.
- If frequent retrieval is needed, the table should later be optimized.

---

## Sequential File (aka "Ordered File")
- Records are stored in **search-key order**.

### Tradeoffs
- **Slow insertion**:
  - Requires computing the correct position for the record.
  - Shifting existing records to maintain order.
- **Quick search speed** due to the sorted nature of the file.

### Insertion Process
1. Locate the position for the new record.
2. If space is available, insert the record there.
3. If no space is available, use an **overflow block**.
4. Update the pointer chain in either case.

---

## Factors to Consider for File Organization

Suppose we have these tables:

- `student(id, name, address)`
- `course(course_id, coursename, location)`
- `enroll(id, course_id)`
- `dept(dept_name, budget)`

And the following queries:

1. Insert a new student and associate them with a course (1/day).
2. Insert a new course (100/month).
3. Find all students taking courses 1, 2, or 3 (10/day).
4. Insert a department (1/year).
5. Find all departments with budgets between 1 million and 10 million (6/month).

---

## Tools

### Hashing
- Ideal for **random search**.

#### When to Use Static vs. Dynamic Hashing:
- **Static Hashing**:
  - Best for files with minimal growth and insertions.
- **Dynamic Hashing**:
  - Handles frequent insertions efficiently.
  - Example: "Dynamic hashing with hash key `<attribute>`."

#### Special Cases
- **No Searching Required**: Use a **heapfile**, especially for frequent insertions.
- **Range Search Needed**:
  - Use a **B+ tree** for frequent insertions.
  - Use an **index-sequential file** for rare insertions.

---

### Approach to File Organization
For each table, evaluate:
1. Query types and frequency.
2. The **search key**.
3. Whether the table is referenced in other queries.

The file organization decision depends on operations involving the table itself and related queries.

#### Example: `Student` Table
- **Query Types**: 
  - Insertions (e.g., adding a new student).
  - Random searches (e.g., finding students in specific courses).
- **Decision**: Use **dynamic hashing** to support frequent insertions and efficient random searches.

---

Let me know if further adjustments or refinements are needed! # Topic 4

# file organization
## simplest case: fixed-length records
### free lists
stores the address of the first **deleted** record.
this address stores the address of the second deleted record, and so on.
it is similar to a linked list.

## variable length records
- used for types such as `varchar`
- used for storage of multiple record types in a file
- record types for repeating fields, such as arrays.

## heap file (aka "pile file")

- with no sorting, new records are inserted at the end of the file
- linear search is used due to no sorting
- typically used when we need to populate a table for the future but we're unsure how it should be used. (later on, this should be tuned).
- if we need to retrieve something from this table often, we should tune t. 

## sequential file (aka "ordered file")
- records are inserted in a search-key order
### tradeoffs
- has slow insertion, because it needs to compute where the record should be placed. additionally, it needs to shift the records down when an insertoin happens.
- search speed, however, is very quick.
### insertion
1. location the position where the record is to be inserted
2. if there is free space, insert there
3. if there is no free space, insert the record in an "overflow block"
4. in either case, pointer chain must be updated

## Factors Considered When Deciding on a File Organization for a Table

Suppose we have these tables:

student(id, name, address)
course(course_id, couresname, location)
enroll(id, course_id)
dept(dept_name, budget)

And suppose we have these queries:
- Insert a new student and associate the student with a (1/day)
- Insert a new course (100/month)
- Find all students who take course number 1, 2, 3 (10/day)
- Insert a department (1/year)
- Find all departments whose budget is between 1 million and 10 million (6/month)

## Tools
## Hashing
- good for random search
### When to use static, when to use dynamic:
- static is good when we dont have a growing file with many insertions, dynamic hashing can accomodate insertion.
remember when answering: "dynamic hashing with hash key <attribute>"
### No searching?
use a heapfile, especially if there are many insertions.
### range search?
if theres a range search, use a B+ tree if there are lots of insertions.
if insertions are seldom, use a index-sequential file on the search key.

### Approach

We'll have a table, tpe of query, the search key, and the query frequency. At the end, we'll have the file organization determined by these.
Additionally, the decision is determined by if the table is used on other queries too.
So, not only the operations on the table itself, but any operations where the table is related to.

#### Student
Type of queries: insertion (q1), random search (q3)
We'll use dynamic hashing since its good for random search and insertion (because the file grows frequently).


...



