# Computer network and the internet

-	service description
	-	distrubuted applications
		-	multiple end systems
	-	end systems
		-	provide API
			-	for running data on another end systems
	-	protocols
## network edge
-	hosts
	-	= end system
	-	host apps such as a web program
	-	2 categories
		-	clients
			-	ex: desktop, PC, laptop
		-	servers
			-	ex: more powerful to store and distrobute web pages
-	data centers
	-	each one has many servers
-	home access
	-	DSL
		-	digital subscriber line 
		-	from telephone company
	-	optical fiber
	-	ethernet and wifi 
-	wide area wireless access 3G and LTE

## Physical media

-	guided media
	-	guided along a solid medium
		-	fider-optic twisted-pair
-	unguided media
		-	wireless LAN or a digital satallite channel
-	twisted-pair copper wire
	-	Unshielded twisted piar (UTP)
-	coaxial cable
-	fiber optics
-	terrestrial radio channels
-	satellite radio channels

## network core
-	packet switching
	-	packets
		-	source breaks a msg into a small chunks of data called packets
		-	travels through communication links and packet switches
	-	store-and-forward transmission
		-	packet switch must receive the entire packet first
	-	end-to-end delay:
		-	d = N * L/R
		-	rate L rate R N links
	-	queueing delay and packet loss
		-	output buffer ( output queue)
		-	waiting for other buffer causes delay
	-	forwarding tables and routing protocols
## circuit switching 
-	circuit switching and packet switching
	-	packet switching is not suitable for real-time services
	-	
-	multiplexing in circuit-switched networks
	-	FDM (frequency division multiplexing)
		-	frequency band to each connection for the duration of the connection 
		-	width of 4 KHz ( bandwidth)
	-	TDM (time division multiplexing)
		-	divided into frames of fixed duration 
		-	each frame is divided into a fixed number of time slots
-	ISP
	-	access ISP
		-	customer
	-	golbal transit ISP
		-	provider
	-	regional ISP
	-	tier-1 ISPs
	-	PoP (points of presence)
		-	a group of one or more routers in the network where customer ISPs can connect into the provider ISP
	-	any ISP can multi-home
		-	i.e. connect to 2 or more provider ISPs
	-	content provider network
		-	google
## delay, loss, throughput in packet-switched networks
-	delay
	-	nodal processing +
	-	queuing +
	-	transmission +
	-	propagation + 
	-	= total nodal delay
-	processing delay
	-	time required to examine the packet's header and determine where to direct the packet
-	queuing delay
	-	waits to be transimitted onto the link
-	transmission delay
	-	L/R
	-	L - length of packets
	-	R - tranmission rate from router to router
-	propagation delay
	-	in milliseconds
-	differences between transmission and propagation
	-	tranmission delay is the amount of time required for router to push out packet
	-	propagation delay is the time it takes a bit to propagate from router to next router.
-	traffic intensity
	-	La/R
	-	queue is capable of holding an infinite number of packets
-	packet loss
## End-to-End Delay
-	nodal delay
	-	delay at single router
-	Dend-to-end = N * nodal delay
-	traceroute
	-	3 times repeat
	-	3 * N packets
## Throughput 
-	instantaneous throughput
-	average throughput
	-	Rs < Rc
	-	Rc < Rs
		-	the router will not be able to forward bits 
		as quickly as it receives them.

## Protocol layers and service models
-	applicaiton layer
	-	HTTP, SMTP, FTP
-	transport layer
	-	TCP, UDP
		-	TCP breaks long msgs into shorter and provides a congestion control mechanism
		-	UDP provides a connectionless service to its applications
	-	segments (packet)
-	network layer
	-	datagrams (packet)
-	link layer
	-	frames (packet)
-	physical layer
	-	bits
-	OSI
-	encapsulation and de-encapsulation































`
