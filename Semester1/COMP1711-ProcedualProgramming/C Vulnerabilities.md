#-1711 #semester-1 
- C can behave differently on different platforms
- has close access to system 
- When errors occur they will behave differently in different systems
- standardisation doesn't cover everything

## Undefined Behaviour
- use of initialised values
	- the value will be different at different times
	- will often compile
	e.g. 
```c
int i,j;
j = i + 3
```

- incorrect use of [[Pointers]]
	- out-of-bounds access
		- try to access items in array that haven't been defined
		- it will still find a value but it will not be in the array
		- most compilers won't pick it up
	- use of free
		- free( a ) deallocates a memory location
		- once an item is freed the data stays there until it's overwritten
		- this means it can still be accessed 
		- however it is not certain that it will be the same
	- double-free
		- try to free data that has not been allocated
		- free function doesn't do any checks
		- free function is only well defined for valid inputs
		- free has undefined behaviour for invalid inputs

To find a warning where the code still compiles use gcc -Wall to throw up all warnings

## Type 1 and Type 2 functions

#### Type 1
- Function behaviour is well-defined for all inputs
	- We should always try and write Type 1 functions
	- Particularly if we do not control the inputs

#### Type 2
- Function behaviour is not defined for all inputs
	- We often write Type 2 functions based on assumptions about their use
	- Some library functions have this behaviour
	- We should check inputs before using them in our code
	- often not used as there is a lot of overhead
