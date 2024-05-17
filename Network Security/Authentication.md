### Digital Signatures:
- internet checksum:
	- produces fixed length digest of message 
	- is many to one
	- different messages can have same checksum

Public Key Certification Authorities:
- **certification authority (CA)** binds public key to particular entity, E
- when alice wants bob's public key:
	- get Bob's certificate 
	- apply CA's public key to Bob's certificate, get Bob's public key
- 