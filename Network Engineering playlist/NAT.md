#computerNetworks 
- Network Address Translation
- designed to solve limited number of ipv4 
- [[TCP vs UDP]]
- if 2 devices are in the subnet then they can find each other's MAC address's using ARP and can sent frames and packets to each other
- where does NAT comes into the picture?
	- a public ip address 44.12.1.9 (FFF) 8080 is trying to talk to private wifi
	- they both cannot talk to each other, the private ip needs a public representation
	- since they cannot find the MAC address, in the subnet.
	- if for some reason the device can't find the target machine in the subnet it calls, the default gateway
		- that is the router usually or a different machine
	- send mac address of router and forward the same packet to the router
		- the router understands the frame because it is addressed to it as the MAC address but not to it because of wrong IP address
		- the router does not allow because ip is private
	- ![[Pasted image 20240221220641.png]]
	- the router receives packet, router changes the source IP address to its **OWN**
	- BUT **how do you know what the previous machine's ip address was???**
		- this is where NAT comes into the picture
		- old IP address, router iop address, new ip address. this data goes into memory or disk (not sure)
- **NAT applications**
	- we don't run out of ipv4 but we have ipv6
	- port forwarding
		- instead of having root access to listen on port 80
			- anything less than 1024 you cannot listen to those ports, cuz they are root access ports
		- use NAT to port forward with iptables 
	- L4 load balancing
		- fast load balancing
		- creates virtual IP 
		- gets entry in the NAT table but it does not have a presence its just a record in a table

**WAN SIDE OF THE ROUTER**: the side that is connected to the world
**LAN side of the router**: private address space