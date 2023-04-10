#Architecture
## What you need
1. Sign
2. Mantissa (magnitude)
3. Sign of exponent
4. Exponent
Exponent is stored in [[Bias Notation]] 
- floating point numbers are normally normalised
	- the exponent is adjusted so that the leading bit (MSB)of mantissa is 1
	- Since it is always 1 there is no need to store it
be careful of [[OverFlow and Underflow]]

## Process
1. convert the decimal number into binary
2. normalise and count how much radix point has moved(exponent)
3. convert exponent into 127-bias then in
4. 

### -1.1101 x 10<sup>1001</sup>  (binary)
- sign = negative = 1
- exponent = 1001 = 9 = 136<sub>127-bias</sub> = 1000 1000<sub>127-bias</sub> 
- mantissa = 1.1101 -> 11010000...
- sign(1-bit), exponent(8-bit), mantissa(the rest)
- 1100 0100 0110 1000 0000 0000 0000 0000