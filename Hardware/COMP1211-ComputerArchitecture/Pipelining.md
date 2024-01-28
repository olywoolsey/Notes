# Pipelining
#COMP1211 
##### Do multiple instructions at once - think of manufacturing (don't wait till product is complete before starting next one)
- FI Fetch instruction
- DI Decode instruction
- CO Calculate operands (effective addresses)
- FO Fetch operands
- EI Execute instructions
- WO Write result
- Pipe-lining means overlapping these operations.
![[Images/Pipilining.png]]

## Multiple streams
- Have two pipelines
- [[Instruction Cycle#Prefetch|Prefetch]] each branch into a separate pipeline
- Use appropriate pipeline
- Leads to bus and register contention
- Multiple branches lead to further pipelines being needed 

![[Images/Multiple_Streams.png]]
- In this example, Instruction 3 is a conditional branch to Instruction 15.