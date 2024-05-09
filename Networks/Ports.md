# Ports
- Applications are linked to the Transport [layer](Protocol%20Stack.md) via network ports.
	- Different port numbers can be associated with different Application layer processes.
	- This allows multiple applications to run simultaneously on the same host with the same IP address.
	- Purely software, provided by the OS.
	- Can be allocated to a particular service, e.g. email, HTTP etc
	![](port-usage.png)
## Sending and Receiving
- Converting host-to-host delivery to process-to-process delivery is the job of the Transport layer.
	- Known as multiplexing (sending) and demultiplexing(receiving)
- Applications typically publish the port they are listening to(receiving on).
	- A sending process will attempt to establish a connection using the published port number.
	- Will continue to communicate using the same port number,but the port can also be used to initiate new contacts
## Available Ports
- Ports 1-65535 are available on any given host.
	- 16-bit unsigned int, with zero not allowed.
	- [TCP](TCP.md) and [UDP](UDP.md) ports and independent.
- Ports are characterised by:
	- Ports 1-1023 are reserved; approved by IANA (InternetAssigned Numbers Authority).
	- Commonly used ports lie outside this range, i.e. 1024-65535.
	- We can use any freely available ports in this range.
- To see ports on a UNIX machine, look at `` /etc/services ``
### Port Examples
#### telenet
- Port 23
- Short for teletype network
- The original client-server communication protocol
- Now is rarely used as is insecure
#### ssh
- Port 22
- Secure Shell
#### ftp
- File Transfer Protocol
- Port 21 for commands (dir, put, get, etc)
- Port 20 used for data (the og use ; slow)
#### smtp
- Port 25
- Stands for simple Mail Transfer Protocol
#### imap
- Port 143
- Used to access mail
- Stands for Internet Message Access Protocol
#### pop3
- Port 110
- Used to access mail
- Stands for Post Office Protocol
#### http
- Port 80
- Stands for Hypertext Transfer Protocol
- Insecure
#### https
- Port 443
- Secure version of http, requires authentication
