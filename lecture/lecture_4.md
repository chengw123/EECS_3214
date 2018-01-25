# Application HTTP

## Creating a network app

-	structure of applications 
	-	differences
		-	client-server
			-	`permanent` IP addresses
			-	always on host for server, intermittent for clients
			-	clients do not communicate mutually.
		-	P2P
			-	`change` IP addresses
			-	`not` always on host

## Processes communicating

-	process:
	-	program running within a host
		-	within same host, 2 processes communicate using `inter-process communication` (defined by OS)
		-	processes in different hosts communicate by exchanging `messages` (like packets)
	-	client process
		-	process that initiates communication
	-	server process
		-	process that waits to be contacted.
-	aside:
	-	applications with `P2P` structure have client processes and server processes (but not server-client structure)
## application layer defines

-	types of messages exchanged
-	message syntax
-	message semantics
-	rules for when and how processes send & respond to messages
-	`open protocol`
	-	defined in RFCs ( remote function call)
	-	allows for interoperability (?)
	-	eg: HTTP, SMTP(simple mail transfer protocol)
-	`proprietary protocol`
	-	like skype
## transport service that app needs

-	data integrity
	-	reliable data transfer
-	timing
	-	low delay
-	throughput
	-	be effective
-	security
## internet transport protocol services

-	TCP service
	-	reliable transport
	-	flow control
	-	congestion control
	-	does not provide
		-	timing
		-	minimum throughput guarantee
		-	security
	-	connection-oriented
-	UDP service
	-	unreliable data transfer
	-	connectionless
	-	less reliable than TCP, but faster
-	Securing TCP
	-	TCP & UDP
		-	no encryption
		-	cleartext sent into socket
	-	SSL(transport layer securiy)
		-	encrypted TCP connection
		-	data integrity
		-	end-point authentication
		-	app layer
		-	socket API
			-	sent into socket to get encrypted
			-	encrypted passwd sent into TCP socket
-	HTTP request msg
	-	request, response
-	HTTP (hypertext transfer protocol)
	-	client/server model
		-	client:
			-	receive, receive and display web objects ( hostname + URL)
		-	server:
			-	sends objects in response to requests
	-	use TCP:
		-	initiates TCP connection, port 80
		-	server accepts TCP from client
		-	HTTP messages exchanged
		-	TCP connection closed
		-	HTTP is stateless
			-	maintains no info about past client requests. i.e. no records






		
		
































