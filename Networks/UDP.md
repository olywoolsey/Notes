# UDP: User Datagram Protocol
- Best effort: UDP segments may be delivered out-of-order, or lost altogether.
- Connection-less: no handshaking between sender and receiver
- Each UDP segment is handled independently of the others
## Why is there a UDP?
- Connection establishment can add a delay
- Smaller segment header
- No congestion control, so can send as fast as desired
- Often used for streaming applications that are loss tolerant but rate sensitive.
- Can add reliability at the Application layer if needed.(e.g. VoIP - Voice over IP; RTP - Real-time Transport Protocol)
## Usages
- DNS uses UDP (fast; small messages).
- So does SNMP (Simple Network Management Protocol) for similar reasons.
- Also useful for real-time multi-media, often wrapped into the Real-time Transport Protocol
	- Sits between Application and Transport Layers
	- UDP packets are numbered such that receiver can determine if packets are missing
	- No correction or re-transmission
	- Receiver can interpolate lost data
#### RTP
- Open standard for real-time conversational applications:  
Runs on-top of UDP (typically) — seen as any other UDP  
packet in the Network layer.  
12-byte RTP header — sequence numbers, time-stamps, etc.  
Better chance of interacting if both end applications use RTP
### One To Many

**SEE LECTURE 15**

### Header
Prepends an 8-byte header to the message including:
- Destination port number
- Source [Port](Ports.md) number
- Message length
- Checksum (check for data integrity but simply discards corrupted data segments)
![](UDP-segment-structure.png)
> [!note]
> There are no host(IP) addresses in the header for UDP (same as [TCP](TCP.md))
> This is the [Network Layer](Network%20Layer.md) Responsibility

