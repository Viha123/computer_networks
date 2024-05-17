- provides datagram level encryption, authentication, integrity for both user traffice and control traffic
- transport mode:
	- only datagram payload is encrypted, authenticated
- tunnel mode:
	- entire datagram is encrypted authenticated
	- encrypted datagram encapsulated in new datagram with new IP header, tunneled to destination
2 IPSec protocols:
- Authentication Header (AH) Protocol
- **Encapsulation Security Protocol**
	- provides source authentication, data integrity and confidentiality. 
Security Associations
MAC in ESP auth field created with shared secret key
