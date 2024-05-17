four key characteristics of an SDN can be defined
- **flow based forwarding**:
- **separation of data plane and control pane**:
- **network control functions**:
- **a programmable network**:
## the sdn controller pane: sdn controller and sdn network-control applications
- functionality into 3 layers:
	- *a communication layer*: transfer info between the sdn controller and the device that it controls. device must be able to provide status to sdn. "Southbound interface"
	- *network wide state management layer*: state includes flow tables that go into the routers, configuring flow tables to implement load balancing, or implement firewall capability etc
	- *interface to control network layer*: talking to rest api and give network graph information i guess?
## openflow protocol
- port 6653
- important messages flowing from controller to the switch would be:
	- configuration, modify-state, read-state (statistics from switch), send-packet.
- messages flowing from switch to controller:
	- flow removed, port-status(change in port status), packet-in (packet not matching any flow table entry sent to controller)
- 