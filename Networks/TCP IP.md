# Transition Control Protocol
The most widely used [Protocol Stack](Protocol%20Stack.md) mode for the internet, and the most relevant for this course, is a simplified version of the [OSI Model](OSI%20Model.md)

| Layer       | Usual Name For Packet     | Address Or Similar                               |
| ----------- | ------------------------- | ------------------------------------------------ |
| Application | Message                   | -                                                |
| Transport   | Segment ([UDP](UDP.md))   | Port                                             |
| Network     | Dataframe ([UDP](UDP.md)) | IP (converted to host-names using [DNS](DNS.md)) |
| Link        | Frame                     | MAC                                              |
| Physical    | -                         | -                                                |
Three layers (Transport, Network and Link) add headers (and possibly trailers/footers) to messages:
- 


- Presentation and Session layers merged into Application.
- Network layer sometimes called the Internet layer.
- (Data-)Link and Physical layers sometimes merged to give a4-layer model (or the Physical layer simply dropped).
## Layers
### [Layer - Application](Layer%20-%20Application.md)
- User code and interface reside here.
- Sends data into the Transport layer, and delivers data to the user from the Transport layer.
- The protocol used determines what is done with incoming data :
	- http - display in a browser.
	- ftp - deliver a data file.
	- smtp - open an email client.
	- etc.
- Can also create user-defined protocols
### Transport Layer
- Raw data packets can be corrupted, arrive out-of-order, or not arrive at all!
- Essentially two protocols exist at this layer:
	- [TCP](TCP.md)  - Transmission Control Protocol
		- Ensures all packets/segments are received.
		- May ask for re-transmission.
		- Can have a high overhead.
	- [UDP](UDP.md) - User Datagram Protocol
		- Detects corruption, but not ordering or lost pack-ets/segments.
		- Low overhead.
### Network Layer
- Most common protocol is the Internet Protocol, or IP
	- .Describes how data is grouped into datagrams (packets).
	- The network addressing scheme.
- A datagram is produced containing the data and header information.
- Also ICMP (Internet Control Message Protocol), which is how routers communicate to ensure efficient transport of messages through the network.
- Java only understands IP
### Link Layer
- The Link layer controls how packets are transported between network nodes.
- How e.g. your device or laptop is detected by a Wi-Fi network.
- Error checking, which may be redundant (i.e. repeated atanother level)
### Physical Layer
- The Physical layer is where data is converted to/from e.g.electrical or radio signals.
- May involve digital-to-analogue conversion.
- Sometimes merged with the Link layer
## Pros and Cons
### Pros
- Suited to network programming (particularly java.net, which is designed around TCP/IP)
- Simpler than the OSI model.
- Well suited to the internet.
### Cons
- Layers and protocols are not always clearly defined
- For example, security protocols sit ‘between’ layers
- Lacks generality
