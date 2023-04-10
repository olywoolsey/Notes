#-1711 #semester-1 
- We pass data from the calling function using the argument_list
	- Each item is strongly typed
	- Can include primitive types, arrays, pointer

## Call-by-value
- The argument list is a copy of the data that is passed to the function
	- The function scope is limited to the body of the function { . }
	- Inside the function these local copies can be modified
	- But this does not change the value in the calling environment 
- This function behaviour is known as call-by-value
	- Data values inside a function are considered as local to that function
	- Consistent with the concept of scope

## Pointers as arguments
- we can pass a pointer to a function as an arguments
- this means we can edit values from other functions without using the return statement
```c
int main( void ) {
	int k = 5; // initialise k
	add_one( &k ); // call the function    & means address of
	printf( “ k=%i \n”, k ); // print k – value?
	return 0;
}

void add_one( int *p ) { // function header     *p is the value stores in &k
	*p = *p + 1; // increase the value
	return;
}
```
#### Side effect
- [[Arrays in C]] pointer duality means that:
	- An array passed to a function is also a pointer (address)
	- We can modify array entries inside a function
	- This also modifies them in the scope of the calling function

