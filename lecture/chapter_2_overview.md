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
		-	no encryption if using UDP
		-	cleartext sent into socket if using UDP
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
# Persistent HTTP

-	non-persistent HTTP issues:
	-	at most one obj over TCP
		-	connection then closed
	-	downloading multiple objects require multiple connections
-	persistent HTTP
	-	multiple obj can be sent over TCP between client, server

## Non-persistent HTTP
-	RTT (round-trip delay time) 
	-	time for a small packet to travel from client to server and back
-	HTTP response time
	-	non-persistent HTTP response time = 2RTT + file transmission time

## Persistent HTTP
-	non-persistent HTTP issues:
	-	requires 2 RTTs per object 
	-	OS overhead for each TCP connection
	-	browsers often open parallel TCP coonections to 
	fetch reference obj
-	Default is persistent HTTP
	-	server leaves connection after sending response
	-	subsequent HTTP between same client/server
	-	client sends requests as soon as it encounters a 
-	referenced obj
	-	one `RTT` for all the referenced objects
	-	closes after a time-out interval

## HTTP response status
-	200 OK
	-	request succeeded
-	310 moved permanently
-	400 bad request
	-	not understood by server
-	404 Not Found
	-	not found in the server
-	505	HTTP Version Not Supported
-	304 Not Modified

## Cookies
-	identify users
-	components:
	-	cookie header line in HTTP response msg
	-	cookie header line in next HTTP response msg
	-	kept on user's host, managed by user's browser
	-	back-end database at website
-	use:
	-	authorization
	-	e-commerce
	-	recommendations
	-	user session states
-	protocol endpoints maintain state at sender/receiver
-	http messages carry state
## Uploading method
-	POST method
	-	web page includes form input
		-	input is uploaded to server in entity body
-	URL method
	-	GET method
		-	input is uploaded in URL field of request line
-	method types
	-	HTTP/1.0:
		-	get, post
		-	head
			-	asks server to leave object out of response
			-	quick response for debugging
	-	HTTP/2.0:
		-	get post head
		-	put
			-	uploads file in entity body to path specified in URL
		-	delete
			-	delete files specified in URL
## Web caches
-	Goal: satisfy client request without involving origin server
-	steps:
```Python
user sets browser: web accesses via cache

browser sends HTTP requests to cache

if object in cache
	cache return object 		# more efficient here.
else
	requests object from origin sever, then return
```
-	features:
	-	cache acts as both client and server
	-	installed by ISP
-	advantages:
	-	reduce response time
	-	reduce traffic
	-	internet dense with caches
## Domain name systen
-	people:
	-	SSN, name etc.
-	internet host, routers:
	-	IP address 
		-	used for addressing datagrams
	-	URL 
-	DNS
	-	distributed database
		-	implemented in many DNS servers
	-	application-layer protocol
		-	DNS resolve names(address/name translation)
-	services
	-	hostname
	-	host aliasing
		-	long name (canonical
		-	short name (alias
	-	mail server aliasing
	-	load distribution
		-	many IP addresses correspond to one name
		-	DNS sends entire list, rotating the ordering ( for optimization)
	-	replicated(duplicated) web servers:
		-	many IP address correspond to one name
		-	DNS server sends entire list, rotating order

## DNS: a distributed, hierarchical database
-	root DNS servers
	-	provide IP addresses of the TLD(top lv domain) servers
	-	over 400 root DNS worldwide
-	TLD servers:
	-	.com .org .net .edu
	-	provide IP addresses for authoritative servers
-	authoritative DNS servers:
	-	organization's own DNS servers
	-	maintained by organization
-	local DNS server
	-	not in the hierarchy
		-	each ISP has one
		-	default DNS 
-	when host makes DNS query, query is sent to its DNS server

## DNS name resolution
-	iterated query
-	recursive query
## caching , updating records
-	caches mapping
## DNS records
-	DNS: distributed databse storing resource records (RR)
	-	RR format (name, value, type, ttl)
	-	type=A
		-	name = hostname
		-	value = IP address
	-	type=NS
		-	name = domain
		-	value = hostname of authoritative name server for domain
	-	type=CNAME
		-	name = alias name for canonical name
		-	value = canonical name
	-	type=MX
		-	value is name of mailserver with name
## DNS messages
-	message header
	-	identification
		-	16 bit # for query, reply to query uses same #
	-	flags
## Inserting records into DNS
	-	
## Attacking DNS
-	DDoS Attacks
-	man-in-middle
-	DNS poisoning

# P2P applications

## Pure P2P architecture
-	ex: 
	-	file distribution (BitTorrent)
	-	streaming (Xunlei kankan)
	-	VoIP (skype)

## P2P file distribution: BitTorrent
-	tracker:
	-	tracks peers participating in torrent
-	torrent:
	-	groups of users exchanging chunks of a file
-	peers joining torrent:
	-	has no chunks, but will accumulate over time
	-	registers with tracker to get list of peers, connects to subset of peers


















