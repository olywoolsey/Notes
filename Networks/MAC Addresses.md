# MAC Addresses
Whatever the protocol, each node must have a unique MAC (Media Access Control) address

The MAC (or LAN, physical, Ethernet) address:  
- Used ‘locally’ to get frame from one interface to another.  
- Both interfaces in the same network (in IP sense).  
- 48-bit MAC addresses burned into NIC ROM.  
- e.g. 1A-2F-BB-76-09-AD

MAC addresses only matter locally so can be 

## Creation of MAC Addresses
- MAC address allocation done be IEEE
- Manufacturer buys a range of MAC addresses - unique
- Even though all devices should have separate MAC addresses it is possible to randomise:
	- Most phones support random MAC addresses
	- Every time you connect to a new network you will use a different MAC address

**ARP (Address Resolution Protocol)**: 
- When a device on the network needs to send a packet to another device, it uses ARP to resolve the IP address to a MAC address. 
- The router, as a Layer 2 device, maintains an ARP table that maps IP addresses to MAC addresses. 
- When a packet is received, the router checks the ARP table to determine the MAC address of the destination device.