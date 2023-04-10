#-1711 #semester-1 
## Why
- faster - direct as don' t need to translate
- more compact - as bits rather than (multiple) bytes per item

## Binary Data Values
- is add 0b to front of binary string then can store numbers in the binary format
- isn't explicit but is very common

## Bit-wise Operations
- has to be done on the binary representations
- Different to [[Operators in C#Logical|Logical Operators]]

| Symbol | Operator   |
| ------ | ---------- |
| &      | AND        |
| \|     | OR         |
| ^      | XOR        |
| ~      | NOT        |
| <<     | LeftShift  |
| >>     | RightShift |

## Bitwise Applications
- Embedded Systems
	- Common in embedded systems programming where we have limited memory
	- e.g. Arduino and similar devices
	- Specific bits are associated with pins on the device
- Machine Learning Systems
	- One-hot encoding uses binary representation for categories
	- Where we can only fit one of many categories

## Binary Read/write
- is only really good for numerical data
- very useful in c as most important data is numerical

## Binary Read
```c
int fread( void *storage, int elementSize,int numElements, FILE *fp );
```

## Binary Write
```c
int fwrite( void *storage, int elementSize,int numElements, FILE *fp );
```

## For Both
#### Inputs:
- storage:  Memory address for the data to be stored 
- element Size:  The size in bytes of 1 item 
- numElements: The number of items
- fp: The file pointer (source)
#### Returns:
- int: The number of items read