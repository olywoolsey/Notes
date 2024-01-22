#COMP1211 
## Memory Hierarchy
![[Images/Memory_Hierarchy.png]]

#### Memory hierarchy exploits program locality
- Programs tend to reference parts of their address space that are local in time and space
- **Temporal locality:** recently referenced addresses are likely to be referenced again (reuse)
- **Spatial locality:** If a memory address is referenced,nearby addresses are likely to be referenced soon
	- E.g., access to array A[1] is likely to followed by an access to A[2] 

## Cost 
- The design of a computer’s memory is constrained by capacity,transfer rate and cost
- In general:
	- faster access time requires greater cost per bit;
	- greater capacity implies smaller cost per bit;
	- greater capacity implies slower access time
- SRAM ~$10K per GByte
- DRAM ~$10 per GByte
- “Drivers” ~$0.1 per GByte

## Location
- smaller memory is closer to the CPU as its faster
- The CPU has it's own [[Registers]]
- Internal memory (or main memory) resides within the computer.
- External memory consists of peripheral storage devices

## Capacity
- number of bits ( or words ) it can store
- Words length is the natural unit of organisation
- It is usually equal to the number of bits used to represent an integer and to the instruction length.

## Performance
- There are three main performance parameters: 
	- Access time (or latency) is the time between presenting the address and receiving or storing the valid data.
		- Time may be required for the memory to “recover” before the next access
	- Memory cycle time is the access time plus the recovery time.
	- Transfer rate is the rate at which data can be moved
| Memory technology | Capacity   | Access Time           |
| ----------------- | ---------- | --------------------- |
| SRAM              | 512KB      | Sub Nanosecond (nsec) |
| SRAM              | KByte ~ MB | nsec                  |
| DRAM              | GByte      | ~ 50 nsec             |
| SSD               | Tbyte      | millisecond (msec)    |
| HDD               | TByte      | ~10 msec              |

## Unit of Transfer
The unit of transfer is the number of data lines into and out of the memory module
- For internal memory this is usually governed by the data bus width
- For external memory this is often a block much larger than a word.
- The addressable unit is the smallest location which can be uniquely addressed
	- This is often a word, but can be a byte

## Access Method
Sequential access starts at the beginning of the memory and accesses the records in order
- Access time depends on the location of the data and the previous location
- This is highly variable
Direct access moves to a general region of memory then uses sequential access.
- Individual blocks have unique addresses
- Access time still depends on location and previous location
Random access allows any selected memory location to be directly addressed and accessed.
- Unique physical addresses identify locations exactly.
- Access time is independent of location or previous access
Associative access is a form of random access.
- Data is located by a comparison with contents of a portion of the store
- Access time is again independent of location or previous access.

## Physical Type
Common types include:
- semiconductor storage
- magnetic storage
- optical storage

## Physical characteristics
- Information can decay naturally or be lost without electrical power ( volatile )
- Non-erasable memory cannot be altered, e.g. read only memory
- Power consumption influences the cost

## Organisation
refers to its physical arrangement of bits into words
- **this is not obvious**, e.g. they can be interleaved
- a key design issue is the number of bits of data that can be read/written at a time

---
# Memory Errors
Memory is subject to errors
- Those caused by permanent physical defects are known as hard failures
- Soft errors are random events which alter the stored information but cause no permanent damage
Errors can be detected and corrected at the expense of storing additional bits and a little work
	e.g [[Parity Bits]], Hamming codes.

## M-bits
- single error can be detected and corrected using K bits,where K is the smallest integer satisfying
		2K − 1 ≥ M + K
- We assume that K zeros represent no error.

- A typical error-correcting code will store an M-bit word along with a K-bit code, calculated when the word is stored
- The K-bit code is recalculated when the data is read, and compared with the original code, giving one of:
	- no error detected;
	- an error detected which can be (and is) corrected;
	- an error detected (and reported) which can’t be corrected.
![[M-Bits.png]]
---
# Semiconductor Memory
Includes RAM, ROM, and Flash memory ^291502
- Based on memory cells
- two stable states, 1 & 0
- can be written to set state
- can be read to sense state

## RAM
- is read/write memory
- is volatile

### Dynamic RAM
- DRAM
- cells store bits as charge in capacitors
- charge can leak so need to be periodically refreshed ( even when powered )
- simpler and smaller
- provides denser storage and is cheaper
- It is favoured for large memory requirements
- All DRAM requires a refresh operation
	- A refresh circuit is included on the chip
	- It disables the chip while refreshing
	- It loops through the rows, reading and then writing back the contents of each cell
	- The apparent performance is reduced

### Static RAM
- cells store bits with the same on/ off processes as the CPU
- there are no charges to leak so can't leak
- no refreshing  - as long as power is on
- requires less circuitry ( for refreshing )
- faster
- favoured for cache

### ROM
- provides permanent data storage, so cant be changed as is hardwired in
- nonvolatile
- used for very low level data storage