## Config Gates with Nand
### Not
![[Pasted image 20230208101202.png]]
### And
![[Pasted image 20230208101221.png]]
### Or
- uses De Morgans Law
![[Pasted image 20230208101242.png]]

## Multiplexor (MUX)
- 3 input gate
- 1 input is a selection bit
- One of the other two inputs, a and b, are outputted depending on the value of the selection bit
![[Pasted image 20230208102950.png]]

## Demultiplexor
- opposite function to a MUX
- 2 inputs (in and a selection bit)
- 2 outputs a and b
- Outputs in on either a or b depending on the value of the selection bit
![[Pasted image 20230208103330.png]]

## Multi Bit Gates
- computer hardware use buses of a specified width
- n-bit variety of most of the logic gates
- n-bit Or
- n-bit And
- n-bit Not
- n-bit Mux

## Multi Way Gates
Many logic gates which have 2 inputs generalise to having n bits
n-way Or
n-way And
n-way Xor
n-way Mux

## Multi-way/Multi-bit Multiplexor
- Multi-way multiplexor can be constructed out of multiplexor
![[Pasted image 20230208105042.png]]

## Look Up Tables
An alternative to combinatorial logic
Essentially a large memory chip
Inputs are used as address lines
Output is the value stored in a specific memory location
Alternatively can be implemented using multiplexors, with hardwire values