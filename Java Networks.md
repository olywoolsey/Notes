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
