- covered forwarding in previous chapter 
- ISP may not be able to SDN to a router that is not in its control
- **routing:** determine route taken by packets from src to destination
- algorithms with global state information are known as **Link-state algorithms**
- **decentralized routing algorithm**: each node does not have the full information, however through an iterative process of calculation and exchange of information with neighboring nodes it is able to compute more.Example of such algorithm: **Distance Vector**
- static vs dynamic routing algorithms:
	- dynamic are run periodically or over link changes 
	- but more susceptible to problems such as routing loops and route oscillation
	- 
- **load sensitive**: link costs vary dynamically to reflect the current level of congestion in the underlying link.
- today's routing algorithms such as RIP, OSPF, and BGP are load insensitive as a link's cost does not explicitly reflect its current level of congestion.
- Dijkstra's is a link state algorithm

### Distance Vector Algorithm
![[Pasted image 20240410084724.png]]

- Bellman ford equation (with a little code twist)
 $$ D_x(y)=min_{all neighbors of node}(C(x,neighborNode) + d_{NeighborNode}(y))$$
 - the bellman ford provides the entries in node x's forwarding table.
 - if v* is known to be the node with min distance to y, then x's forwarding table would specify node v* as the next-hop router for the ultimate destination y.
 - decentralized
 - used by RIP and BGP and ISO, and IDRP and the original ARPAnet
 - distance vector in operation:
 - ![[Pasted image 20240410092339.png]]
 - **count to infinity problem**!
	 - when a cost has increased, the time taken for the increase to take into affect is huge. because there will be a routing loop.
	 - can be avoided using a technique called *poisoned reverse*
	 - z will advertise to y that Dz(x) = infinity. This way y will never route through z. 
	 - loops involving three or mode nodes will not be detected by the poisoned reverse technique
**per router control pane**:
- **Research count to infinity problem**
- **distance vector protocol an da** 
- **difference between ospf (link state protocol) and rip which is a (distance vector protocol)**

- **why is rip v1 bad?**
	- ripv1 doesn't have subnet, v2 has VLSM, CIDR and route summarization.
	- can rip v1 and rip v2 work together
- implementation of OSPF
- ISIS: intermediate system to intermediate system
which protocol converges faster?
- convergence: how quickly do all routers know the state of an updated router
- ospf will not 
- **reliable flooding**

### Intra-AS Routing in the Internet
- 2 problems: scalability and administrative autonomy
- solved by organizing routers into autonomous systems
- routers in the same AS have the same routing algorithm running, and its called an **intra-autonomous system routing protocol**
- 


