#COMP1211 
## Little-Endian vs Big-Endian
- **What order do we read numbers that occupy more than one [[Binary|byte]]?**
	- Consider 12345678 to be a hexadecimal representation of a 32-bit binary number.
| Address | Value(1) | Value(2) |
| ------- | -------- | -------- |
| 184     | 12       | 78       |
| 185     | 34       | 56       |
| 186     | 56       | 34       |
| 187     | 78       | 1        |

- The problem is called Endian
- The system on the left stores the most significant byte in the lowest numerical address
- This is called big-endian
- The system on the right stores the least significant byte in the lowest numerical address
- This is called little-endian
### Standards
- Pentium (80x86), VAX are little-endian
- IBM 370, Motorola 680x0 (Mac), and most RISC are big-endian
- The internet is big-endian
- Make writing internet programs on PC more awkward!
- WinSock provides htoi and itoh (Host to internet and internet to host functions to convert)
- 