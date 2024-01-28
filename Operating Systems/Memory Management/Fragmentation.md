# Fragmentation
#COMP2211 
##  Types
- **External Fragmentation** - total memory space exists to satisfy a request, but it is not contiguous
- **Internal Fragmentation** - As allocated memory is split into [Frames](Frames.md), it may be slightly larger than requested memory; this size difference is memory internal to a partition, but not being used
- First fit analysis reveals that given N blocks allocated, 0.5 N blocks lost to fragmentation
- Fragmentation problems mean quite a lot of memory is “wasted”
## Compaction 
- Used to reduce Fragmentation
- Shuffle memory contents to place all free memory together in one large block
- Compaction is possible but potentially computationally expensive to manage and needs to be carefully analysed as to whether it is an appropriate use of system resource
