#COMP1711
>written C code
>-> ( compiling ( source to object code ))
>Object Code
>-> ( linking (to library's and between different object codes ))
>Executable program

- Multiple C source code files will be compiled into object code separately
- are linked after into one executable

## Compiling Multiple Files
### Simple: 
```
gcc main.c file1.c file2.c –o <executable name>
```
- is okay for smaller programs
- can take a while for bigger programs
- will need to recompile every file again even if a change is made in one file
### Compiling multiple files
```
gcc -c main.c
gcc -c file1.c
gcc -c file2.c
gcc main.o file1.o file2.o -o <exececutable name>
```
- splits compilation into multiple steps
- means you can recompile only 1 file at a time
- Have to recompile dependencies as well 

### Makefiles
https://makefiletutorial.com/
- is a script that manages the compilation of our code
	- We specify the compiler and the required options
	- We specify the structure of our C program and dependencies
	- We specify the final executable name
- type make rather than gcc
- **Many different ways of doing it**
We can write a Makefile in many different ways:
- It is a plain text file containing rules for compilation ( store in plaintext file called Makefile)
- The important feature is that it is largely generic
- We can reuse it for other C applications with minimal changes
- The make process will detect files that have changed,and only recompile files that are required,based on the dependencies

#### Structure of Makefiles
``` txt
//source files
SRC = library.c staff.c user.c      // Define the list of source code files
OBJ = library.o staff.o user.o      // Define the list of object code files
EXE = library                       // Define the executable filename

// compiler options
CC = gcc                            // Define the compiler
CFLAG = -Wall –std=c99              // Define the compiler options
CLIBS =                             // Define any libraries to include
CLINK = -lm                         // Define any libraries to link
```
- We define variables (SRC,OBJ,EXE) in the script for our application
- SRC defines the input for the Makefile• OBJ and EXE define the outputs for the Makefile
- EXE is typically called the target for the Makefile

- We define variables in the script for the compiler
- These rules define the compilation process

#### Build
##### Rule for .c to .o
%.o: %.c
	$(CC) -c $(CFLAGS) $(CLIBS) $< -o $@
###### Build executable from objects
$(EXE): $(OBJ)
	$(CC) $(OBJ) –o $(EXE) $(CLINK)

### Dependancies
- Makefile dependencies define which of our source (.c) and header(.h) files each object (.o) file depends on
- If any of the dependencies change that file must be recompiled
>[!note]
>that changing a header file can then also require re-building several object files
