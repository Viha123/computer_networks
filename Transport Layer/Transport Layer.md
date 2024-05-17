- [[TCP vs UDP]]
- [[OSI Model - Video]]
#computerNetworks
### Transport services and protocols:
- provide logical communication between application process running on different hosts
- each thing is called a segment in the transport layer, and passes it to network layer
- TCP and UDP
- **network layer**: logical communication between hosts
- **transport layer**: logical communication between process
	- relies on, enhances, network layer services
	- headers get added at one end and get stripped off at another end
	- 
	- contents of IP header?
		- ip address and port
		- TTL (time to live)
- Hop by hop:
	- network layer changes every hop
- Sender:
	- is passed an application layer message
	- determines segment header fields values
	- creates segment
	- passes segment to network layer
- Receiver:
	- receives segment from IP
	- checks header values
	- extracts application layer message
	- demultiplexes message up to application via socket
- built in header checksum to ensure packed is not corrected
- TCP protocol value: 6
- UDP protocol valule: 17
- when packet comes to network layer, the network should have some way of sending the packet to the right destination
- protocol field in the ip packet
- in case of TCP application gets it in order that the sender sent it
### Multiplexing/De-multiplexing
- multiplexing at sender:
	- handle data from multiple sockets, add transport header (later used for demultiplexing)
- demultiplexing at receiver:
	- use header info to deliver received segments to correct socket
- **ephemeral ports**
	- src operating system will pick a high port
- ![[Pasted image 20240221125200.png]]
### how demultiplexing works
- host receives IP datagrams
	- each datagram has source IP address, destination IP address
	- each datagram carries one transport layer segment
- host uses IP address and port numbers to direct segment to appropriate socket
- [[NAT]] - Network address translation
### Connection oriented demultiplexing
- TCP socket identified by 4-tuple
	- src: IP, port and dest IP, port
- demux: receiver uses 4 values to direct segment to appropriate socket

