# One to many Communication
- The server application sends one message but is routed to multiple clients
- Requires additional processing by routers
## Multicasting
- Sending to a group of hosts
- Predefined
- Router that receives the multicast has the addresses where it needs to send it next
## Broadcasting
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
### Multicast
The server delivers duplicate data to multiple clients . . .  
- . . . but only sends one copy onto the network.  
- Low risk of congestion in the link between server and the first (edge) router
#### Multicast Address
A set of IP addresses are available for multicast comm