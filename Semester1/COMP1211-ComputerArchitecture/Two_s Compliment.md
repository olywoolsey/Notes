#Architecture
- alternative to [[Bias Notation]] in representing [[Binary]] numbers
- unlike [[One's compliment]] it doesn't have two zeros and mathematical operations work on it
	- as long as there's no overflow
- using 4 bits:
| Denary | Two's comp |
| ------ | ---------- |
| +3     | 0011       |
| +2     | 0010       |
| +1     | 0001       |
| 0      | 0000       |
| -1     | 1111       |
| -2     | 1110       |
| -3     | 1101           |
## Benefits
- one representation of 0
- better maths
- negating is fairly easy
## Negating
1. flip all digits
2. add 1 to the least significant bit
	remember - negating 0 will not work
	**always make sure the most significant bit ends up flipped or you've run into an overflow error**
## Conversion Between Lengths
- Pack with MSB
- positive numbers pack with leading zeros
	- +18 =                     0001 0010
	- +18 = 0000 0000 0001 0010
- negative numbers pack with leading ones
	- −18 =                1110 1110
	- −18 = 1111 1111 1110 1110
