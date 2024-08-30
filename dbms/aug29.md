---

## Degree of a Relationship Set

The **degree** of a relationship set refers to the number of entity sets involved in the relationship.

### Binary Relationship
- Involves two entity sets.
- Example: A "teaches" relationship between the entity sets **Instructor** and **Course**.

### Non-Binary Relationship
- Involves more than two entity sets.
- Example: A "student enrolls in course at semester" relationship involving **Student**, **Course**, and **Semester** entity sets.

## Attributes

Attributes provide more information about an entity and can be classified into several types:

### Domain
- **Domain**: The set of permissible values that an attribute can take. It defines the range of acceptable values for that attribute.

### Types of Attributes

#### Simple
- **Simple Attribute**: Composed of a single, indivisible value. 
  - Example: A **StudentID** or **Salary**. These attributes cannot be further divided into smaller meaningful components.

#### Composite
- **Composite Attribute**: Consists of multiple subparts, each representing a more specific aspect of the attribute.
  - Example: **Address** can be divided into **Street**, **City**, **State**, and **ZipCode**. Each of these subparts is meaningful on its own.
---
## Keys

Keys are used to uniquely identify entities in a database. They ensure that each record can be uniquely retrieved.

### Super Key
- **Super Key**: One or more attributes that, when taken collectively, uniquely identify an entity within an entity set.
  - Example: In an **Employee** entity set, attributes such as **EmployeeID** and **Email** together form a super key if their combination uniquely identifies each employee.

### Candidate Key
- **Candidate Key**: A minimal super key; that is, a super key with no redundant attributes. There are no attributes in a candidate key that can be removed without losing the uniqueness property.
  - Example: **EmployeeID** is a candidate key for the **Employee** entity set because it uniquely identifies each employee and cannot be reduced further while retaining its uniqueness.

### Primary Key
- **Primary Key**: A candidate key selected to uniquely identify entities in a table. It is chosen from among the candidate keys and is used as the main reference point for the entity.
  - Example: For the **Employee** entity set, **EmployeeID** might be chosen as the primary key. It must be unique and not null for every record.
  - Additional considerations: 
    - **Uniqueness**: The primary key value must be unique for each record in the entity set.
    - **Non-nullability**: The primary key must always have a value; it cannot be left empty.
    - **Stability**: Ideally, primary key values should not change frequently to maintain referential integrity.

---