#COMP1711
## Memory
#### The Stack
- compiler allocates static data types to the stack during [[Compilation]]
- This includes static arrays (see last lecture)
- This includes any pointer defined in our program
#### The heap
- Because pointers can store a memory address they can “point to”heap memory locations
- This is generally termed dynamic memory and is allocated at run-time when it is requested
- ##### allocating memory on the heap
	- requires <stdlib.h>
	- **malloc**: allocate item of given type
	- **calloc**: allocate an array of given type
	- **free**: release allocate memory

## memory allocation syntax
```c
#include <stdlib.h>
int *kp;
kp = (int *) malloc( sizeof(int) );
kp = (int *) calloc( 24, sizeof(int) );
free( kp );
```
- malloc and calloc allocate a precise number of bytes
- **sizeof**: is a portable way of calculating the correct amount of bytes

## reallocate memory size
	kp = (int *) realloc( kp, 36*sizeof(int) );
- changes it from 24 to 36
- the address stored in kp isnt changed
- if reaccocates to a smaller size, data stored will be lost

## Garbage Collection
- many languages allocate and de-allocate dynamic memory silently
- C requires program to manage memory
- can cause fatal errors if its programmed wrong