#COMP1212
- Optimising some Criteria
	- no. transistors
	- no. of different type gates
	- depth of logic circuit
	- fan in/out

## Why?
- limit to transistor density
- cost implication for each transistor and gate
- propagation time through logic gates
	- greater depth = longer time
- Conceptual simplicity for bug finding
- simple design is less likely to go wrong

## Algebraic Manipulation
- Logical equivalences reduce number of variables
### Karnaugh Maps
- alternative representation to a truth table
- 1952 by Maurice Karnaugh
- ideal for identifying redundant variables in a logic expression
- ideal for up to 6 variables
- have 0 and 1 entries
![[Pasted image 20230214092657.png]]

#### More Variables
- 3 Variables will contain 8 values
![[Pasted image 20230214093140.png]]
- notice the order of the values:
	- they are not binary order 
	- each adjacent value must only differ by one bit therefore
	- if counted in binary 01 and 10 would be adjacent so the table wouldn't work
## Reading a Karnaugh map
1. for each row and column find pairs of matching ones
	note: the tables can wrap around the side
2. for each box in the pair, 'and' all of the variables that have made that value
3. put the two boxes together then reduce it to get rid of values that negate or are duplicate
4. 'Or' with every other pair of ones in the table 