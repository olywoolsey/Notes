# Network Layer
- Layer that handles [IP Addresses](IP%20Addresses.md) for hosts and routers
- Most common protocol is the Internet Protocol, or IP
	- .Describes how data is grouped into datagrams (packets).
	- The network addressing scheme.
- A datagram is produced containing the data and header information.
- Also ICMP (Internet Control Message Protocol), which is how routers communicate to ensure efficient transport of messages through the network
- Java only understands IP
## ICMP: Internet Control Message Protocol
- Used by hosts and routers to communicate network level information
- e.g. error reporting
- ICMP messages carried in IP datagrams
- **ICMP Message:** type, code plus first 8 bytes of IP datagram causing error
### traceroute command
Source sends a series of segments to the destination
- First has Time To Live = 1, second has TTL = 2... etc
When $n$th datagram arrives at the $n$th router:
- Router discards it, returns ICMP message type 11 code 0
- When received, sender calculated RTT (Round Trip Time)
- Three times for statistics; '\*'  denotes timeout
**Stopping Criteria:**
- UDP segment eventually arrives at destination host
- Destination returns 'prt unreachable' (ICMMP message type 3) because port doesn't exist
- When source gets this, it stops

