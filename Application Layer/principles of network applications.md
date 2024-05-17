#computerNetworks 
- need to know HTTP/DNS/TLS (Transport layer security)
- Some network apps:
	- social networking, web, text messaging, email, p2p file sharing
- **creating a network app**:
	- write programs that:
		- run on different end systems
		- communicate over network
		- eg. web server software communicates with browser software
	- **no need to write software for network-core devices** (routing equipment) because all the work is done by custom selection
		- network-core do not run user applications
		- applications on end systems allows for rapid app development propagation
- private space ips: 10.8...., 192.168.0.211
	- martian IPs: 
- client-server-paradigm:
	- server:
		- always-on host
		- permanent IP address
		- often in data centers, for scaling
	- client:
		- may have dynamic IP
		- do not communicate directly with each other
		- examples: HTTP, IMAP, FTP
- DHCP: network access point will give you an IP address. 

**Peer-peer architecture**:
- no always-on server
- arbitrary end systems directly communicate
- peers request service from other peers, provide service in return to other peers
	- self scalability: new peers bring new service capacity, as well as new service demands
- peers are intermittently connected and change IP addresses
	- complex management
- example: P2P file sharing
**Process communicating**:
- process: program running within a host
- within same host, two processes communicate using inter-process communication (defined by OS)
- http port: 80, https: 443
- processes in different hosts communicate by exchanging messages
- Ephemeral Port: client's ip address

- **But what is a port**
	- port is a unique identifier to an application
	- 
**Sockets**:
- 2 sockets involved: one on each side
- sending
**network address translation?** 
Addressing processes:
- to receive messages, process must have **identifier**
- host devices 
An application protocol defines:
- types of messages exchanged: request, response
- message syntax: what fields in messages and how fields are delineated
- message sematics
- rules,
- open protocol,
- proprietery protocols
What transport service does an app need:
- **data integrity, throughput, security, timing**

Internet transport protocols: 

| TCP: transmission control protocoL? | UDP : User Datagram protocol |
| ---- | ---- |
| reliable transport | unreliable data transfer |
| flow control: sender won't overwhelm the receiver | does not provide reliability, flow control, congestion control, througput guarantee, security or connection setup |
| congestion control: throttle sender whn network overloaded |  |
| does not provide: timing, minimum throughput guarantee |  |
| connection-oriented: setup required between client and server |  |
| client's responsibility to restart connection |  |
|  |  |
TLS is built on top of TCP
real time data applications are UDP
DNS is on top of UDP and a little bit of TCP

Securing TCP:
- vanilla TCP and UDP sockets
- no encryption 
- Transport Layer Security (TLS):
	- encrypted TCP connections
	- data integrity
- 
