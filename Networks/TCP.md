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

## Reliable Data Transfer (RDT)
The sender waits until one acknowledgement(ACK) or another is received and re-sends the packet if necessary
- Only need 2 sequnce numbers for ACKs but will use more if pipelining (sending multiple packages)
### Positive
- Receiver sends a positive acknowledgement ACK if the packet was received without errors
- While receiver has sent positive ACK the sender might not get it and could send the package again
- If this happens then the sequence number will be compared and if it's already received then it will send a positive ACK even if the data was corrupted
### Negative
- Sends a negative acknowledgement NAK if  errors were detected
**Bit Errors:**
- Can detect for occurrences using the checksum
- If error cannot be corrected then will send a negative acknowledgement
### Corrupted ACKs
- If the ACK is corrupted and doesn't return / returns corrupted the sender will always send another package
- If a positive ACK gets corrupted then the receiver will detect this if the sequence numbers match
