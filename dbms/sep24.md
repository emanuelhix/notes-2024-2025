---

### **Cartesian Product (`*` and `SELECT *`)**

* A Cartesian product generates **every possible pair** of rows from two tables.
* Using `SELECT *` returns **all columns** from the result.
* This operation **does not apply any filtering conditions**; filtering occurs afterward with a `WHERE` clause.
* Because it produces a very large intermediate result set, it is considered **one of the most expensive operations** in a database.
* On its own, it is not very useful—essentially just a display of all combinations. It becomes meaningful when combined with a `WHERE` clause.

---

### **Join Operation**

* Originally, a join was implemented by:

  1. Performing a Cartesian product of two tables.
  2. Applying the join condition using the `WHERE` clause to filter relevant rows.
* Modern DBMSs use more efficient join algorithms (e.g., **hash join**, **merge join**, **nested loop join**) instead of creating a full Cartesian product.
