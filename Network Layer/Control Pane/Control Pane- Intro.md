- SNMP: simple network management protocol (on UDP)
	- helps configure and manage networking infrastructure
- OSPF and BGP
	- enterprise: OSPF
	- BGP used between **autonomous systems** (service provider who maintains their own network like Google/Facebook, they get unique AS (aton system) number)
- OpenFlow, ODL and ONOS controllers
- Internet control message: ICMP (traceroute, ping)
- SNMP, YANG/NETCONF

### 2 types of routing protocols:
- link state
	- topology of network
	- LSA (link state advertisements)
	- computes route to other routes in network
- distance vector
	- connected to peers
	- each router send their routing table. and use collective information to combine
- within the ISP routing: OSPF
- between the different ISPs: BGP
- SDN (software defined networking) come up with rules that are sent to different routers

Link state: 
- cost always be 1 or inversely related to bandwidth or inversely related to congestion
- for this to work every router must have a complete picture of the network. it should know the topology (**centralized**)
	- accomplished via link state broadcast, all nodes have same info
	- 
- link state reacts to changes must faster
Dijkstra's link-state routing algorithm:
- route oscillations are possible

Bellman Ford (Distance Vector Algorithm):
- uses dynamic programming remember previous answers essentially
- count to infinity problem
## More intro facts
- OSPF and BGP use the per-router control approach where the routing table and forwarding table exist in the router itself

