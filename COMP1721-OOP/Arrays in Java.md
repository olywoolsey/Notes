# Java Arrays
#COMP1721
## Arrays
- [Arrays in C](../Procedural%20Programming/Arrays%20in%20C.md) have Static (stack) and dynamic (heap)
- Arrays in java are always on the heap
- size can be computed at run time but remains fixed once created
- size as property called length ( for array x, x.length gives size )
```java
int[] x  = new int[10];

System.out.println(x.length);  // prints 10

System.out.println(x[0]);    // prints 0
System.out.println(x[1]);    // prints 0
...
System.out.println(x[9]);     // prints 0
System.out.println(x[10]);    // exception!
```

```java
Clock[] c = new Clock[3];  

System.out.println(c.length); // prints 3  
System.out.println(c[0]); // prints null  
System.out.println(c[1]); // prints null  
System.out.println(c[2]); // prints null  

c[0] = new Clock(7, 30);  
System.out.println(c[0]); // prints 07:30:00  
c[0].tick(); // advances time by 1 sec  
c[1].tick(); // exception
```

- Storage allocated objects & arrays using new but can't release it
- Java uses automatic garbage collection to reclaim memory no longer being referenced by the program

## Multidimensional Array
```java
int[][] x = new int[3][4];  

int[][] y = { { 1, 2, 3, 4 },  
			  { 2, 4, 6, 8 },  
			  { 7, 5, 3, 1 } };
```
- can also iterate over elements

## Lists
- part of Java's collections framework
- represent ordered sequence of values
- more flexible, can shrink and grow after creation
- Items accessed by position, via get() & set() methods
- implemented as classes
- two different implementations in java.util
	- ArrayList
		- Better when access pattern is unpredictable
		- … and we donʼt often need to do insertions or removals within the sequence
	- LinkedList
		- Better when insertions or removals are frequent
		- … and access pattern is usually one of iterating over the entire sequence

### Creating a list
```java
ArrayList<String> lines = new ArrayList<String>();  
LinkedList<String> words = new LinkedList<String>();  
LinkedList<String> words = new LinkedList<>();    // list element type can be ommited on RHS
// better
List<String> lines = new ArrayList<>();  
List<String> words = new LinkedList<>();
```
- List is an interface implemented by the ArrayList and  LinkedList classes
- Working through interfaces helps to decouple our code from implementation choices, making it easier to change  the chosen implementation in future

### Wrapper Classes

## Some List Methods
- as lists are classes you need to use methods to use them

| size | returns number of elements in the list |  |  |  |
| ---- | ---- | ---- | ---- | ---- |
| isEmpty | returns number of elements in the list |  |  |  |
| get | returns element at the given integer index |  |  |  |
| indexOf | returns position of the first occurrence of the specified item, or –1 if item is not present |  |  |  |
| add | adds item to the end of the list, or at the given index |  |  |  |
| remove | removes the item at the given index |  |  |  |
| clear | removes all items |  |  |  |
| toArray | returns an array containing the list items |  |  |  |


