# Transition Control Protocol
- Point-to-point: One sender, one receiver
- Reliable
- Send and receive buffers
- Pipelined: Send multiple packets without waiting for acknowledgement of the first
- Bidirectional data flow in same connection
- Connection oriented: Handshaking (exchange of control messages) before actual packet transmission
- Flow control: Sender will notoverwhelm the receiver
## TCP Segment Structure
![](TCP-segment-structure.png)
## TCP Flow Control
- The idea of flow control is that the sender won’t overrun receiver’s buffer by transmitting too much, too fast
- **Receiver:** Explicitly informs the sender the (dynamically changing) amount of free buffer space. The Rcv Window field in TCP segment 
- **Sender:** Keeps the amount of transmitted, unacknowledged data less than most recently received Rcv Window