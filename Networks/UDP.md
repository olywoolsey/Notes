# UDP: User Datagram Protocol
- Best effort’: UDP segments may be delivered out-of-order, or lost altogether.
- Connectionless: no handshaking between sender and receiver
- Each UDP segment is handled independently of the others
Why is there a UDP?
- Connection establishment can add a delay
- Smaller segment header
- No congestion control, so can send as fast as desired
## Segment Structure
- Often used for streaming applications that are loss tolerant but rate sensitive.
- Can add reliability at the Application layer if needed.
- DNS uses UDP (fast; small messages).
- So does SNMP (Simple Network Management Protocol) for similar reasons.
![](UDP_Segment_Structure.png)
