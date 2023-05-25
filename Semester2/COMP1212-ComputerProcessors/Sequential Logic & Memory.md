#COMP1212
## Clocks
- In most computers the passage of time is represented by a master clock  
- A clock has two phases tick/tock (or low/high)  
- The frequency of the clock, amongst other things, determine the speed of computation  
- The waveform need not be regular it is the transition that is important

## SR Flip Flop
![[SRFlipFlop.png]]

## D-type Flip Flops (DFF)
- We want a logic circuit such that out(t) = in(t-1) where t is a discrete time interval 
- The output of the gate at time t is dependent on the input of the gate at the previous time step (t-1)
![[dtype.png]]
![[DtypeFlipFlop.png]]

## 1-bit Memory
- D-type Flip Flop can store a single bit, but they have no mechanism to read/write
- Mux allows for the selection of storing either the currently stored value or the value at in  
	- Read - value from out 
	- Write - put bit on in and set load

## Registers
- Collection of bits
- width of register is dependant on architecture
	- ours is 16 bit
- share a common **load** control bit

## RAM
- Random Access Memory (RAM) is a type of memory where access to arbitrary positions is possible at uniform cost  
- Memory locations are numbered from 0 to n often where n is a power of 2
- pointers refer to memory addresses
![[RAM.png]]
- memory addresses are found recursively by zooming in by 3 bits every time
![[MemoryScale.png]]

