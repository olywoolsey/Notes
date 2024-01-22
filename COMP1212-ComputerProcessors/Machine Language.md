#COMP1212
A machine language is an agreed upon formalism, designed to code low level programs as a series of machine instruction
- low level operations
	- manipulating memory
	- basic logic operations
- An instruction is a binary sequence of some specified length (16 bits)
![[Images/Pasted image 20230307091930.png]]
`Such an operation might sum operand 1 to operand 2 storing the result in operand 0

## Memory
- a collection of hardware implementations that store data and instructions
- can be seen as a continuous array of words of a fixed width (16-bit)
- each location has an unique address

## Processor
- device capable of performing a set of basic boolean functions
	- arithmetic/logic operations
	- memory address
	- flow control (branching)
		- if statements
		- loops
		- functions

## Registers
- "special" locations within a processor
- memory access is slow so the registers are located closer to the CPU so that it is faster
- machine instructions, unless multiple words are used can't reference the entire memory address space
- all computation is done on registers rather than RAM
- few registers as few as 4 but modern processors may have many kilobytes

## Machine Language
The operation code (opcode) corresponds to operations defined in the decoder circuitry  
- Opcodes are often given mnemonics such as ADD or AND  
- Operands are values stored in registers  
- Registers have mnemonics such as R1, R2...  
- The instruction from before might then look like  Machine Language  ADD R2,R1,R0
	- looks friendlier than 0101 1100 1010 1100

## Assembly
- Programs can be defined as lists of mnemonics  
- A mnemonic is read & translated into the underlying binary sequence that represents a machine instruction  
- some mnemonics might be sequences of machine instructions#
- assembly is translated into machine language by an assembler
#### Assembly Commands
- Arithmetic and Logic operations
	- addition, subtraction, boolean, bit-wise operations
	- at least one opcode for each ALU functions
		ADD R2, R1, R0  // R2 = R1 + R0
		ADD R2, R1, foo  // R2 = R1 + foo
		AND R1, R2, R0  // R1 == bit-wise R2 and R0
- Memory access
	- direct addressing
	- immediate addressing
	- indirect addressing
		LOAD  R1, 67  // R1 = Memory[67]       (Direct)
		LOADI R1, 67  // R1 = 67                      (Immediate)
- Indirect addressing
	- method of implementing pointers
	- loads the value of the memory address referenced by the value of another register
		LOADI R1, 101  // R1 = 101
		LOAD* R0, R1   // R0 = Memory[R1]

### Hack Machine Language
- Hack is a 16 -bit von Neumann architecture
	- a 16-bit CPU
	- two 32K 16-bit memory modules (instruction memory, data memory)
	- two memory mapped Input/Output
		- keyboard
		- screen
#### Hack Registers
- Hack has two 16-bit registers called **D** and **A**
- register D is exclusively used to store data
- register A can be used as a data register or an address register
- there is an implicit label called M which refers to the value of memory location pointed to by register A
- jump instruction use register A to specify the destination to jump to 
- to load an immediate value into register A the following notation is used: @value // load value into register A

#### A-instruction
- A-instructions manipulate register A  
A-instructions  
@37  
is equivalent to:  
0 000000000100101
- A-instructions are identified by their leading ‘0’  
- The following 15-bits are a binary value  
- The @ symbol can be preceded by a symbol referencing a number
- A-instructions have different purposes  
	- To load a constant into the computer under program control  
	- To set up for a subsequent C-instruction designed to manipulate a certain memory location by first setting the A register to the address of the location  
	- To set up for a subsequent C-instruction design to specify a jump by first loading the destination address into register A then executing an instruction which may result in a jump

#### C-instructions
- C-instruction execute some computation operation
- what to compute, where to store the result and to what to do next
- format is
	dest = comp; jump
- if either the destination or jump field are empty then they might be omitted
	- M=D+M           add value in D register to M memory address and store in M
	- D;JGT              jump if greater than D
	- 0;JMP              jump to 0
- C-instructions are encoded as follows:
![[Images/Pasted image 20230307094043.png]]
- C-instructions start with a ‘1’, the next two bits aren’t used, the following three fields  correspond to the three parts in the symbolic representation
##### Computation
![[Images/Pasted image 20230307094219.png]]
- if a is 0 do operation of left
- if a is 1 do operation on right
##### Destination
- The value computed by a C-instruction can be saved in a number of places (destinations)  
- Stored in D, A or M  
- The three bits of the destination part of the C-instruction indicate what to do with the result
![[Images/Pasted image 20230307094551.png]]
##### Jump
- the jump field instructs the computer which instruction to execute next  
- Defaults to executing the next instruction, can be made to fetch and execute any instruction from program memory  
- The criteria for a jump is specified by the three jump bits in the instruction and the result of the last computation
![[Images/Pasted image 20230307094636.png]]
###### Examples:
- D - 1: 1 1 1 0 0 0 1 1 1 0 d1 d2 d3 j1 j2 j3
- D+A: 1 1 1 0 0 0 0 0 1 0 d1 d2 d3 j1 j2 j3
- compute constant 0: 1 1 1 0 1 0 1 0 1 0 d1 d2 d3 j1 j2 j3

### File Specifications
- Machine language programs by convention have the file extension .hack  
- Each line contains either an A-instruction or a C-instruction  
- Contract states that line n of a .hack file will be loaded into program memory address n
