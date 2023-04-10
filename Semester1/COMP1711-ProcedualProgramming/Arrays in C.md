 #-1711 #semester-1 
 ordered list of data
- strongly typed
- allow us to collect data together and store with the same name
- has static memory
- size is fixed once designed
- array[0], array[1], array[2].... can be treated as adjacent memory
## 1-Dimensional array
- C also uses 1-d arrays to store [[Strings]]
###### Syntax:
```c
int vec[5];
The components are { vec[0], vec[1], vec[2], vec[3], vec[4] } which are each int
	c uses square brackets for array components
	indexing starts from 0
```
### Initialising arrays
###### For loops
```c
	int vec[5];
	int k;
	for( k=0; k<5; ++k ) {
	 vec[k] = 2-k;
	}
```
###### Inline
```c
int array[5] = {2 , 1 , 0 , -1 , -2};
```

## Multidimensional array (matrix)
- mat\[5\]\[5\] is a 2-d array or a matrix in maths
  - has 25 elements
- this can be extended to as many dimensions as needed
- however memory is required and the standard limit is 255
- each matrix is stored row by row

### Defining a matrix
```c
int mat[5][5];
int k, j;
for( k=0; k<5; ++k ) {                // outer loop
	for( j=0; j<5; ++j ) {               // inner loop
		- [ ] mat[k]j] = 6-k-j;
	}                                             // inner loop end
}                                                 // outer loop end
```
![[Pointers#Array Pointer Duality#]]

