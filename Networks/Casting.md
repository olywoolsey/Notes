# One to many Communication
- The server application sends one message but is routed to multiple clients
- Requires additional processing by routers
## Broadcasting
- Only IPv4
- Can send to a (sub) network
- e.g. Everyone in the Uni, the country, the whole internet

The [Network Layer](Network%20Layer.md) supports broadcasting
- If a device is added to the network it first needs an IP address
- Initially communicates with local network via broadcasting
- Part of [DHCP](DHCP)
- The IPv4 address 255.255.255.255 is reserved for local broadcasting
	- Messages will not be forwarded by a router.  
	- Other hosts on the local network choose whether to listen.  
	- No IPv6 equivalent; instead multi-casts to ‘all hosts'
## Multicast
The server delivers duplicate data to multiple clients . . .  
- . . . but only sends one copy onto the network.  
- Low risk of congestion in the link between server and the first (edge) router
#### Multicast Address
A set of [IP addresses](IP%20Addresses.md) are available for multicast communication
- IPv4: [ClassD](IP%20Addresses.md)
- IPv6: Prefix ff00::/8
Each address represents a multicast group.  
- Servers send packets to this address.  
- Clients listen to this address; they are not connected
### Routing
Multicasting relies on the router to handle these addresses
Transparent to application programmers
- It is a service supplied by lower levels in the protocol stack
- Standard UDP-based network programming
### Scope
How far do we want our message to travel?  
- There is no direct connection.  
- We do no know who is listening.  
- Without some sort of control packets could proliferate, even without multicasting


  
 