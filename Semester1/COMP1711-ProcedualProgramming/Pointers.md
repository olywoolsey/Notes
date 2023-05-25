#COMP1711
- Pointers give us access to heap memory addresses
- The standard library tools allow us to allocate and use heap memory
- This dynamic memory is allocated at run-time
- Not pre-allocated on the stack by the compiler
- have to define pointer type to know memory address size
```c
float *p;
```
- ->
	- is a pointer to a float variable
	- stores address of a floating point value

## Array Pointer Duality
- The properties of arrays and pointers are closely linked in C
-  Pointers are the link between:
	- statically (compiler) allocated memory on the stack (can't change)
	- dynamic (runtime) allocated memory on the heap (can change)
	- On the stack an array can be used like a pointer
	- On the heap a pointer can be used like an array
