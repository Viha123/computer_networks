- most routers are dual stack: they have both IPv4 and IPv6
- ![[Pasted image 20240318175653.png]]
	- ipv6 has introduced a new type of address in addition to unicast and broadcast: anycast: allows datagram to be delivered to  any one of a group of hosts
	- a lot of v4 fields have been dropped such as checksum, allows faster processing
	- flow: kind of like priority. real time audio and video have more priority, and people who pay more also have more priority
	- next header: specifies the protocol to which the contents of the datagram will be delivered
	- *fragmentation and disassembly* is an expensive operation and the funcitonality is removed from the router to the end system. if its too big user will get a packet is too big error

### Tunneling:
- intervening set of IPv4 routers between two IPv6 routers is a tunnel
- use tunneling method where you put IPv6 inside the payload of a IPv4 and then indicate in the protocol field (number 41) that the payload is another IPv6 datagram
- 