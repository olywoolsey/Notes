# The Full Picture
After connecting, the laptop needs an IP address:
- Laptop’s OS places a DHCP request into a [UDP](UDP.md) segment, itself placed into an IP datagram, which is then broadcast across the Ethernet within a link-layer frame
- Ethernet switch sends this message to all outgoing ports, including the router which extracts the request
- Router returns an DHCP message (inside a UDP segment, inside an IP datagram, inside a link-layer frame)
- Laptop extracts DHCP message, its IP address, and the address of the DNS server it will use.

The student now types www.google.com into their browser, which needs to be converted to an IP address using the DNS:
- Browser creates a DNS query and puts it into a UDP segment with a destination port of 53
- Sent to the configured DNS server (as always, after placing in an IP datagram inside a link-layer frame)
- Does not yet know the MAC address of the router, so creates an ARP query1 and broadcasts within a link-layer frame
- Router sends an ARP reply (in a link-layer frame) to the laptop’s OS

The laptop can now send its DNS query via the router.  
- Router extracts query (from the frame, datagram, segment) and uses its forwarding table to see where to send it
- Places inside a segment, datagram, frame, and sends
- Travels to the DNS server via various routers (RIP; OPSF; BGP; cf. Lecture 18)
- DNS server checks its cache and, presuming it is found, sends a DNS reply to the laptop (segment/datagram/frame)
- The Laptop’s OS extracts the message and the IP address for www.google.com
- Web browser creates a TCP socket, which first performs a handshake with the web server
- Each stage in this handshake uses the port number for the browser, and port number 80 for the server
- Browser creates an HTTP GET request which is forwarded via one or more router(s) to the server
- The server returns an HTTP response message to the laptop
- The laptop extracts the information and displays it

Of course, all messages sent between the browser and the server are placed in a TCP segment, itself placed in an IP datagram, itself placed in a link-layer frame . . .  