# Paging
- Although the logical address space appears contiguous, the equivalent physicaladdress space probably isn’t.
- We want to be able to allocate physical memory wherever we can (the alternative is disk ‘memory’)
- Divide physical memory into fixed sized blocks (called frames)
	- Size is power of 2 (usually between 512 bytes and 16MBytes- in RISC-V usually4KB blocks)
- Divide logical memory into blocks of the same size called pages
- Keep track of all the free frames in physical memory...
- So, to run a program of size N pages we need to find N free frames (in physicalmemory) to load the program
- Set up a page table to translate the logical to physical addresses
## Implementing a Page table
- Page table is kept in main memory
- Page-table base register (PTBR) points to the page table
- Page-table length register (PTLR) indicates size of the page table (like an offset)
- In this scheme every data/instruction access requires two memory accesses
- One for the page table and one for the data / instruction
- Interesting point:
	- The two memory access problem can be solved by the use of a special fast-lookup hardware cache called associative memory or translation look-aside buffers(TLBs)
## Sharing Pages Between Processes
### Shared Code
- One copy of read-only (re-entrant) code shared among processes (i.e., texteditors, compilers, window systems)
- Similar to multiple threads sharing the same process space
- Also useful for interprocess communication if sharing of read-write pages is allowed
### Private code and data
- Each process keeps a separate copy of the code and data
- The pages for the private code and data can appear anywhere in the logicaladdress space
## Page Table Structure
### Hierarchical Paging
- Layered Approach: Hierarchical paging divides the page table into multiple levels,reducing memory overhead.
- Efficiency for Large Address Spaces:Particularly useful for systems with large address spaces, as it avoids the need for a single, large page table.
- Multi-Level Page Tables: Typically involves two or more levels (e.g., two-level paging,three-level paging).
- Reduced Memory Usage: Only the needed parts of the page table are in memory,reducing the total memory footprint
### Hashed Page Tables
### Inverted Page Tables

