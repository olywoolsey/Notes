- Conceptual design:
	The process of constructing a model of the data used in an enterprise, independent of all physical considerations
- Logical design:
	The process of constructing a model of the data used in an enterprise based on a specific data model(e.g. relational), but independent of a particular DBMS and other physical considerations
- Physical design:
	The process of producing a description of the implementation of the database on secondary storage; it describes the base relations, file organisations, and indexes design used to achieve efficient access to the data, and any associated integrity constraints and security measures

## Build conceptual data model
1. Identify entities
2. Identify relationships
3. Identify & associate attributes with entities/relationships
4. Determine attribute domains
5. Determine candidate, primary & alternate keys
6. (optional) use enhanced modelling
7. Check for redundancy
8. Validate model against user transactions
9. Review data model with user

## Logical Database Design
1. Derive relations
	- i.e. 1:1 many:1, superclass:subclass
2. Validate relations using normalisation
3. Validate realtions against user transactions
4. Define integrity constraints
5. Review logical data model with user
6. Merge logical data models into global model
7. Check for future growth

