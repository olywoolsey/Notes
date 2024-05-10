# MAC Addresses
- Identify a device on a local network (LAN) and are used for communication between devices on the same network.
- Are unique to a specific network interface or device, making them a reliable way to identify a device on a LAN.
- Allow for efficient packet transfer within a LAN, as they are used to determine the destination device on the same network.
- Are used by the data [Link Layer](Link%20Layer.md) of the [OSI Model](OSI%20Model.md) to manage data transmission within a LAN.

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