# Frames
#COMP2211 
## Definition
- Dividing memory into frames is part of a memory management technique known as [Paging](Paging.md)
- They are physical secions of memory
- Size is power of 2 (usually between 512 bytes and 16 M Bytes- in RISC-V usually 4 KB blocks)
## Why
### Ease of Management:
- Dividing memory into fixed-size frames simplifies memory management for both the operating system and the hardware. The fixed-size frames provide a structured and organised way to allocate and deallocate memory.
### Contiguous Allocation:
- Frames enable a form of contiguous allocation within the framework of non-contiguous memory allocation. While each individual frame is allocated in a contiguous manner, the frames themselves need not be physically contiguous in memory. This helps reduce external [fragmentation](Fragmentation.md).
### Non-Contiguous Allocation:
- Frames allow for non-contiguous allocation of memory for processes. Each process's logical address space is divided into fixed-size pages, and these pages can be scattered throughout physical memory as long as each page is assigned to a valid frame.
### Page-Frame Mapping:
- The division into frames facilitates the mapping of logical pages to physical frames. This mapping is maintained in a data structure called the page table. When a program generates a logical address, the [Memory Management Unit](Memory%20Management%20Unit.md) (MMU) uses the page table to determine the corresponding physical frame, allowing for efficient address translation.
### Efficient Use of Memory:
- Fixed-size frames allow for efficient use of physical memory. Processes can be allocated space in increments of frames, and the operating system can allocate frames to different processes as needed. This flexibility in allocation helps maximise the utilisation of physical memory.
### Memory Protection:
- The use of frames contributes to memory protection mechanisms. By assigning each frame a specific protection level, the operating system can control access to different parts of memory, ensuring the security and integrity of the system.
### Page Replacement:
- In virtual memory systems, where some pages may reside in secondary storage (e.g., on disk), the division into frames makes it easier to implement [page replacement](Page%20Replacement.md) algorithms. When a page needs to be brought into physical memory, the operating system can select a frame to evict a current resident page.
### Hardware Simplicity:
- Frame-based memory management simplifies the design and implementation of memory-related hardware, including the [Memory Management Unit](Memory%20Management%20Unit.md) (MMU) and address translation mechanisms.
