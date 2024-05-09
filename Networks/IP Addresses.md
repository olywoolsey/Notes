# IP Addresses
Every public host on the internet has a unique IP address.
Hosts in private networks (LANs) can use internal addresses (10.\*.\*.\*)
Outward-facing servers, i.e. the public hosts visible to the Wide Area Network (WAN), do have a unique IP address
- They forward messages from LAN hosts to the WAN, and vice versa, using a Network Address Translation (NAT) table
- Does this by (ab-)using port numbers
## Protocols
Two protocols are currently in use:
- IPv4: Internet Protocol version 4.
- IPv6: Internet Protocol version 6.
IPv6 is gradually replacing IPv4, although there is no road map for the end of IPv4 (yet)
### IPv4
- Usually written as a 4-byte string of 4 integers
- a.b.c.d
- Each byte takes a value from 0 to 255 (i.e. unsigned).
- The ‘4’ in IPv4 does not refer to the number of bytes
- There are only (256)4 ≈ 4.29 × 109 possible addresses, i.e. about 4.3 billion
#### Classful Addressing
Originally there were several classes of IPv4 address:
- Class A: 0.*.*.* to 127.*.*.*
- Class B: 128.*.*.* to 191.*.*.*
- Class C: 192.*.*.* to 223.*.*.*
- Class D: 224.*.*.* to 239.*.*.*
- Class E: 240.*.*.* to 255.*.*.*
where the ‘\*’ means ‘any value.’
They vary in size: Class A > Class B > Class C > Class D, E

### IPv6
![](Pasted%20image%2020240509164022.png)