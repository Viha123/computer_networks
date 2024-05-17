### Desirable Properties:
- **Confidentiality**
- **Message Integrity**
- **End-point authentication.**
- **Operational security.**
## Principles of Cryptography:
- **Symmetric key system**:
	- Keya(message) -> Bob:
	- KeyB(Keya(message)) = message
- **public key systems**:
	- public key, and private key to each individual associated.

Advanced Encryption Standard:
- brute force takes 149 trillion years

### Symmetric Key Cryptography:
- need Kb+() and Kb-() such that Kb+(Kb-(m)) = m
- given public key it should be impossible to compute private key

### RSA: Rivest, Shamir, Adelson Algorithm:
- message is just a bit pattern. 
- creating a public/private key pair:
	1. Choose 2 prime numbers, p, q (1024 bits each)
	2. compute n = pq, z = (p-1)(q-1)
	3. choose e < n where e has no common factors with z. e and z are relatively prime
	4. choose d where ed-1 is exactly divisible by z. ed mod z = 1
	5. public key is (n, e)
	6. private key is (n,d)
- to encrypt message m < n:
	- c = m^e mod(n)
- to decrypt message:
	- m = c^d mod(n)
### RSA in practice using session keys:
- exponentiation in RSA is computationally intensive
- DES is at least 100 times faster than RSA
- use public key crypto to establish secure connection, then establish second key - symmetric session key - for encrypting data
- session key, Ks
	- use RSA to exchange a symmetric session key
	- once both have Ks they use symmetric key cryptogrpahy
- 