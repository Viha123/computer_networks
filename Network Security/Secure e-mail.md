**alice wants to send confidential e-mail, m, to Bob:**
- generates random symmetric private key, Ks
- encryptes message with Ks (for efficiency)
- also encrypts Ks with Bob's public key
- sends both Ks(m) and K+B(KS) to Bob
Bob:
- uses his private key to decrypt and recover Ks
- uses Ks to decrypt Ks(m) to recover m
**alice wants to send m to Bob, with message integrity, authentication**:
- alice digitally signs hash of her message with her private key providing integrity and authentication
- sends both message (in the clear) and digital signature
**alice sends m to Bob, with confidentiality, message integrity, authentication**:
- alice does the authentication stuff and then does the confidential stuff so uses 3 keys: her private key, Bob's public key, new symmetric key. 

