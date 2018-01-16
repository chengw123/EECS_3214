# Chapter 1
-	Intro to Internet
-	TCP/IP protocol 

## Roadmap
-	what is the Internet 
-	network edge
-	network core
-	delay, loss, throughput in networks
-	protocol layers, service models
## the network core
-	mesh of interconnected routers
-	packet-switching hosts
	-	store-and-forward
	-	queueing delay, loss
		-		
## functions
-	routing 
-	forwarding
## circuit switching 
-	FDM vs TDM
	-	frequency division multiplexing
		-	frequency vs time diagram
	-	time division multiplexing
		-	same
-	packet switching vs circuit switching 
	-	circuit-switching
		-	10 users
	-	packet-switching
		-	35 users, probability > 10 active at the same time
		-	prob = .0004 > 10 active (binominal distribution)
		-	prob = .9996 < 10 active 
	-	great for bursty data
	-	excessive congestion possible: packet delay and loss
		-	packet delay and loss
		-	circuit like behaviour
## network of networks
-	ISPs (Internet service provider)
## internet structure
-	point of presence (PoP)
	-	a group of routers connect to ISPs
-	multihome
	-	an ISP may connect 2 or more provider ISPs
-	Peering
	-	ISPs at same lv without going through upstream intermediates
-	IXP ( internet exchange provider)
-	content provider network
	-	eg Google
	-	private network that connects its data centers to Internet 
	-	bypassing tier-1 network
## Tier-1 ISP like Sprint
## packet delay
-	nodal processing delay
-	queueing delay
-	transmission delay
-	propagation delay
	-	d: length of link
	-	propagation speed (2 * 10^8 m/sec)
## queueing delay
-	La / R -- traffic intensity
-	R: Link bandwidth
-	L: packet length 
-	a: avg queueing delay













