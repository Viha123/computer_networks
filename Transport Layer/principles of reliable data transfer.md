- For example, TCP is a reliable data transfer protocol that is implemented on top of an unreliable (IP) end-to-end network layer.
- how do you guarantee reliability
- reliable service **abstraction**
- complexity of reliable data 
- reliable data transfer protocol: **RDT**
- finite state machines
- **rdt1.0:** **reliable transfer over reliable channel:** 
	- separate FSMs for sender, receiver
	- ![[Pasted image 20240226123100.png]]
- **rdt2.0: channel with bit errors**:
	- acknowledgements (ACK) receiver explicityly tells sender that pkt received OK
	- NAKs: receiver explicitly tells sender that pkt had errros
	- sender re-transmits pkt on receipt  of NAK
	- **stop and wait**:
		- sender sends one packet, then waits for receiver response
	- In TCP:
		- if 1/10 packets weren't received, 
		- receiver can ask sender to resend packet 4: then it will send from 4, 5,6,7,8,9,10 again because most TCP does not have NAKs
	- ![[Pasted image 20240226123611.png]]
	- Timeout: if once sent, no message received, timeout can be implemented
- fatal flaw!:
	- what happens if ACK/NAk corrupted?
		- sender doesnt' know what happened at receiver
		- can't jsut retransmit: possible duplicate
	- handling duplicates:
		- sender retransmits current pkt if ACK/NAK corrupted 
		- sender adds sequence number to each pkt
		- receiver discards (doesn't deliver up) duplicate pkt
		- sequence number
- timeout is different than TTL
- problem of premature timeout
### calculate utilization
- **utilization**: fraction of time sender busy sending
- $Dtrans = L/R$
- $Usender = (L/R)/(RTT + L/R)$

Pipelining Protocols equation
- sender allows multiple, "in-flight", yet to be acknowledged packets
pipelining increases utilization


### Selective Repeat:
- receiver individually acknowledges all correctly received packets
	- buffers packets, as needed, for eventual in-order delivery to upper layer
- sender times out/retransmits individually for UNNACKED packets
- SACK: selective acknowledgement
