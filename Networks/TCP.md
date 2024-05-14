# Transition Control Protocol
- Connection-oriented protocol
- Point-to-point: One sender, one receiver
- Reliable as requests lost data again
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

## Acknowledgement
### Positive
- Receiver sends a positive acknowledgement ACK if the packet was received without errors
- While reciever has sent positive ACK the sender might not get it and could send the package again
- If this happens then the sequence number will be compared and if it's already received then it will send a positive ACK even if the data was corrupted
**Bit Errors:**
- Can detect for occurrences using the checksum
- If error cannot be corrected then will send a negative acknowledgement
