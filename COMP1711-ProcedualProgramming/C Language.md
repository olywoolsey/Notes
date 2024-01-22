#COMP1711 #semester-1 
## Overview
- C is for operating systems
- Procedural - takes input and produces output
- for operating systems
- Windows and UNIX 
- high level as is written in natural language
- low level as can precisely control use and access to memory
- use small memory amount
- **ANSI c** is the standard
- c is a compiled language
- we use GNU compiler collection (gsc) tool
---
- program starts at main, and stops at the end of it
- other conventions may still work but stick to int main(void)
- {} - Braces: define the scope of the function
- indentation not required but helps readability so is convention
	written C code
	->(compiling(source to object code))
	Object Code
	->(linking(to library's))
	Executable program
---
## Memory
- C has two different types of memory
	[[Memory Allocation in C]]
	- [[The Heap in C]]
	- [[The Stack in C]]
---
## Processes
- [[Operators in C]]
- [[For loop in C]]
- [[While loop in C]]
- [[If else in C]]
---
## Data Types
- in C you must define the [[Data Types]] when assigning and don't really change them after
- Changing data type is called casting
	int k;
	k = 4;         ->       int k = 4;
---
## C Library's
- The standard library tools allow us to allocate and use heap memory
- [[Stdio.h]]
