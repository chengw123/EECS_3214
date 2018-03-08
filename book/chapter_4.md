# Network Layer: Data Plane

-	network layer
	-	transport segment from sending to receiving host
	-	sending side: encapsulates segments into datagrams
	-	receiving side: delivers segments to transport layer
	-	router examines header fields in all IP datagrams
-	functions
	-	forwarding
	-	routing
-	data plane
	-	local, per-router function
	-	determines how datagram arriving on router input
	port is forwarded to router output port
	-	forwarding function
-	control plane
	-	network-wide logic
	-	determines how datagram is routed among routers
	along path from source to dest
	-	`traditional routing algorithms`
		-	implemented in routers
	-	`software-defined networking`
		-	implemented in servers
-	Per-router control plane 
	-	each and every router
	-	`logically centralized control plane`
-	network service model
	-	individual
		-	guaranteed delivery
		-	bounded guaranteed delivery
	-	a flow of datagrams
		-	in-order datagram delivery
		-	guaranteed minimum bandwidth to flow
		-	restrictions on changed in inter-packet spacing
##	Input port functions
-	line termination -> link layer protocol -> lookup, forwarding (queueing)
-> switch fabric
-	decentralized switching
	-	using header field values, lookup output port using 
	forwarding table in input port memory
	-	goal: complete input port processing at `line speed`
	-	queuing if datagrams arrive faster than forwarding rate
	into switch fabric
	-	destination-based forwarding
		-	forward based on dest IP address
-	longest prefix matching
	-	using longest address prefix that matches dest address
	-	performed using TCAM (Ternary Content Addressable Memories)
		-	content addressable:
			-	retrieve address in one clock cycle, regardless of table size
		-	Cisco Catalyst
##	Switching Fabrics
-	transfer packet from input buffer to appropriate output buffer
-	switching rate
	-	often measured as multiple of input/output line rate
	-	N inputs: switching rate N times line rate
	-	types:
		-	via memory
		-	via bus
		-	via crossbar
-	switching via memory
	-	packet copied into system's memory
	-	speed limited by memory bandwidth (2 bus crossing per datagram)
-	swiching via bus
	-	datagram from input to output via a shared bus
	-	`bus contention`
		-	switching speed limited by bus bandwidth
	-	32 Gbps bus is sufficient speed 
-	switching via interconnection network
	-	overcome bus bandwidth limitations
	-	initialy developed to connect processors to multiprocessors
	-	fragmenting datagram into fixed length cells, switch cells through
	the fabric
-	input port queuing
	-	fabric slower than than input ported combined -> queuing may 
	occur at input queues
		-	queuing delay and loss due to input buffer overflow
	-	HOL blocking ( head of the line)
		-	queued datagram at front prevents others in queue from moving 
		forward
##	Output ports
-	`buffering` required from fabric faster rate
	-	Datagram can be lost due to congestion, lack of buffers
-	`scheduling` datagrams
	-	priority scheduling - best performance, network neutrality
-	buffering when arrival rate via switch exceeds output line speed
-	queuing delay and loss due to output port buffer overflow
-	buffering:
	-	RTT * C / sqrt(N)
	-	with N flows, Round Trip Time times link capacity (bandwidth)
##	Scheduling mechanisms
-	scheduling: choose next packet to send on link
-	FIFO(first in first out) scheduling: like queue data structure
-	full queue:
	-	tail drop
	-	priority
	-	random
-	priority
	-	like priority queue
	-	ex: VoIP vs SMTP or IMAP
-	RR scheduling
	-	multuple classes
	-	Weight Fair Queuing (WFQ)
		-	Generalized Round Robin
##	IP datagram format
-	MTU = max transfer size
-	overhead = 20 bytes of TCP + 20 bytes of IP = 40 bytes + app layer overhead
##	IP addressing 
-	IP address: 32-bit identifer for host, router interface
-	interface: connection between host/router and physical link
	-	routers has multiple interfaces
	-	host has one 
-	subnets
	-	subnet part: high order bits
	-	host part: low order bits
	-	each isolated network from host is called a subnet
-	CIDR
	-	classless interdomain Routing
	-	subnet port of address of arbitrary length
	-	format 123.123.123.123/x, where x is the CIDR
##	DHCP
-	`dynamic host configuration protocol`
-	dynamically get address from server
-	goal
	-	allow host to dynamically obtain its IP address from server 
-	can return more than just allocated IP address on subnet
	-	default gateway
	-	name and IP address of local DNS server
	-	network mask (indicating network vs host portion of address)
-	encaped in UDP i.e. dumuxed to UDP
##	NAT
-	`network address translation`
-	all dataframs leaving local network have same single 
source NAT IP address, different source port numbers
-	motivation
	-	local network uses just one IP address
	-	can change addresses of devices in local network with notifying outside world
	-	can change ISP without changing addresses of devices in local network
	-	devices inside local net not explicitly addressable
-	changes both source addr & dest addr
-	other issues
	-	16-bit number field
		-	60000 maximum
	-	controversial
		-	routers should only process up to layer 3
		-	address shortage should be solved by IPv6
		-	violates end-to-end arguments
			-	must be taken into account by app designer
		-	traversal
## Ipv6
-	motivation:
	-	32-bit address space soon to be completely allocated
	-	header format helps speed processing
	-	facilitate QoS
-	format
	-	fixed-length 40 byte header (Ipv4 : 20 byte)
	-	no fragmentation allowed
		-	ICMP: "packet too big"
	-	priority -> identify priority among datagrams in flow
	-	flow label -> identify datagrams in same "flow"
	-	next header -> identify upper layer protocol for data
-	changes from Ipv4
	-	checksum
	-	options
	-	ICMPv6 -- new version of ICMP
		-	additional message types ex: "packets too big"
		-	multicast group management functions
- 	transition from Ipv4 to Ipv6
	-	not all routers can bu upgraded simultaneously
	-	tunneling
		-	Ipv6 datagram carried as payload in Ipv4 datagram among Ipv4 router






























