- Used to define the [[Relational Model]] in terms of algebra
## Components of a Data Model
- Structural - set of rules
- Manipulative - operations allowed on data
- Set of integrity constraints

## Basic Operations
- Join, Intersection and Division can also be represented in terms of these operations
### Selection
- Works on a single relation
- Defines a relation of tuples that satisfy the condition
- i.e. Define all Employees with age > 30
### Projection
- Retrieves attributes from the relation with duplicated items removed
- When producing a list with less attributes than are in the table there may be times where data will be repreated
- this only shows one record instead of repeating it
### Cartesian Product
- R x S
- Defines a relation that is a concatination of every R with every S
- i.e. R = {a, b, c} S = {1, 2} RxS = {a1, a2, b1, b2, c1, c2}
### Union
- R $\cup$ S
- Produces a relation that contains the tuples of both R or S with Duplicates removed 
### Set difference
- R - S
- Defines a relation that contains all tuples that are in R but not in S

## Other Operations
### Intersection
- R $\cap$ S
- A relation that is both R and S
### Joins
#### Theta Join
- R $\bowtie$ S
- Defines a relation that contains tuples satisfying the predicate F from the Cartesian product of Rand S
- If predicate F contains only equality (=), the term Equijoin is used
#### Natural Join
- R $\bowtie$ S
- Equijoin of the two relations R and S over all common attributes x with no duplicate in each common attribute
#### Left Outer Join
- The (left) Outer join is a join in which tuples from R that do not have matching values in the common attributes of S are also included in the result relation
- Missing values in the second relation are set to null
#### Semijoin
- The Semijoin operation defines a relation that contains the tuples of R that participate in the join of R with S satisfying the predicate F.
#### Right (outer) join
- Defines a relation with all tuples from S including those without a matching values in common attributes in R
#### Full outer join
- R ⟗ S
- Defines a relation with a tuples from R and S with matching values in common attributes, and also those in S and R that have not matching values
### Aggregation
- Applies aggregate function to a list
- i.e. SUM, COUNT, MAX...
### Grouping
- Groups tuples by grouping attributes then applies aggregate function to the list
- Resulting relation contains the grouping attributes,GA, along with results of each of the aggregate function