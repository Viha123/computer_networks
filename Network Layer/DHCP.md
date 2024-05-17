- Dynamic Host Configuration Protocl (DHCP): is a client/server protocl that automatically provides an IP with its IP address and other related configuration information such as the subnet mask and default gateway
- ### DHCP: dynamic host config protocol
- host dynamically obtains IP from network server when it joins network
- can renew its lease on address in use
- allows reuse of addresses
- support for mobile users who join and leave network
- what layer protocol is this:?
	- application layer 
	- runs on UDP
- **Default gateway**: address of first hop router
- 4 step process when a new host arrives and tries to get a ip address:
	1. *DHCP server discovery*: done through the dhcp discover message, which a client sends through a UDP packet to port 67. But who does it send this too? sends to a broadcast destination IP address. Broadcasts to all nodes in the subnet
	2. *DHCP server offer(s)*: many DHCP server respond with **offer message** which is also broadcast to all. each server offer consists of: transaction ID, proposed IP address, the network mask and an IP address lease time.
	3. *DHCP request*: the client will send to a selected offer with a request message
	4. *DHCP ACK*: server responds and confirms the requested parameters
1. 
