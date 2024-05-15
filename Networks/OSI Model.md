# Open Systems Interconnection reference model
- Developed in the 1970’s by the Organisation for Standardisation (ISO).
	- At a time when networking protocols were still being defined.
	- Probably not intended for the internet.
- Applies to networks in general.
- 7 layer stack.
- Sometimes used in text books and training courses

| Stack |
| ---- |
| Application |
| Presentation |
| Session |
| Transport |
| Network |
| Link |
| Physical |
## Layers
### Application Layer
- Layer contains the user-facing protocols.
- ftp, http, smtp, ...
### Presentation Layer
- Used to interpret data
- Includes Compression and Encryption tools
- Also data description (Format)
### Session Layer
- Layer organises and structures the dialogue between applications.
- Delimiting and synchronisation
### Transport Layer
- (Downwards) Accepts session data and splits into segments before passing to the [Network layer](Network%20Layer.md).
- (Upwards) Receives [Network layer](Network%20Layer.md) segments and constructs Session layer data.
- Data integrity depends on the protocol.Host-to-host communication 
	- Includes destination address in a header.
	- Oblivious to network infrastructure.
### Network Layer
- Controls the operation of the sub-network between hosts.
- Determines how packets (often called datagrams for this layer)are routed dynamically.
	- Links may be made or broken as machines are added to the network, break down etc.
- May also offer congestion control and quality of service.
- The highest level of the protocol stack for simple routers.
	- i.e. routers do not need Transport or Application layers, but will often have software to help routing, firewalls etc
### Link Layer
- The Link layer, sometimes known as the Data Link layer, handles the movement of frames (packets) from node-to-node along the route
	- Ethernet, Wi-Fi, and combinations.
	- This is the layer at which MAC (Media Access Control) addresses are relevant
### Physical Layer
- Handles movement at the bit level.
- Copper wire, fibre optic, radio waves etc.
- Purely hardware

## Pros and Cons
### Pros
- Clearly defined layers and protocols.
- Very general design that could be applied to any network (defence, cash machines etc.), not just the internet
### Cons
- Often overly complex.
- The Presentation and Session layers have minimal functionality that could easily be subsumed into the Application layer