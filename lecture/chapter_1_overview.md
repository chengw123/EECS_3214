#Introduction 

## view 
-	global ISP (Internet service provide)
	-	regional ISP
		-	home network
		-	insititutional network
	-	mobile network
-	hosts = end systems
-	tranmission rate: bandwidth
-	packet switches: forward packets
	-	routers and switches
-	protocols: control sending, receiving messages
-	Internet standards
	-	RFC: request for comments
	-	IETF: Internet Engineering Task Force
## Service view
-	infrastructure
	-	Web. VoIP, email
-	protocols
	-	define format
	-	order of messages 
	-	actions taken on messages

## network structure
-	network edge:
	-	hosts: clients and servers
	-	servers often in data centers
-	access networks, physical media
-	network core
	-	interconnected routers
	-	network of networks
-	dedicated line : specific for one app
	-	vs shared

## Access network
-	user network that connects subscribers to service provider
-	DSL(digital subscriber line)
	-	DSLAM
		-	DSL access multiplexer
		-	`data/voice` over DSL phone line goes to Internet
	-	transimission rate 
		-	upload < 2.5 Mbps
		-	download < 24 Mbps
-	cable network
	-	technique:
		-	FDM (frequency division multiplexing)
			-	different channels transmitted in different frequency bands
	-	HFC: hybrid fiber coax
		-	30 Mbps download 2 Mbps upload
	-	homes share access network to cable headend (like control center)	
-	home network
	-	from home to headend
-	Enterprise access network (Ethernet)
	-	connect insititutional deivices to ISP
-	Wireless access networks ( WAN)
	-	wireless LANS (local area network)
		-	WiFi
	-	wide-area wireless access
		-	3G, 4G, LTE
## Hosts
-	transmission delay
	-	L (bits) / R (bits/sec)
	-	tranmission rate R
	-	between end-systems
## physical media
-	bit
	-	propagates between transmitter/receiver pairs
-	physical link
	-	lies between transmitter/receiver
-	guided media
	-	propagate in solid media like cooper fiber coax
-	unguided media
	-	radio
-	twisted pair
	-	2 copper wires
-	coaxial vs fiber
	-	coaxial
		-	2 copper
	-	fiber optic
		-	carrying light
		-	high speed, low error
-	radio
	-	microwave
	-	LAN
	-	wide-area
	-	satellite
## network core
-	`packet switching`
	-	hosts break application-layer into packets
		-	forward packets from one router to next
		-	each packet tranmitted at full link capacity
	-	takes L/R seconds to transmit
	-	store and forward
		-	entire packet arrived and forward
	-	end-end delay
		-	2 L/R (round trip time)
-	`queueing delay and loss`
	-	arrival rate to link exceeds tranmission rate
		-	packets will queue ( wait)
		-	will dropped if memory fills up
	-	routing
		-	determine route of packets
	-	forwarding 
		-	move packets from input to output
-	`circuit switching`
	-	end-end resources
	-	for traditional telephone network
-	FDM vs TDM
	-	frequency division multiplexing
	-	time division multiplexing 
	-	for wireless
		-	FDMA vs TDMA
		-	MA stands for multiple access
-	packet switching vs circuit switching
	-	packet switching 
		-	allows more users
		-	great for bursty data
		-	simpler, no call setup
		-	cons : congestion 
## Internet structure: network of networks
-	end systems connect to Internet via access ISPs
-	access ISPs must be interconnected
-	complex
-	PoP ( Point of presence)
-	Multi-home ( 1 ISP connect 2 more ISPs)
-	Peering ( ISPs connect directly)
-	IXP( Internet Exchange Point)
-	Content provider network ( Google)
-	Tier-1 ISP -(IXP)--> access ISP
-	queueing delay 
	-	La/R
## Packet loss
-	packet arriving to full queue dropped
-	may be retransmitted
-	throughput 
-	per connection throughput
	-	min( Rc , Rs, R/ N) 
	-	Rc 	client
	-	Rs  server
	-	N	number of connections
	- 	bottleneck link
## layering
-	dealing with complex systems

## TCP/IP
-	application
-	transport
-	network
-	data link
-	physical

## ISO
-	application
-	presentation
-	session
-	rest of layer is same as TCP/IP


































