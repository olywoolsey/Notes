#COMP1211 
- the smallest [[Semester1/COMP1211-ComputerArchitecture/Memory]] type
- are very quick because of the size
![[Pasted image 20221020133910.png]]

## General Purpose Registers
- may be used for data or addressing
- normally between 8 - 32
- often possible to use 2 registers to store 1 word / address
## Program Counter
- Program Counter (PC) is used to keep the track of execution of the program
- It contains the memory address of the next instruction to be fetched
- PC points to the address of the next instruction to be fetched from the main memory when the previous instruction has been successfully completed
- Program Counter (PC) also functions to count the number of instructions
## Instruction Register
- The IR holds the instruction which is just about to be executed
- The instruction from PC is fetched and stored in IR
- As soon as the instruction in placed in IR, the CPU starts executing the instruction and the PC points to the next instruction to be executed
## Memory Address Register (MAR)
- It holds the address of the location to be accessed from memory
- MAR and MDR (Memory Data Register) together facilitate the communication of the CPU and the main memory
## Memory Data Registers (MDR)
- It contains data to be written into or to be read out from the addressed location
## Accumulator (AC)
- This Register is used for storing the Results those are produced by the System
- When the CPU will generate Some Results after the Processing then all the Results will be Stored into the **AC Register**
## Program status word register
- The PSW is a special register that contains status information
- This typically includes condition codes such as;
	- Zero (when result is zero)
	- Carry
	- Overflow
	- Interrupt enable/disable