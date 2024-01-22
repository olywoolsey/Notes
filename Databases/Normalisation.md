# Normalisation
#COMP1121 
## Why?
- Have minimal number of attributes
- attributes with close logical relationship in same relation
- minimal redundancy

## Functional Dependency
- If A and B are Columns of R
- B is functionally dependent on A (denoted A → B), if each value of A in R is associated with exactly one value of B in R (one-to-one relationship)
- i.e. Storing a customers and ID together in a table that also stores sales

## Un-normalised Form
- A database that contains one or more repeating groups
- All data is stored in one table

## $1^{st}$ Normal Form
- A relation in which intersection of each row and column contains one and only one value
- The 1st normal form requires that each column in a table contains only atomic values. Atomic values are indivisible and cannot be further broken down.
- Each attribute (column) in a table should hold only a single value, not a collection or a list of values.
- The order of the rows and columns is insignificant.
- There should be a unique identifier for each row (primary key).
- Duplicate rows are not allowed

## $2^{nd}$ Normal Form
- The 2nd normal form builds on the 1st normal form and adds an additional requirement.
- It states that a table should meet 1NF, and every non-key attribute (column) in the table should be functionally dependent on the entire primary key.
- In simpler terms, if a table has a composite primary key (consisting of multiple attributes), each non-key attribute should depend on the entire composite key, not just a part of it.
- This helps eliminate redundancy and partial dependencies

## $3^{rd}$ Normal Form
- The 3rd normal form builds on the 2nd normal form and further refines the normalisation process.
- It states that a table should meet 2NF, and every non-key attribute (column) in the table should be dependent only on the primary key. In other words, there should be no transitive dependencies.
- Transitive dependencies occur when a non-key attribute depends on another non-key attribute, which itself depends on the primary key.
- To achieve 3NF, these transitive dependencies need to be eliminated by creating separate tables for related attributes

## Boyce–Codd Normal Form (BCNF)
- A relation is in BCNF if and only if every determinant is a candidate key
- Every relation in BCNF is also in 3NF. However, a relation in 3NF is not necessarily in BCNF
