#COMP1211  
- [[Von Neumann]] architecture is used to store all data and code in current machines
## Program
- A program is a sequence of instructions
- For each instruction, an arithmetic or logical operation is performed on some data
- Each distinct operation requires a different set of control signals.
- it uses the [[Fetch, execute cycle]]
- ---
- For each operation a unique code is provided (opcode)e.g. ADD, MOVE
- A hardware segment accepts the code, interprets it, and issues the corresponding control signal
- **This constitutes a computer.**
---
## Components
- [Central Processing Unit](Central%20Processing%20Unit.md)
- [Input and Output](../COMP1711-ProcedualProgramming/Input%20and%20Output.md)
- [Memory](Memory.md)
![[Images/Components.png]]

## Instruction Cycle
![[Images/Instruction_Cycle.png]]

## Data Flow
### Instruction Fetch
1. PC contains address of next instruction
2. Address is moved to MAR
3. Address place on address bus
4. Control unit requests memory read
5. Result place on data bus, copied to MBR, then to IR
6. Meanwhile PC is incremented by 1
![[Images/Instruction_Fetch.png]]

### Data Fetch
- The IR is examined
- If indirect addressing is used, an indirect cycle is performed
	- Right most N bits of MBR transferred to MAR
	- Control unit requests memory read
	- Result (address of operand) moved to MBR
- With indirect addressing, the operand of an instruction contains a short memory address of a location which itself contains the full memory address of the operand(allowing shorted instructions)
- Indirect addressing requires more memory access per instruction
- Can be though of as an additional instruction subcycle

## Pipelining and Prefetching
- allows the CPU to perform multiple tasks at once, less waiting for other processes to complete
- can be used to improve performance
### Prefetch
- A fetch accesses main memory
- An execution usually does not access main memory
- Therefore we can fetch the next instruction at the same time as executing the current instruction
- This is called instruction prefetch
### [[Pipelining]]
- overlaps all operations not just the fetch