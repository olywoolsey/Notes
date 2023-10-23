#COMP1211 
Normal [[Semester1/COMP1211-ComputerArchitecture/Memory]] is so slow
- bigger memory is slower
- can take 400 clock cycles to retrieve an item from memory
- cache memory is a lot faster
## Terminology
- An memory access is said to hit at a cache if the block is found at a cache line
- Access time of a hit is the hit time
- The additional time (much slower) to fetch a block on a miss is called the miss penalty
- Miss rate = no.misses / no.accesses

## Memory blocks and Cache Lines
![[Pasted image 20221117133820.png]]
- Block: the unit of data transfer. We break main memory into blocks. Each block holds m bytes (typically, 64 bytes)
- Line: We break the cache into multiple lines, each cache line holds exactly a memory block.

## Average Memory Access Time ( AMAT )
- AMAT = Hit Time + (Miss Rate * Miss Penalty)
- Improving AMAT:
	- Keep miss rate low
		- Increase cache size lowers cache miss rate, but this increases hit time
		- Better cache management policies
			- Pre-fetching: anticipate what you will need
			- Replacement: anticipate what you don’t need
	- Keep miss penalty Low
		- Reduce miss penalty with a faster main memory (but higher cost)
		- Better solved by adding intermediate levels

## Cache Hierarchies
- Trade off between access time and hit rate
	- L1 can focus on fast access (hit time)
	- L2 can focus on good hit rate
![[Pasted image 20221117135014.png]]

## Direct-Mapped Cache
- each memory block is assigned to a specific line in the cache
- More than 1 line can be mapped to the same cache line
- makes block placement, lookup and replacement easy
![[Pasted image 20221118122534.png]]

## Cache Mapping Function
### Mod
- If the cache has $2^k$ lines then the data at memory line i would go to cache line i mod $2^k$
![[Pasted image 20221118123216.png]]
### Least sig bit
- With our 4-byte cache. we would inspect the two least significant bits of our memory addresses
- Taking the least k bits of a binary value is the same as computing that value mod 2<sup>k</sup>
![[Pasted image 20221118123238.png]]

## Finding whats in cache
- tags supply the rest of the address bits to let us distinguish between different memory locations that map to the same cache line
- this means you know what line is stored in cache
![[Pasted image 20221118123926.png]]
- Concatenating the tags with the cache line index to calculate the block addresses

## The Valid Bit
- Initially the cache is empty and doesn't store any data
- when system is init all valid bits are set to 0
- when data is loaded then corresponding bit is set to 1
![[Pasted image 20221118124128.png]]

## Cache Hit
- When the CPU tries to read from memory, the address will be sent to a cache controller
![[Pasted image 20221118124732.png]]
