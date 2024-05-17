### UDP
- "best effort"
- DNS, SNMP, HTTP/3 use UDP
- if reliable transfer needed over UDP:
	- add needed reliability at application layer
	- add congestion control at application layer
- UDP checksum (parity check i think) or CRC 
	- goal is to detect errors
- segment is the proper term for this layer
- length field to tell UDP how long the data is
- length includes UDP header length + data
### Internet Checksum:
- **Sender**
	- checksum: addition (one's complement sum) of segment content
	- checksum value put into UDP checksum field
- **Receiver**:
	- make sure that their calculation is the same as sender calculation
- checksum can catch some errors but not all 
### Pros UDP:
- no setup/handshaking (no RTT incurred)
- DNS and SNMP run on top of UDP
- can function when network service is compromised
- helps with reliability
- SNMP network monitoring protocol
- build additional functionality on top of UDP in application layer (e.g HTTP/3)
