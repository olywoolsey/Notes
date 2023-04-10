## The Procedural Paradigm
- Procedures (or functions) change the state of values of data
	- they operate on program data
- functions all us to define the sub-sequences of instructions units of our program
- they are re-usable

## Single-Responsibility Principle
- Every function should have only one purpose and encapsulate that part
- each function should have an obvious and simple purpose (can it be described in a small sentence)
- should have a simple name
- makes testing easier as it only does one thing

## Functions in C
- All executable code must be in a function
- all programs must have at least one function - main()
- java uses classes as the basic unit of code and python can be written in only statements

## Defining a function
- the name
	eg: main
- the [[Arguments]]
	eg: argc, argv
- the [[Data Types|return-type]]
	eg: [[int]]
- this definition is known as the header

## Scope
- defined as { . }
- Scope means that data values defined within brackets {.} are localised
- comes after the header

## Returning Values
- as the variables are limited to the function values aren't automatically returned
- need to use a return statement to pass back the value to the calling statement
- we can only return one value
- need to use pointers to change more than one variable ([[Arguments]])

## main()
- The entry point to our executable program
- Invoked (called) by the operating system to start execution
```c
int main ( void )
// or...
int main( int argc, char *argv[] )
```

## Library Functions
- like <[[Stdio.h]]> they are imported and tell the compiler the headers of external functions (what the .h means)

## Library's in Linux
- The standard libraries are stored in common locations:
	- Headers (definitions) are stored in /usr/include/
	- Compiled implementations are stored in /usr/lib/ and /usr/lib64
- When we use stdio we include the header file <stdio.h>
	- This contains definitions for all the I/O functions
	- The .h extension denotes a header file
- The compiler checks the definition in the header file against our use of the function

## Own Functions
#### Defining the Function
```c
int factorial( int n ) {
	int i;
	int f = 1; // initialise f
	for( i=2; i<=n; ++i ) {
	f = f*i; // accumulate f}return f; // return the result
}
```

#### Using the Function
```c
#include <stdio.h>
int factorial( int n ); // header definition
// main function
int main( void ) {
	int k = 6;
	int f;
	f = factorial( k ); // using the function
	printf( “ fact(%i)=%i\n”, k,f );
	return 0;
}
```

## Recursion
- Recursion is a method of solving a problem by using smaller versions of the same problem
- is a function that calls itself
- can normally implement the problem without recursion however recursion is often more ${elegant}$
- have to ensure recursive functions can terminate (not infinite)
