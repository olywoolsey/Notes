# Transition Control Protocol
The most widely used [Protocol Stack](Protocol%20Stack.md) mode for the internet, and the most relevant for this course, is a simplified version of the [OSI Model](OSI%20Model.md)
- Presentation and Session layers merged into Application.
- Network layer sometimes called the Internet layer.
- (Data-)Link and Physical layers sometimes merged to give a4-layer model (or the Physical layer simply dropped).

| Layer                                 | Usual Name For Packet     | Address Or Similar                               |
| ------------------------------------- | ------------------------- | ------------------------------------------------ |
| [Application](Application%20Layer.md) | Message                   | -                                                |
| [Transport](Transport%20Layer.md) | Segment ([UDP](UDP.md))   | Port                                             |
| [Network](Layer%20-%20Network.md)     | Dataframe ([UDP](UDP.md)) | IP (converted to host-names using [DNS](DNS.md)) |
| [Link](Layer%20-%20Link.md)           | Frame                     | MAC                                              |
| [Physical](Layer%20-%20Physical.md)   | -                         | -                                                |
Three layers (Transport, Network and Link) add headers (and possibly trailers/footers) to messages:
- Sizes depending on the protocol ([TCP](TCP.md)/[UDP](UDP.md); IPv4/IPv6; any number of [Ethernet](Ethernet.md)/IEEE protocols), but can be 20-40 bytes per header level.
- Means message sent over Physical layer can be much larger than the Application data
- Highlights importance of buffering at Application level to improve I/O performance (e.g. Java streams)
## Pros and Cons
### Pros
- Suited to network programming (particularly java.net, which is designed around TCP/IP)
- Simpler than the [OSI model](OSI%20Model.md).
- Well suited to the internet
### Cons
- Layers and protocols are not always clearly defined
- For example, security protocols sit ‘between’ layers
- Lacks generality
