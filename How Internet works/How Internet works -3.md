#computerNetworks 

- **packet switching vs circuit switching**:
	- circuit switching guarantees that no packets are lost once the connection is made
- Internet Structure: network of networks:
	- Hosts connect to internet via access Internet Service Providers (ISPs)
	- ISPs must be connected in turn
	- resulting network of networks is very complex
- Border Gateway Protocol v4
- Given millions of access ISPs, how to connect them together?
	- if every ISP is connected to every ISP, then that would be N^2, and that would be incredibly unmaintainable and stupid
	- **Option**: connect each access ISP to one global transit ISP
		- but if one global ISP is a viable business, there will be competitors
		- multiple global ISPs 
		- then there will be an **IXP** (Internet exchange points): peering exchange in different spots
- ![[Pasted image 20240131121755.png]]
- content delivery network:
	- wtf did i just hear i don't know what he talked about ask nina
- how do packet loss and delay occur:
	- packet loss occurs when arrival rate to link (temporarily) exceeds output link capacity
	- different delays:
		- d_prod, d_queue, d_trans, d_prop
	- queuing is the waiting at output link for transmission
	- nodal processing: check bit errors
	- transmission delay: L/R (packet length / link transmission rate)
	- propagation delay: how much time the packet spends on the cable itself, calculated in d/s (length of link and s is the speed)
- packet queuing delay:
	- packet arrival rate:
		- customers coming to the queue
		- denoted by A
	- we want to keep the L (packet length)/R Link bandwidth (bps) as low as possible
- **ICMP**: Internet control message protocol
	- time to live
	- ping, traceroute runs on icmp protocol
- multi-cast:  
- any-cast: multiple server with the same address, routing will try to get you to the closest 
- no IPv6 route, because the sjsu wifi hasnt' implemented it
**Network security**:
- usually designed for trusty users
- **Malware**:
- spyware malware
- [[DDos -distributed denial of service]]:
	- attackers make resources(server, bandwidth) unavailable to legitimate traffic by overwhelming resource with bogus traffig
	- cloud flag
	- **CDN**
- 
- packet sniffing: 
	- promiscous network interface reads/records all packets passing by
	- 
- iwancry virus: 
**MAC address**: burn in address, cannot change it. 
broadcast frame -> 2nd layer from bottom
every machine has a gateway and a routing table. 