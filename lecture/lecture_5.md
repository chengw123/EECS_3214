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
	-
















