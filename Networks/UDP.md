# UDP: User Datagram Protocol
- Best effort: UDP segments may be delivered out-of-order, or lost altogether.
- Connection-less: no handshaking between sender and receiver
- Each UDP segment is handled independently of the others
## Why is there a UDP?
- Connection establishment can add a delay
- Smaller segment header
- No congestion control, so can send as fast as desired
- Often used for streaming applications that are loss tolerant but rate sensitive.
- Can add reliability at the Application layer if needed.
## Usages
- DNS uses UDP (fast; small messages).
- So does SNMP (Simple Network Management Protocol) for similar reasons.
- Also useful for real-time multi-media, often wrapped into the Real-time Transport Protocol
### Header
Prepends an 8-byte header to the message including:
- Destination port number
- Source [Port](Ports.md) number
- Message length
- Checksum (check for data integrity but simply discards corrupted data segments)
![](UDP-segment-structure.png)
> [!note]
> There are no host(IP) addresses in the header for UDP (same as [TCP](TCP.md))
> This is the [Layer - Network](Layer%20-%20Network.md) Responsibility

