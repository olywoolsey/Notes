#COMP1211 
## Data Transfer
- Specify
	- Source
	- Destination
	- Amount of data
- May be different instructions for different movements
	- e.g. IBM 370 - STORE (register to memory)
- or one instruction and different addresses
	- e.g. VAX - MOVE

## Arithmetic
- Add, subtract, multiply, divide, ...
- Signed integer - all four always provided
- Floating point - often provided
- May also include• 
	- Increment (integers)
	- Decrement (Integers) 
	- negate (a := −a)

## Logical
- Bit-wise operations
- [[Conjunction|AND]] [[Dis-junction|OR]] [[negation|NOT]]
- Shift
![[Images/Logical_Shift.png]]

## Conversion
- Conversion between different data types
- eg binary to decimal (or [[Binary Coded Decimal(BCD)]])

## [[../Procedural Programming/Input and Output]]
- May be specific instructions
- May be done using data movement instructions
- May be done by a separate controller (DMA, later in course)

## Systems Control
- privileged instructions for operating systems use
- CPU needs to be in specific state

## Transfer Of Control
- Define the next instruction to be executed by changing the address in the program counter
- Branch• e.g. Branch to x if result is zero
- Skip• e.g. increment and skip if zero
- Subroutine call
- c.f. interrupt call
