#COMP1711
## Structures and ${syntax}$
- Is like a normal [[Data Types]] data type and can be used as such
- define more complex data types
- similar to a class in python or java

## Creating a Structure
```c
struct bankAccount {
	char name[100];
	int accountNumber;
	int branchSortCode;
	float balance;
};
struct studentRecord {
	char name[100];
	int studentIDnumber;
	char department[100];
	char degreeSubject[100];
};
```

## Using The Structure
```c
struct studentRecord {
	char name[100];int studentIDnumber;
	char department[100];
	char degreeSubject[100];
};
	typedef struct studentRecord Student;   /// line can be replcaed with writting Student in the line above, before the semi colon
	Student aStudent;
	aStudent.department = “School of Computing";
```

## Strong Typing
- The normal rules of strong typing in C mean that our ‘type def struct’ data types obey the same rules as primitive data types
- We can define static arrays of structures
- Functions can take structures as parameters and return structure values
- We can define pointers to structures
- We can dynamically allocate structures and arrays of structures.

## Pointers
- [[Pointers]] to structures obey the same rules as primitive datatypes
- We can assign the address of a structure (where it starts in memory) to a pointer variable of the correct type

## Dynamic Memory allocation
If we can declare a pointer to a structure type we can use Standard Library functions malloc/calloc/free to [[Memory Allocation in C|dynamically allocate]] structure data.
```c
Student *pStudents = (Student *)calloc( 5, sizeof(Student) );
```
Through [[Arrays in C|array-pointer duality]] we can now use pStudents as an array of 5 Student structures

## Structures and Functions
Once a structure type is defined it can be used like a primitive type
- We can pass structure values to a function:
```c
void output StudentDetails( Student the Student );
```
- We can return a structure (or pointer to a structure) from a function:
```c
Student *createNewStudent(char name[100], char dept[100], char degree[100] );
```

## Structures Containing Structures
In keeping with the SRP:
- Structures should encapsulate a meaningful unit of data
- and be named accordingly
If necessary we should separate the data into several structures.
We can compose larger structures from other structures

## Self-referential Structures
“Self-referential” means the structure contains a pointer to its own type
- a structure containing an item of its own type would not be possible
- Illegal C:
```c
struct illegal {struct illegal item;}
```
```c
Legal C:struct legal {struct legal *p_item;}
```
This is a useful construction for many data structures including [[Linked Lists]] and trees
#### e.g.
*A binary tree structure*
```c
struct tree_node {
	struct tree_node *link[2];
}
```