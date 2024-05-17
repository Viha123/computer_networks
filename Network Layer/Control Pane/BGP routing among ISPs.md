- Border gateway protocol
- is a similar to Distance Vector type algorithm. It advertises reachability information: "I am ehre, here is who i can reach, and how"
- 2 types: EBGP (exterior) and IBGP (interior)
- in the internet all ASs run the same inter-AS routing protocol
- BGP is a decentralized and asynchronous protocold
- **autonomous system**
	- 1 organization controlling all routers within the organization
	- like how do ISPs communicate with each other is the question that BGP answers
	- 16 bit number, that an organization assigns
- eBGP: obtain subnet reachability info from neighboring ASes
- iBGP: propagate reachability ifnromation to all AS-internal routers
- runs on TCP port 179
- RIP ran on UDP port 520
	- when 2 AS connect there is eBGP connectivity. Withink autonomous system, there is iBGP. 
- within Autonomous system, virtual connection
### BGP Basics
- BGP session: two BGP two routers exchange BGP messages over semi-permanent TCP connection
	- advertising paths to different destination network prefixes
- path attributes and BGP routes:
	- BGP advertised route: prefix + attributes
	- prefix desination being advertised
	- two important attributes:
		- AS-PATH
		- NEXT_HOP
	- policy based routing
		- gateway receiving 

### The role of BGP
- In BGP the packets are not routed to a specific destination address but instead to CIDRized prefixes, with each prefix representing a subnet or a collection of subnets.
- BGP provides each router the ability to:
	- advertise its existence to the rest of the internet. (*Obtain prefix reachability information from neighboring ASs*.)
	- determine the best routes to the prefixes
### how does BGP Advertise route information
- for each AS, a router is either a **gateway router** or a **internal router**
- gateway router: directly connects to a router in another AS (edge)
- *internal router* connects only to hosts in the same AS
- eBGP connection and iBGP connection
- iBGP connections do not always correspond to physical links
### Jargon
- when a BGP connection is advertised it includes a prefix and several **BGP attributes**
- in BGP jargon a prefix along with its routes is called a route
- AS-PATH (*list of ASes the advertisement as passed*) and NEXT-HOP are 2 of the most important attributes
- ==NEXT-HOP:== **IP address of the router interface that beings with AS path**

## hot potato routing
- the idea of this is to get the packet out of the AS as quickly as possible without worrying about the path from teh other AS to the destination
- two routers in the same AS may choose different AS to transfer to
- ![[Pasted image 20240417090211.png]]
## Route selection algorithm:
- if 2 or more routes point to the same output then: 
	- local preference attribute assigned by net admin. highest local pref selected
	- from the remainign route with the highest local pref, the route iwth the shortest AS-PATH is selected
	- if that is the same, then hot potato routing is used
	- last the router uses bgp identifiers to select the route

## IP anycast
- service implemented by BGP that is used in DNS
- motivation for anycast:
	1. replicate some content on different servers
	2. having each user access the content through the server
- the point is that many CDN servers will have teh same IP address, adn they will broadcast their IP. Each router will use BGP to determine the shortest way to get to that IP, and although these are different physical locations there will be different routes to get to that IP. So this way internet routers find the IP address of the closest web server. 
- used in DNS because only 13 ip addresses for DNS root servers exist but there are many root servers. any cast is used to route the query to the nearest DNS root server 
## Routing policy
- 