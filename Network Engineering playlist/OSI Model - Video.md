#computerNetworks
- **Layer 7: application** (GET/ sends HTTP header cookies, content type etc)
- **Layer 6: Presentation** (if using HTTPS) (encrypt if necessary)
- **Layer 5:** Establish session tag it
	- data needs to be tagged with a session
- **Layer 4: Transport Layer**- bunch of bits and split into **segments**
	- tagged with port number
	- sequence is embedded into the **segments**
- **Layer 3: Network Layer**
	- doesn't know port, only knows a segment and attaches IP address + src IP address
	- called a packet
- **Layer 2: Data Link**
	- Each packet is passed down 
	- touches physical medium
	- adds the target MAC address for **frames**
	- have basic error detection
	- sometimes you don't know the mac address
		- here is where **ARP** comes into the picture
			- takes IP and reverse engineers it into a MAC address
- **Layer 1: Physical:**
	- bits
Everyone in the wifi network gets the data, if data not encrypted then malicious users can easily see what is in the data

