#COMP1121
## Defs
| Name         | Definition                      |
| ------------ | ------------------------------- |
| Cardinality  | how many rows it has            |
| Relation      | a table, or file                |
| Tuple          | a single row, called a record   |
| Attribute      | a single column, called a field |

## Keys
### Super Key
- a set of attributes that collectively can identify each record in a table
- can be multiple columns that will always have different values
- Relations may have multiple super keys
### Primary Key
- A specific type of super key
- Is based on the minimal attribute set and its stability over time
### Candidate Key
- Is a super key without any extraneous attributes
- Each candidate satisfies the properties of minimality and uniqueness
### Foreign Key
- A set of columns in a table that refer to the primary key of another table
- establishes a relationship between two tables
- Enable the use of joins between tables in query's

## Relations Schema
R = {${A_1}$:${D_1}$ , ${A_2}$ : ${D_2}$ , ${A_3}$ : ${D_3}$ , ${A_4}$ : ${D_4}$}
A = attribute 
D = Domain

## Integrity Constraints
- Entity Integrity
- Referential Integrity
- Multiplicity constraints
- General constraints - constraint applied to particular system

## Views
- Provides powerful and flexible security mechanism by hiding parts of database from certain users
- Permits users to access data in a customised way, so that same data can be seen by different users indifferent ways, at same time
- Can simplify complex operations on base relations
- A virtual relation that does not necessarily actually exist in the database but is produced upon request, at time of request
- Dynamic result of one or more relational operations operating on base relations to produce another relation