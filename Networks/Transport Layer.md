# Transport Layer
- Provides ports to control data transfer between processes
- Raw data packets can be corrupted, arrive out-of-order, or not arrive at all!
- Essentially two protocols exist at this layer:
	- [TCP](TCP.md)  - Transmission Control Protocol
		- Ensures all packets/segments are received
		- May ask for re-transmission
		- Can have a high overhead
	- [UDP](UDP.md) - User Datagram Protocol
		- Detects corruption, but not ordering or lost pack-ets/segments
		- Low overhead

## Reliable Data Transfer
![](reliable-data-transfer.png)

## Congestion Control
- Routers typically have multiple input and output lines.  
- If streams of packets arriving on multiple lines and all need the same output line, a queue will build up.  
- If capacity of the buffer is exceeded, packets will be discarded (lost)
- Slow processors can also cause congestion:  
	- Queueing buffers, updating router tables etc. usually require processing
### End-to-end Congestion Control
I.E. Flow Control (Like as is adopted by [TCP](TCP.md)):
- The idea of flow control is that the sender won’t overrun receiver’s buffer by transmitting too much, too fast
- **Receiver:** Explicitly informs the sender the (dynamically changing) amount of free buffer space. The Rcv Window field in TCP segment 
- **Sender:** Keeps the amount of transmitted, unacknowledged data less than most recently received Rcv Window
- No explicit feedback from the network
- Congestion inferred from loss and delay observed by the end systems and hosts
### Network Assisted Congestion Control
- Routers provide feedback to end systems
- Either:
	- Single bit indicating congestion
	- Explicit rate sender should send at