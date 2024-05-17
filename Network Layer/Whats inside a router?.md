- **Input ports**:
	- terminates physical link at the router
	- performs link layer functions to interoperate with the link layer
	- lookup function to determine the output port
- **switching fabric**: connects router's input ports to output ports
- **output ports**: 
	- transmits packets to the link layer and physical layer
- **routing processor**: performs control pane functions. It executes routing protocols, maintains routing tables and computes forwarding table for router
- input ports, output ports, switching fabric all implemented in hardware
- **destination based forwarding, and generalized forwarding**

### Input port processing and destination port forwarding:
- **longest prefix matching rule**:
- look up time need to be incredibly fast
- DRAM and faster SRAM. TCAMs or Ternary Content Addressable Memories are used for lookup.
	- TCAM provided with a 32  bit IP essentially returns the forwarding table entry in constant time
- other than lookup the input port needs to:
	- process the physical and link layer
	- checksum, TTL, version number needs to be processed or updated
	- counters used for network management must be updated
### Switching:
- Switching via **shared memory**: processor memory does the work
- switching via **bus**: an input port transfers a packet directly to the output port via a shared bus.
	- all output ports get the packet, only the port that has the correct label will send the packet.
	- only one packet can go through the bus at a time, so speed is limited by the bandwidth of the bus.
	- enough for small local networks
- switching via an **interconnected network**: 
	- multiple packets can go from input port to output port at the same time
	- crossbar switch is **nonblocking**
		- packet going into output port will not be blocked unless there is a packet going to the same output port
		- if 2 packets from 2 different input ports and need to go to the same output port, one will wait at the input 
### Output port processing:
- includes scheduling, and dequeing packets for transmission, and performing the needed link layer and physical transmission functions
### **Where does queuing occur?**:
- the location and extent of queuing depends on traffic load, relative speed of the switching fabric and the line speed.
- when the queues grow large, the routers memory can be exhausted and packet loss can occur.
- **Input queueing**:
	- what happens when the switch fabric is not fast enough
	- **Head of line blocking ** (HOL):** can happen
	- when in the output buffer there are not enough memory, packets can be dropped. (**drop tail**)
		- it may be advantageous to drop the buffer before its full and provide a congestion signal to the sender
- **How much buffering can be provisioned in a port?**
	- larger buffers is not always better. It could mean longer queuing delays
	- long delay due to persistent buffering is known as **bufferbloat**
	- **Active Queuing Management** (AQM)
	- **Random Early Detection** (RED)

### Packet Scheduling:
- FCFS
- Priority Queuing
	- when packets arrive they are classified into priority classes
	- packets containing network information such as TCP/UDP port information are higher in priority than user traffit
	- real time voice over packets > priority than gmail type stuff
	- in a **non preemptive packet queuing** the transmission of the packet is not interrupted once it has begun
- A **work conserving queing** will never allow the link to be idle whenever there are packets queued for transmission
- 