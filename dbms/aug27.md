---

### Computer Architecture and Databases

The structure of a database system is influenced by the underlying computer system it operates on. Common types of computer systems include:

- **Centralized**:
  - The original architecture for database systems, typically managed on a single system.
  - This is the architecture we will study in this course.

- **Client-Server**:
  - **Two-Tier Architecture**:
    - **User/Client Application** --- Network ---> **Database System**
    - The client directly interacts with the database server over a network.
  - **Three-Tier Architecture**:
    - **User/Client Application** --- Network ---> **Application Server** --- Network ---> **Database System**
    - Adds an intermediate application server between the client and the database system, improving scalability and separation of concerns.

- **Parallel (Multi-Processor)**:
  - Uses multiple processors to handle database operations simultaneously, improving performance.

- **Distributed**:
  - The database is distributed across multiple locations or servers, providing redundancy and potentially improving access speed and reliability.

---

### History of Database Systems

- **Early 1950s to Early 1960s**:
  - **Magnetic Tapes**:
    - Used for data processing, but limited by sequential access only. Random access and memory jumps were not possible.

- **Late 1960s to Early 1970s**:
  - **Hard Disks**:
    - Introduced direct and random access, significantly improving speed and flexibility.
  - **Data Models**:
    - Network and hierarchical data models became widely used, employing tree and graph structures to represent data.

---

### When Not to Use a DBMS

- **Overhead Costs**:
  - **Concurrency Control**: Managing simultaneous access to data.
  - **Data Recovery**: Ensuring data can be recovered after a failure.
  - **Data Integrity**: Maintaining accuracy and consistency of data.

- **High Initial Investment**:
  - Costs associated with hardware and DBMS software.

- **Consider Using Files Instead**:
  - For **time-critical applications** where the overhead of a DBMS might be prohibitive.
  - For **applications with a limited number of users**, where advanced features like concurrency control may not be necessary.

---

## Topic 2: Entity-Relationship Model

### Modeling

A database can be modeled as:

- **Entities**: Objects that exist and are distinguishable from other objects, typically having a unique identifier.
  - **Definition**: An entity is an object with a unique ID.
  
- **Attributes**: Properties or characteristics of an entity.
  - **Definition**: An attribute describes a property of an entity. For example, an entity "Person" might have attributes such as "Name" and "Age."

- **Entity Set**: A collection of entities of the same type, sharing the same attributes.
  - **Example**: An entity set "Instructors" might include entities such as instructors with attributes like `instructor_id` and `instructor_name`.

- **Relationships**: Associations that link at least two entities together.
  - **Definition**: A relationship is an association between entities. For example, an "Advises" relationship might link students and instructors.

- **Relationship Set**: A collection of relationships among entities from different entity sets.
  - **Definition**: A relationship set is a set of tuples where each tuple represents a relationship between entities from entity sets. 
  - **Example**: If `(44553, 22222)` represents an "Advises" relationship, where `44553` is an `instructor_id` and `22222` is a `student_id`, then this pair is part of the "Advises" relationship set.

---