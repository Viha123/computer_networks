### IPV4 Datagram format
![[Pasted image 20240313091801.png]]
- version#
- headers can be variable 
- type of Service (**TOS**): 2 of these TOS bits are used for the explcit congestion notification, its useful to distinguish whether it is real time or not
- Datagram length: field 16 bits long, theoretical maximum size of datagram si 65K bytes
- Identifier, flags, fragmentation offset: if large packets are chopped down and forwarded independently. V6 does not allow this anymore
- TTL
- Protocol field: used only when the IP reaches its destination. 6 indicates TCP, 17 indicates UDP
	- protocol number binds the network and transport layer
	- port number binds the transport and application layer
- Header checksum: 
	- recomputed at each router because TTL and some other fields might change
- ![[Pasted image 20240313092701.png]]
- Options: allow a IP header to be extended 
- In total if a datagram carries a TCP segment it carries 40 bytes of header: 20 bytes of TCP segment and 20 bytes of IP header
### IPV4 Addressing:
- the host typically has only one link into the network
- when IP in the host wants to send a datagram it goes over this link. the boundary between the host and the link is called the **interface**
- IP requires each host and router interface to have its own IP address
- IP is attached to an interface rather than the host or router 
- each interface on every host and router in the global Internet must have a IP address that is globally unique
- **subnet**: a network interconnecting n host machines and one router interface
- each isolate network is called the subnet
- The Internet's address assignment strategy is known as: Classless Interdomain Routing (**CIDR**)
- a.b.c.d/x. x is called **prefix**, number following slash represents network size
- difference between switch and router:
	- switch is a L2 device, router is a L3 device
- 10/8 -> 10.0.0.0/8, identifies network, remaining bits to identify hosts within networks
- ![[Pasted image 20240313121107.png]]
- all 0s to identify network, all 1s to broadcast

### IP addressing : CIDR
1. convert to binary
2. draw the line for the subnet mask

IP addresses: how to get one?
- How does host get IP address within its network?
	- DHCP: Dynamic Host Configuration Protocol
- How does a network get IP address for itself
	- ICANN: body has to apply for an ICANN, they need to pay some money to get that IP address
	- role of this organization is to allocate IP addresses as well as manage DNS root servers.
	
- IP broadcast address: 255.255.255.255
- 
