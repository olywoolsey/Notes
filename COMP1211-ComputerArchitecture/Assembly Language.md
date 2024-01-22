#COMP1211
![[../zImages/Pasted image 20221027132642.png]]
## 3 addresses
Operand 1, operand 2, result
- a := b + c• May be a forth - next instruction (usually implicit)
- Not common approach
- Needs very long words to hold everything.

## 2 addresses:
- One address doubles as an operand and the result
- a := a + b
- Reduces length of instruction
- Requires some extra work
- Temporary storage to hold some results.

## 1 address:
- Implicit second address
- Usually a register (accumulator)
- Common on early machines

## 0 addresses:
- All addresses implicit
- Uses a stack
- Example
	- push a
	- push b
	- add
	- pop c

