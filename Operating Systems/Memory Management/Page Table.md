# Page Tables
#COMP2211 
## Implementing a Page table
- Page table is kept in main memory
- Page-table base register (PTBR) points to the page table
- Page-table length register (PTLR) indicates size of the page table (like an offset)
- In this scheme every data/instruction access requires two memory accesses
- One for the page table and one for the data / instruction
- Interesting point:
	- The two memory access problem can be solved by the use of a special fast-lookup hardware cache called associative memory or translation look-aside buffers(TLBs)
## Page Table Structure
- Don’t want to allocate that contiguously in main memory
- OS developers have therefore created a few techniques to make this a bit more manageable
### Hierarchical (Multi-Level) Page Tables
- Layered Approach: Hierarchical [paging](Paging.md) divides the page table into multiple levels,reducing memory overhead
- Efficiency for Large Address Spaces:Particularly useful for systems with large address spaces, as it avoids the need for a single, large page table
- Multi-Level Page Tables: Typically involves two or more levels (e.g., two-level paging,three-level paging)
- Reduced Memory Usage: Only the needed parts of the page table are in memory,reducing the total memory footprint
### Hashed Page Tables
- Hashing Mechanism: Uses a hash table to store page table entries, enabling faster access.
- Handling Large Address Spaces: Ideal for handling large address spaces in 64-bit architectures.
- Collision Resolution: Handles collisions using techniques like linked lists.
- Efficient Search Time: Offers efficient search time for page numbers,especially in sparse address spaces
### Inverted Page Tables
- Single Entry Per Frame: Contains one entry for each frame of physical memory, unlike traditional page tables.
- Reduced Memory Size: Significantly reduces the size of the page table for large memory systems.
- Page Number as Key: Uses the page number as a key into the table to find the corresponding frame.
- Supports Large Physical Memory: Particularly efficient for systems with large physical memory.