# IP Addresses
Every public host on the internet has a unique IP address.
They are converted from human readable names to computer readable addresses using [DNS](DNS.md)
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
- Class A: 0.\*.\*.\* to 127.\*.\*.\*
- Class B: 128.\*.\*.\* to 191.\*.\*.\*
- Class C: 192.\*.\*.\* to 223.\*.\*.\*
- Class D: 224.\*.\*.\* to 239.\*.\*.\*  (Multi-casting)
- Class E: 240.\*.\*.\* to 255.\*.\*.\*   (Future use)
where the ‘\*’ means ‘any value.’
They vary in size: Class A > Class B > Class C > Class D, E
### IPv6
- Uses 16 byte addresses
- Total of $256^{16}$ possible addresses
- Should never run out
- Some legacy systems don't support IPv6
	- Can wrap IPv6 datagrams into IPv4 datagrams if some intermediate routers only support IPv4
	- Know as Tunneling
- Usually written in hexadecimal, with 8 groups (pairs of bytes) separated by colons
- E.G. 2001:0630:0062:0059:0000:0000:0000:0053 or 2001:630:62:59:0:0:0:53 or
- Replace consecutive sections of 0s with double colon, e.g. 2001:630:62:59::53
	- Only can replace one section per address
	- If more than 1 section of 0s, replace largest (or leftmost if equal)
	
![](IPv6-parts.png)

## Temporary Fixes For Not Having Enough Addresses
### CIDR: Classless Inter-Domain Routing
Define subnetworks by any number of bits  
- Greater range of subnetwork sizes (i.e. 256, 512, 1024, . . . )  
- Notation: a.b.c.d/x with x the number of common bits.  
- For example, 220.10.128.0/20 means ‘all addresses that share their first 20 bits with 220.10.128.0’:  
	- All of the first byte (220).  
	- All of the second byte (10).  
	- The most significant 4-bits of the third byte (128-143 inc.):  
	- Full range is:  
		- 220.10.128.0  
		- . . .  
		- 220.10.143.255  
### NAT: Network Address Translation
Private networks to have their own internal addresses, and only public servers to have actual IP addresses
- Re-direct messages to/from private hosts using ports
- 10.\*.\*.\* most common