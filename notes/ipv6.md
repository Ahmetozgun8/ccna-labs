\# ipv6 notes



day 31 notes from jeremy's it lab



\## basics

\- 128 bits, written in hex

\- 8 groups x 4 hex digits, separated by :

\- 1 hex digit = 4 bits -> 1 group = 16 bits

\- subnets are usually /64 (first 4 groups network, last 4 host)



\## shortening

\- drop leading zeros in a group: 0db8 -> db8

&#x20; (only leading! 0800 -> 800, not 8)

\- replace consecutive all-zero groups with ::

&#x20; only once per address, use it on the longest zero block



2001:0db8:0000:0000:0000:0000:0080:34bd -> 2001:db8::80:34bd



\## finding the prefix

keep prefix/4 hex digits, zero the rest, then shorten

2001:0db8:8b00:0001:0000:0000:0000:0001/64 -> 2001:db8:8b00:1::/64



\## config

&#x20;   ipv6 unicast-routing

&#x20;   int g0/0

&#x20;    ipv6 address 2001:db8:0:0::1/64

&#x20;    no shut

&#x20;   show ipv6 interface brief



\## link-local

fe80:: addresses, auto assigned on every ipv6 interface

only used on the local link, routers dont forward them

