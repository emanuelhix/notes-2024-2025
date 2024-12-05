# Topic 1

**Poll 1**

c) both (a) and (b)

**Poll 2**

a) True

**Poll 3**

b) False

The query may be slow due to a suboptimal logical or physical design of the database. Typically, the issue lies within the design rather than the Database Management System (DBMS).

_Sometimes_ performance tuning involves upgrading to a more efficient DBMS, but this is not always the case. Therefore, the answer is false.

---

# Topic 2

**Poll 4**

a) One-to-one relationship

**Poll 5**

b) True

The primary key can indeed consist of more attributes than the super key. This occurs because a super key for an entity \( E \) might simply be \( (ID) \), assuming that \( (ID) \) is sufficient to uniquely identify \( E \).

By combining \( ID \) with additional attributes, we can create new keys such as \( (ID, name) \) or \( (ID, GPA) \) for a _Student_ entity. Since these keys include \( ID \), they can still uniquely identify the student.

The _primary key_ is simply the one we select for our implementation. Thus, it’s possible to designate \( (ID, name) \) as our primary identifier, even though it contains more attributes than the super key \( (ID) \).

**Poll 6**

The diagram that requires modification:

![alt text](image.png)

b) Adding a multi-valued attribute to Instructor

A multi-valued attribute is one that can hold multiple values. For example, it would be represented as `{phone_numbers}` within the rectangle for the Instructor entity set. This allows us to store multiple phone numbers for each Instructor entity.

**Poll 7**

a) True

**Poll 8**

b) False

An aggregation is employed when we want to establish a relationship with a relationship set.

---

# Topic 3

**Poll 9**

Skipped !?

**Poll 10**

EMPLOYEE is the relation schema `employee(name, office_number, age)`.

c) (name, office_hours) is the candidate key.

The candidate key is the smallest key possible to uniquely identify an entity.
Name cannot be a key on its own, office_number cannot be a key on its own.

(There is a mistake in the original question, office_hours should be listed as part of the relation schema): `employee(name, office_number, age, office_hours)`

**Poll 11**

**Poll 12**

**Poll 13**

**Poll 14**

**Poll 15**

b) The main data file is sorted on its search-key and the primary index is built on that search key.

**Poll 16**

b) False.

**Poll 17**

**Poll 18**

**Poll 19**
