- *there is a piece of the network layer in each and every host and router in the network*
- can be composed of the **Data Plane** and the **Control plane**
- software defined networking (SDN) separate the data and the control pane. 
- routers do not run application and transport layer protocols
- 2 important functionality: 
	- **Forwarding**: router must move a packet from its input link to the appropriate output link
		- short time scales
		- typically implemented in hardware
		- in data plane
	- **Routing**: 
		- implemented in the control pane
		- determine the route taken by packets as they flow from sender to receiver
		- **routing algorithms**
		- in control pane
- **Forwarding Table**:
	- a router forwards a packet by examining the value of one or more fields of the arriving packet's header, and then index's it into its forwarding table. The output tells it the link in which is needs to be forwarded
### How are the router's forwarding tables configured?
- physically seperate remote controller computes and distributes the forwarding tables to be used by each and every router
- this controller might be managed by an ISP or some third party
- SDN is open source, so researchers can looking into it

### Network Service Model:
- This models defines the characteristics of end-to-end delivery of packets between sending and receiving hosts.
- the Internet's network layer provides the **best-effort service**
- no guarantee of order of packets, no guarantee of delivery of packet, no minimum bandwidth
- **forwarding and switching are used interchangeably**
- **link-layer switches**: base their values on the fields in the link-layer frame 
- **routers**: base forwarding decisions on header field values in the network layer datagram
