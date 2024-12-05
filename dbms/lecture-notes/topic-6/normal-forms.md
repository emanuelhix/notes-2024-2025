# Normalization

### Definition

Normalization is the process of ensuring data integrity in a table by eliminating redundant information.

Each normal form corresponds to specific "safety requirements" or sets of criteria, with 1NF being less stringent compared to higher forms like 3NF or 5NF.

### Benefits

- Tables are smaller, more atomic, and easier to understand.
- Tables are simpler to modify.
- Tables are safeguarded against insertion, deletion, and update anomalies.

## Normal Forms

### First Normal Form (1NF)

#### Violations
1. **Row Order Dependency**: Rows should not convey information. Use explicit data and `ORDER BY` if needed.
2. **Mixed Datatypes**: Columns must contain a single datatype.
3. **No Primary Key**: Every table must have a primary key.
4. **Repeating Groups**: Avoid storing multiple values in one row. Use separate columns for item type and quantity.

### Second Normal Form (2NF)

#### Definition
Non-key attributes must depend on the entire primary key.

#### Violations
1. **Anomalies**: Update, deletion, or insertion anomalies occur when:
   - `{A, B1} -> {C}`
   - `{A, B2} -> {C}`
   - Desired functional dependency is `{A} -> {C}`, but cannot enforce it due to the composite key.
   
   **Solution**: Split the table to create a new table with `{A} -> {C}` and remove this dependency from the original table.

### Third Normal Form (3NF)

#### Violations
1. **Transitive Dependencies**: Non-key attributes depend on other non-key attributes:
   - `{A} -> {B}` (primary key to attribute)
   - `{B} -> {C}` (attribute to attribute)
   - Creates a transitive dependency `{A} -> {B} -> {C}`.

   **Rule**: Non-key attributes should depend only on the primary key, not other non-key attributes.

This form still allows a composite key {A,B} to relate to {C} with only {B}.

### Boyce-Codd Normal Form (BCNF)
#### Definition

With the exception of trivial functional dependencies, every functional dependency in a table must be a dependency on a candidate key, or on a superset of a candidate key (a super key).
A trivial function dependency is one where {A}->{A}, or {A,B}->A or {A,B}->{B}. That is, some attribute is dependent on itself or partially dependent on itself.
An attribute is dependent on the super set of its candidate key because if {A}->{C}, then {A,B}->{C} as well. 

#### Violations
1. A non-primary attribute depends on part of a candidate primary key.

For all of these tables, **ALL** functional dependencies must satisfy the form.

**Solution**: Remove the semantic connection from the attribute that is dependent on the key, that products the data integrity conflict.