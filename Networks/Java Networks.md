# Java Library's
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
*LECTURE 13*
- Can generate and manage certificates using the keytool utility.  
- Part of the standard Java distribution Java SE.  
- Require certificates to implement our own secure communication
- Java Secure Socket Extension (JSSE):  
	- javax.net.*  
	- Includes Secure Sockets Layer (SSL) as javax.net.ssl.*  
	- Also includes the more recent Transport Layer Security (TLS)
- Technically break 5 layer [TCP IP](TCP%20IP.md) protocol but not 7 layer [OSI Model](OSI%20Model.md)

An SSLSocket is constructed by an SSLSocketFactory.  
- Use of factory (rather than a constructor) allows additional security (e.g. authentication)
Plain Socket with added layers of security protection:  
- public class SSLSocket extends Socket
- Once created they act like a plain Socket
```java
SLSocketFactory factory = (SSLSocketFactory) SSLSocketFactory.getDefault();
SSLSocket socket = (SSLSocket) factory.createSocket(host,port);
```
- By choosing different factories, can choose e.g. different methods and algorithms for authorisation or encryption.  
- getDefault() returns a factory class for server-side authentication with encrypted communication1.  
- Alternatives can be found using the getSupportedCipherSuites() method of SSLSocketFactory.  
- getEnabledCipherSuites() gives those that are allowed.  
- Needs to be negotiated by client and server.  
- Network communication functionality is inherited from the Socket
- Plain ServerSocket with added layers of security protection:  
- public class SSLServerSocket extends ServerSocket  #
- Once created they act like a plain ServerSocket, i.e. they inherit network functionality from ServerSocket.  
- Any client that wishes to connect must follow the server’s security protocol.  
- Part of the server protocol.  
- Avoids risk of malicious client deliberately requested weak security.
```java
private void runServer () {  
	try {  
		sslsocket = (SSLSocket) sslserversocket.accept () ;  
		BufferedReader bRead = new BufferedReader(
								new InputStreamReader(
									sslsocket . getInputStream () ) ) ;  
		String string = null ;  
		while ( ( string = bRead () ) != null ) {  
			System . out . println ( string ) ;  
			System . out . flush () ;  
		}  
		sslsocket . close () ;  
		sslserversocket . close () ;  
	}  
	catch ( IOException ex ) { ... }  
}
```
```java
private void runClient () {  
	try {  
		BufferedReader bIn = new BufferedReader (  
								new InputStreamReader(System . in ) ) ;
		BufferedWriter bOut = new BufferedWriter(  
								new OutputStreamWriter(
									sslsocket.getOutputStream()));
		String string = null ;  
		while ( ( string = bIn () ) != null ) {  
			bOut ( string + ’\ n ’ ) ;  
			bOut();
		}  
		sslsocket . close () ;  
	}  
	catch ( IOException ex ) { ... }  
}
```
The text sent by bOut.write() is now encrypted
## Multi Threaded Server
Java's built in *Thread* class
- Shared memory (uses multiple cores for one machine, but only one machine node)
- One thread per client

**SEE LECTURE 10 / 11 / 12**

## Multicast Socket class
**SEE LECTURE 15**

**SEE LECTURE 14**