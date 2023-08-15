#COMP1711 #semester-1
## Key Principles
- Define [[Variables in C|Variables]] with meaningful names
- Define [[Data Types]] with meaningful names, which allows us to define new data types that encapsulate problem-specific information
- Define [[Semester1/COMP1711-ProcedualProgramming/Functions]] with meaningful names, that encapsulate the specific behaviour
- Name source code meaningfully
- compiled file should have similar name
- can split source code into different files
	- group functions based on purpose
	- will still compile to a single executable
> [!reminder]
> will be assessed on layout and readability of program

## Top Down Design
- Decomposition
	- problem can be split onto logical parts
	- can be implemented into a set of functions in one source code file
- Is essentially object oriented design <u>not OOP</u>

## Header Files
- contain function prototypes
- similar to <stdio.h>
- can define own header files and is how you import other source code files
- Good Practice:
	- the header file contains function prototypes
	- if we define a c source code then the .h files should have the same name
	- therefore we have pairs of files: file_name.c and file_name.h
	- \#include is a way of linking files
- the main source code file should include all header files at the top for it to compile
- header files can contain other header files

## Dependencies
[[Compilation]] requires knowledge of dependencies between files
- Dependencies relate to source code files
- Where functions are used that are not implemented in that file
- the compiler can infer dependencies from \#include statements
