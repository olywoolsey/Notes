# Storage Structure
#COMP2211
- CPU can only load instructions from memory
- Programs must be loaded into memory to run (usually RAM)
- EEPROM is slow and rarely changed but conserves when powers off
- Memory is laid out in arrays of bytes, which have addresses
- CPU interacts with memory by load and store instructions addressing specific bytes or words
- Bytes or words are moved between the CPU [registers](../Hardware/Registers.md) and the memory
- CPU loads instructions from memory automatically, addressed by the program counter
## Von Neumann architecture
- Instruction and data stored on same memory (easier reprogramming)
- [Fetch, execute cycle](../Hardware/COMP1211-ComputerArchitecture/Fetch,%20execute%20cycle.md) happens to either instructions or data as they share the same bus
## Direct Memory Access
- [Interrupt](Interrupts.md) driven memory access only works well for small requests
- Direct Memory Access (DMA) offloads work from CPU
- Allows I/O to access main memory without holding CPU
- Instead of interrupting every few bytes it will access directly and interrupt when whole process is complete
- One interrupt is generated per transfer - to tell the device driver the operation has completed