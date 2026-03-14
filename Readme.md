Group 1 OSPF
![Group 1 network map](/images/ospf_network.jpeg)
Group 2 EIGRP
![Group 1 network map](/images/eigrp_network.jpeg)

Time to complete [~40 hours]

Network designed for Meta, Microsoft, Google, and AWS 

# IP 
* Google    - 10.0.0.0/19 (8190 useable hosts)
* Microsoft - 10.0.32.0/19 (8190 useable hosts)
* Meta      - 10.0.64.0/21 (2046 useable hosts)
* AWS       - 10.0.72.0/23 (510 useable hosts)

# VLAN
Vlans allows you to virtually segment traffic within a switch to prevent groups from being able to snoop on eachother.

* Google    - Vlan 10
* Microsoft - Vlan 20
* Meta      - Vlan 30
* AWS       - Vlan 40

# DHCP 

DHCP Servers allow for a user to connect to a network and have IP assigned to them. This allows for seemless connectivity and abstracts the user away from understanding Network fundamentals.

* Mumbai         - Google DHCP
* West-Coast     - Microsoft DHCP
* Starlink       - Meta DHCP 
* Sanfrancisco   - AWS DHCP 

# HSRP 
HSRP allows the network to have redundancy by allowing for multiple routers to be able to act as a gateway.

The West and East coast MLSs are set to be the Gateways for the companies

# IP NAT
Due to limited IPv4 addresses, NAT was developed to allow for internet users to scale a single IP address to multiple users. Here I use the 77.1.1.0/24 range to act as a pool for of public IPs for all companies.

# OSPF and EIGRP
OSPF and EIGRP are routing protocols used to direct traffic within a network. In this network there are 2 groups which implement these protocols using the same infrastrcuture. I used vrfs to imoplement these protocols on the same infrastructure.

# VRF
Vrfs all you to virtually split router to allow for security and flexibility implementing routing protocols. Vrfs accomplish this by creating seperate routing table for each vrf.
