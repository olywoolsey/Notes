#Architecture
## 2 Steps
- **Fetch** an instruction from [[Memory]]
- **Execute** that instruction
![[Pasted image 20221020134137.png]]
## Fetch
- The **program counter** (PC) holds the address of the next instruction to fetch
- The processor fetches the instruction from the memory location pointed to by the PC
- The PC is incremented (unless told otherwise)
- The instruction is loaded into the **instruction register** (IR)
- The processor interprets the instruction and, using the **accumulator** (AC), performs the required actions
## Execute
- **Processor <-> memory**: data transfer between the CPU and main memory
- **Processor <-> I/O**: data transfer between the CPU and an I/O module
- **Data processing**: performance of an arithmetic or logical operation on the data
- **Control**: alteration of the sequence of operations,e.g. jump to an out-of-sequence memory location
	- the program is started by providing PC with a memory address
	- contents interpreted as an instruction
		- MSB provides opcode
		- remaining bits give memory address
		- contents interpreted as an operand
## Interrupts
- every cycle the CPU can receive an [[Semester1/COMP1211-ComputerArchitecture/Interrupts|Interrupt]] which will stop the CPU, run the process then the CPU can carry on afterwards
![[Semester1/COMP1211-ComputerArchitecture/Interrupts#Interrupt cycle]]

