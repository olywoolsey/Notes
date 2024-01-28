# Paging
#COMP2211
- A memory management scheme that eliminates the need for contiguous allocation of physical memory, thereby reducing External [fragmentation](Fragmentation.md)
- Run on the [Memory Management Unit](Memory%20Management%20Unit.md)
## Reason
- Although the logical address space appears contiguous, the equivalent physical address space probably isn’t.
- We want to be able to allocate physical memory wherever we can (the alternative is disk ‘memory’)
- Divide physical memory into fixed sized blocks (called [[Frames]])
- Divide logical memory into blocks of the same size called **pages**
- So, to run a program of size N pages we need to find N free frames (in physical memory) to load the program
- Set up a [page table](Page%20Table.md) to translate the logical to physical addresses
- Will cause internal [fragmentation](Fragmentation.md) as frames could be slightly larger than memory allocated
## How Paging Works
### 1. Logical Address Space:
- In the logical address space of a process, the pages are numbered consecutively. For example, if a process has five pages, they might be numbered Page 0, Page 1, Page 2, Page 3, and Page 4.
### 2. Physical Memory:
- In physical memory, these pages are stored in frames, which are also numbered consecutively. The operating system's memory management system maps the logical pages to physical frames using a page table. So, while the logical pages may be consecutive, their corresponding physical frames may not be.
### 3. Non-Contiguous Allocation:
- The key advantage of paging is that it allows non-contiguous allocation of memory. Each page can be assigned to any available frame in physical memory, and the frames need not be physically adjacent.
### 4. Page Table Mapping:
- The page table keeps track of the mapping between logical pages and physical frames. When a process accesses a logical address, the [Memory Management Unit](Memory%20Management%20Unit.md) (MMU) uses the page table to translate the logical address to the corresponding physical address
## Sharing Pages Between Processes
### Shared Code
- One copy of read-only (re-entrant) code shared among processes (i.e., text editors, compilers, window systems)
- Similar to multiple [threads](Threads.md) sharing the same process space
- Also useful for interprocess communication if sharing of read-write pages is allowed
### Private code and data
- Each process keeps a separate copy of the code and data
- The pages for the private code and data can appear anywhere in the logical address space
## Page Faults
- Page faults occur when a program accesses a page that is not currently in RAM
- When a process needs more memory than is physically available, the operating system may swap some pages in [Page Replacement](Page%20Replacement.md)
- Pages that are not currently needed can be temporarily stored on the disk, and when they are needed again, they can be brought back into RAM
- Will cause performance degradation