# Transport Layer

## goals
-	multiplexing, demultiplexing
-	reliable data transfer
-	flow control
-	congestion control
-	UDP : connectionless transport
-	TCP : connection-oriented reliable transport
-	TCP congestion control
-	TCP flow control

## Transport services and protocols
-	provide `logical coomunication` between application processes running on different hosts
-	transport protocols
	-	sending side
		-	breaks messages into segments
		-	pass to network layer
	-	receiving side
		-	reassembles segments to messages
		-	pass to application layer
-	transport vs network
	-	network layer:
		-	logical coomunication between `hosts`
	-	transport layer:
		-	logical coomunication between `processes`
		-	relies on , enhances, network layer services
-	TCP
	-	reliable, in order delivery
		-	congestion control
		-	flow control
		-	connection setup
-	UDP
	-	unreliable, unordered delivery
-	services not available 
	-	delay guarantees 
	-	bandwidth guarantees
## Multiplexing and demultiplexing
-	Port: external end-point at a node
-	Socket:	internal end-point of local inter-process coomunication
-	socket address = IP address + port
	-	ex: berkeley socket
-	Internet socket is characterized by at least
	-	socket address
	-	protocol (TCP, UDP)
		-	TCP port 1234 and UDP port 1234 are distinct sockets
-	`multiplexing` at sender
	-	handle data from multiple sockets
	-	add transport header
-	`demultiplexing` at receiver
	-	use header info to deliver segments to correct socket
	-	host receives IP datagrams
		-	each datagram has 
			-	source IP address
			-	destination IP address
			-	carries one transport-layer segment
		-	each segment has
			-	source port number
			-	destination port number
	-	host uses IP addresses and port numbers to direct segment to socket
	-	`connectionless demultiplexing`
		-	when host receives UDP segment
			-	checks destination port # in segment
			-	directs UDP segment to socket with that port #
			-	IP datagrams with same destination port # but different source IP addresses or source port numbers will be directed to same socket at dest
	-	`connection-oriented demultiplexing`
		-	TCP socket identified by
			-	source IP address
			-	source port number
			-	dest IP address
			-	dest port number
		-	receiver uses all 4 values for directing
		-	server host may support simultaneous TCP sockets
			-	each one identified its own 4-tuple
		-	web servers have different sockets for each connecting client
			-	non-persistent HTTP have different socket for each request
## UDP: User Datagram Protocol
-	UDP segments may be
	-	lost
	-	delivered out-of-order to app
-	uses:
	-	streaming multimedia apps
	-	DNS
	-	SNMP
-	reliable transfer in UDP
	-	add reliability at application layer
	-	application error-recovery
-	UDP: 
	-	no connection establishment
	-	no connection state 
	-	small header size (8 bytes)
	-	no congestion control
-	checksum
	-	detect errors
	-	sender
		-	treat segment contents
	









































