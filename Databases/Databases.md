# Databases
#COMP1121
Book: Database Systems: A Practical Approach to Design,Implementation, and Management by Thomas Connollyand Carolyn Begg
## File Based Approach
### Limitations
- Separation of Data
	- each program maintains its own data set
	- users of one programs may be unaware of data held by another program
- Duplication of data
	- same data held by different programs
	- wasted space and potentially different values / formats for the same item
- Data Dependence
	- file structure is defined in program code
- Incompatible file formats
	- Programs are written in different languages, and so cannot easily access each other’s files
- Fixed queries/proliferation of application programs
	- Programs are written to satisfy particular functions
	- Any new requirement needs a new program
	- No provision for concurrent access

## DBMS - Database Management System
- A software system that enables users to define,create, maintain, and control access to the database
- all information of how to access the database files is held in the DBMS
- all programs go through DBMS to access data
- DBMS allows for recovery

## History of Database Systems
- First Gen
	- Hierarchical and network
- Second Gen
	- Relational    - what most people use (best)
- Third Gen
	- Object Relational
	- Object Oriented

## Advantages of DBMS
- Control of data redundancy
- Data Consistency
- More information from same amount of data - can relate items
- Sharing of data
- Improved data integrity - less inconsistency as is stored in the same place
- Improved Security
- Enforcement of standards
- Economy of scale
