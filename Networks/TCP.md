# Transition Control Protocol
- Point-to-point: One sender, one receiver
- Reliable
- Send and receive buffers
- Pipelined: Send multiple packets without waiting for acknowledgement of the first
- Bidirectional data flow in same connection
- Connection oriented: Handshaking (exchange of control messages) before actual packet transmission
- Flow control: Sender will notoverwhelm the receiver
## TCP Segment Structure
![](TCP_Segment_Structure.png)