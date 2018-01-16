# TCP/IP protocol suite

-	bandwidth = max capacity >= throughput 
-	throughput is realisitic value 
	- include protocol, data loss, latency
-	link capacity Rs = 10 Mbps, Rc = 1 Mbps (smaller due to latency)
	-	the higher the bandwidth, the higher the link capacity
	-	precisely speaking, bandwidth's units should be Hz, but bps is also correct.
-	1 Mhz -- downstream(BW refers to this part.) -- upstream -- 4 KHz --- O Hz

## internet protocol stack
-	applicaiton:
	-	FTP, SMTP, HTTP
-	transport:
	-	TCP, UDP
	-	TCP
		-	flow control
		-	congestion control
		-	help with reliability 
	-	ex: 
		-	file download
		-	voice application
-	network:
	-	ip, routing network
-	link: (data link)
	-	ethernet, PPP (point to point), wifi
	-	data transfer,
-	physical:
	-	bits " on the wire "
## OSI and TCP/IP model
-	OSI
	-	open system interconnection
	-	developed by ISO
- 	TCP/IP
	- 	encapsulation
	-	addressing
		-	port number ( access point number aka SAP)
	-	MAC address
		-	medium access control
	-	NIC address
		-	network interface card
-	Ip addresses
	-	each host is identified by Ip
	-	2 parts:
		-	network ID
		-	host ID
	-	Ip address identifies the host interface rather than the host itself
		-	ex: one router as a host has several ip addresses
-	physical addresses
	-	








