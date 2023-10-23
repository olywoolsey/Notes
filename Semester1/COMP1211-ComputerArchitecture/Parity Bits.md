#COMP1211 
- type of error detection
- goes with binary at the end 
- can detect errors but can't correct it

Given a set of bits, the value of the corresponding parity bit is chosen so that when it is added to this set the total number of 1s is even
	( It could be chosen so that the total number of 1s is odd(as long as this is checked consistently))
 - This provides a simple way of detecting errors.
	 - If one bit of the original set is changed (0 ↔ 1) then so does the parity bit.
	 - It assumes that there is at most one error


e.g. for 1011 1010 0110 0111
	 the parity bit would be 0