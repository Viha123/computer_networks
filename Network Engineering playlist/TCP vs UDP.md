#computerNetworks 
### TCP
- stateful
- transport communication protocol
- server memory is a con because you risk of [[DDos -distributed denial of service]]
	- server needs to keep checking a port
	- limit to number of connections you can make
- acknowledgment
- ordered packets
- larger packes (cons)
- congestion control
- guaranteed delivery
- slower than UDP
- more bandwidth required
### UDP
- user datagram protocol
- since no communication there is no security. 
	- thats why a lot of files disable UDP altogether
	- you just send data and that is so unsafe
- no ordered packets
- pros:
	- smaller packets
	- less bandwidth
- faster
- stateless
	- if server dies, then client can continue sending information
- [[DNS]], [[DHCP]] run on UDP
- 