# Storage Structure
#COMP2211
- CPU can only load instructions from memory
- Programs must be loaded into memory to run (usually RAM)
- EEPROM is slow and rarely changed but conserves when powers off
- Memory is layed out in arrays of bytes, which have addresses
- CPU interacts with memory by load and store instructions addressing specific bytes or words
- Bytes or words are moved between the CPU registers and the memory
## Von Neumann architecture
- Instruction and data stored on same memory (easier reprogramming)
- [Fetch, execute cycle](../../Semester1/COMP1211-ComputerArchitecture/Fetch,%20execute%20cycle.md) happens to either instructions or data as they share the same bus
## I/O Structure
- [Interrupt](Interrupts.md) driven memory access only works well for small requests
- Direct Memory Access (DMA) offloads work from CPU
- Allows I/O to access main memory without holding CPU
- One interrupt is generated per transfer - to tell the device driver the operation has completed