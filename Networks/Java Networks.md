# Java Librarys
## java.net
### InetAddress class
- Used by: Socket, ServerSocket, URL ...
- Includes both the IP addresses and the host name
- Used to represent both IPv4 and IPv6 addresses

There is no public constructor for InetAddress. Instead, three static methods can return an InetAddress object:
```java
// Most common
public static InetAddress getByName( String hostname )
```
```java
// Returns an array of InetAddress objects
// Depends on configuration of local DNS server
public static Inet Address[] getAllByName( String hostname )
```
```java
// The address of host running code
public static InetAddress getLocalHost()
```
### SSLSocket class
An SSLSocket is constructed by an SSLSocketFactory.  
Use of factory (rather than a constructor) allows additional  
security (e.g. authentication)


## Multi Threaded Server
Java's built in *Thread* class
- Shared memory (uses multiple cores for one machine, but only one machine node)
- One thread per client

**SEE LECTURE 10 / 11 / 12**


## Security
*LECTURE 13*
- Can generate and manage certificates using the keytool utility.  
- Part of the standard Java distribution Java SE.  
- Require certificates to implement our own secure communication
- Java Secure Socket Extension (JSSE):  
	- javax.net.*  
	- Includes Secure Sockets Layer (SSL) as javax.net.ssl.*  
	- Also includes the more recent Transport Layer Security (TLS)
- Technically break 5 layer [TCP IP](TCP%20IP.md) protocol but not 7 layer [OSI Model](OSI%20Model.md)

## UDP
**SEE LECTURE 14**