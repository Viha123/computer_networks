- transport segment from sending to receiving host
	- sender encapsulates segments into datagrams, passes to link layer
	- receiver: delivers segments to transport layer protocol
- network protocols in every internet device: 
	- hosts, routers everything
- **routers**:
	- examines header fields (src, dst, checksum, protocol) in all IP datagrams
	- moves datagrams from input output ports to transfer
- **network layer functions**:
	- **forwarding**: moves packets from a router's input link to appropriate router output link
		- one interachange in the highway
	- **routing**: determine route taken by packets from source to destination
		- routing algorithms
		- path from src to destination
### data plane
- *local*, per router function
- determines how datagram arriving on router input port is forwarded to router output port
### control plane
- **networking-wide** logic
- determines how datagram is routed among routers along end-end path from source host to destination host
- two control-pane approaches:
	- traditional routing algoriths
		- implemented in routers
- per router control plane:
	- routing algorithm components in each and every router interact in the control pane
### SDN (software defined networking) control pane
- remote controller computes, and installs forwarding tables in routers
- happens within same organization

### Network service model:
- what **service model** for "channel" transporting datagrams from sender to receiver
- IP is a best effort
- no bandwidth, loss, order, or timing guarantees

ATM has constant bit rate (its a different kind of network architecture)
Internet: Diffserv (RFC 2475)

How does it work tho:
- sufficient provisioning of bandwidth which allows performance of real time to be good enough
- replicated, application layer distributed services, connecting close to clients's networks, allow services to be provided from multiple locations
### Router architecture overview
- high-level view of generic router architecture
- ![[Pasted image 20240306125551.png]]
- high speed switching fabric done in custom silicon

Input port functions:
- Routers make a decision on the longest prefix match
- when looking for forwarding table entry for given destination address, use longest address prefix that matches destination address

- Ternary Content Addressable memories (TCAMs) is where the routes are all stored
- **content addressable** present address to TCAM: retrieve address in one clock cycle, regardless of table size
