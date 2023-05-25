#COMP1212
## Stored program computer
- computer has a fixed set of instructions  
- Instructions can be used and combined constructing arbitrarily complex programs  
	- Games  
	- Scientific calculations  
	- Communication  
- The logic of the program is not embedded in the hardware it is stored in program memory  
- The computer can be programmed and reprogrammed to complete a task

## Von Neumann
- Named after John von Neumann (1945)  
- A description of an abstract machine containing  
	- A CPU (including ALU and registers)  
	- Control unit  
	- Program counter  
	- Memory (data and instruction)  
	- Input/Output devices  
- Any computer where the fetch-instruction and data operations can’t occur  concurrently as they share a common bus  

## Busses
Three types of information  that's usually passed around  the system:  
1. Data  
2. Addresses  
3. Control  
Each one of these pieces of  information is usually implemented by wires, called a bus
![[Pasted image 20230308103258.png]]

## Basic CPU Loop
### Fetch
- Put the location of the next instruction in the Memory address input 
- Get the instruction code by reading the contents at that Memory location
### Execute
- The instruction code specifies “what to do”  
	- Which arithmetic or logical instruction to execute  
	- Which memory address to access (for read / write)  
	- If / where to jump  
• Executing the instruction involves:  
accessing registers  
and / or:  
accessing the data memory

## Fetch-Execute Clash
If the Memory is one address space:  
This scheme will not work:  
• one Memory input  
• one Memory output

## Separate Memory Units
Variant of von Neumann Architecture (used by the Hack computer):  
- Two physically separate memory units:  
	- Instruction memory  
	- Data memory  
- Advantage
	- Complication avoided  
- Disadvantage: 
	- Two memory chips instead of one  
	- The size of the two chips is fixed.