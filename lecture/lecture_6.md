# DNS server

-	TLD(top-level domain) servers:
	-	ex: uk, .co.jp
-	authoritative DNS server:
	-	organization's own DNS server
	-	maintained by organization
-	local DNS server
	-	each ISP has a default DNS server
	-	acts as a cache
-	resolution example (slides)

## DNS format

-	RR format (name, value, type, ttl)
-	type=a
```
Server:		130.63.10.18
Address:	130.63.10.18#53

Non-authoritative answer:
Name:	google.ca
Address: 172.217.2.99

Server:		130.63.10.18
Address:	130.63.10.18#53

Non-authoritative answer:
google.ca	mail exchanger = 50 alt4.aspmx.l.google.com.
```
-	type=ns
```
Server:		130.63.10.18
Address:	130.63.10.18#53

Non-authoritative answer:
google.ca	nameserver = ns1.google.com.
google.ca	nameserver = ns3.google.com.
google.ca	nameserver = ns2.google.com.
google.ca	nameserver = ns4.google.com.

Authoritative answers can be found from:
ns4.google.com	internet address = 216.239.38.10	# IPV4
ns1.google.com	internet address = 216.239.32.10
ns3.google.com	internet address = 216.239.36.10
ns2.google.com	internet address = 216.239.34.10
ns4.google.com	has AAAA address 2001:4860:4802:38::a	# IPV6
ns1.google.com	has AAAA address 2001:4860:4802:32::a
ns3.google.com	has AAAA address 2001:4860:4802:36::a
ns2.google.com	has AAAA address 2001:4860:4802:34::a
```
-	type=mx
```
google.ca	mail exchanger = 40 alt3.aspmx.l.google.com.
google.ca	mail exchanger = 20 alt1.aspmx.l.google.com.
google.ca	mail exchanger = 10 aspmx.l.google.com.
google.ca	mail exchanger = 30 alt2.aspmx.l.google.com.

Authoritative answers can be found from:
google.ca	nameserver = ns1.google.com.
google.ca	nameserver = ns2.google.com.
google.ca	nameserver = ns4.google.com.
google.ca	nameserver = ns3.google.com.
ns4.google.com	internet address = 216.239.38.10
ns1.google.com	internet address = 216.239.32.10
ns3.google.com	internet address = 216.239.36.10
ns2.google.com	internet address = 216.239.34.10
ns4.google.com	has AAAA address 2001:4860:4802:38::a
ns1.google.com	has AAAA address 2001:4860:4802:32::a
ns3.google.com	has AAAA address 2001:4860:4802:36::a
ns2.google.com	has AAAA address 2001:4860:4802:34::a
```
