# Bit Twiddling
#COMP1921
## 2D Arrays
- Arrays with more than 1 dimension
- malloc() is very slow
	- two context switches and heavy-weight code
	- typically takes at least 1,000 cycles
- In C pointers are the same as arrays
- has to support two types
- a matrix
	- rectangular array
	- what we often use
- an array of pointers
	- in C it is the same
can optimise if arrays are fixed width
## allocating 2D array row by row
- allocated each row seperatly
- cost is 1 malloc() per row, plus 1 extra
- Total: nRows+1
## As a single Block
- we only need two mallloc() calls total
- and we guaranteed the data is all together
- not true the other way

## Bit-Twiddling
- Colloquial for changing bits
- << shifts bits to the left in Big End notation
- x<<2 means shifts bits left by 2 bits, new bits are 0
- more efficient than multiplication
- >> shifts right
- new bits are 0 if number is unsigned
- otherwise often the sign bit
- always so with unsigned 

## Bit Masks
- bit mask is like a stencil
- can be used for retrieving bits
- use bitwise & and | operators
- using the and operator use a bitmask, 0 will ignore the bit and a 1 will keep the bit

- set to 1 with OR
- clear single bit to 0 with AND
- Toggle single bit with XOR

prinf doesn't print in binary

## Evil Swap Macro
- Dangerous forbidden technique
- but is fasted solution known
- take x and Xor with y then take y and XOR with x

## big end vs little end
- Intel chips write Little and First
- 03 00 00 00 in memory
- 0x00 00 00 03 when printed out in big endian
- and pointers are always messy
- the net uses big endian

## Swapping Short
- we want to extract the first and second bytes