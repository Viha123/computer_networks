connection oriented transport
transport is end to end. 
between sender and recevier
- **point to point**:
	- one sender, one receiver
- **reliable, in order byte stream**:
	- no "message boundaries"
- **full duplex data**: (vs Simplex which goes only in one direction)
	- bi-directional data flow in the same direction
	- maximum segment size
		- we don't want to overwhelm slow`` receivers
- **Cumulative ACK**
- **pipelining**:
	- tcp congestion and flow control set window size
- **connection-oriented**:
	- handshaking (exchange of control messages) initializes sender, receiver state before data exchange
- **flow controlled**:
	- sender will not overwhelm receiver
### TCP segment structure:
![[Pasted image 20240228122334.png]]
### TCP Sequence numbers:
- **Sequence numbers**:
	- number of first byte in segment data
- **Acknowledgements**:
	- seq# of next byte expected from other end
- ![[Pasted image 20240228123243.png]]
### TCP Round Trip time, timeout:
- RTT (round trip time)
- how to set timeout:
	- should be longer than RTT, but RTT varies
	- if its too short, then unnecessary transmissions
	- if its too long: slow reaction to segment loss
- TimeoutInterval = EstimatedRTT  + 4* DEVRTT (safety margin)
- math for DEVRTT and Estimated RTT
- ACK Generation:
- ![[Pasted image 20240228124025.png]]
- TCP retransmission scenarios:
	- if hasn't received a previous one, but has recevied a later, then it can just continue to transmit the next one
### TCP fast retransmit:
- if many packets are sent, and one or some of the packets aren't received, but others are received. Then hostB sends the ACK for whichever one was lost, send N times
- tells the sender that there is a missing segment
### TCP flow control:
- What happens if network layer delivers data faster than application layer removes data from socket buffers
- that is the point of flow control: # of bytes the receiver is willing to accept
### TCP connection management:
- before receiving/sendign data, 2way handshake
- agree to establish connection, agree on connection parameters
- problem with a 2 way handshake is what if one of the messages gets dropped

### closing a TCP connection:
- client, server, each close their side of connection
- we don't want to have a connection in half open state
- Synattack 

### TCP textbook notes:
- TCP connection provides a **full-duplex service**: if there is a TCP connection, application data can flow from process A to B at the same time as it does from process B to A
- TCP cannot do one sender many receivers
- three way handshake
- **MSS: maximum segment size**
- TCP segment header: 
	- 