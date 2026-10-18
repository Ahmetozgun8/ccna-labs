Subnetting Cheat Sheet



Concepts

\- Prefix (/26): number of network bits from the left; larger prefix = smaller network

\- Network address: name of the network, used in routing tables (not assignable)

\- Broadcast address: packets sent here reach every host in the subnet (not assignable)

\- First host: network + 1

\- Last host: broadcast - 1

\- Block size: total addresses in a subnet; subnets start at multiples of it

\- FLSM: all subnets same size / \*\*VLSM:\*\* each subnet sized to its needs



&#x20;Formulas

&#x20;Host bits (n) = 32 - prefix 

&#x20;Total addresses  = 2^n 

&#x20;Usable hosts = 2^n - 2 

&#x20;Number of subnets = 2^x (x = borrowed bits) 

&#x20;Block size = 256 - mask value in the interesting octet 



&#x20;Mask Table

| Prefix | Mask (last octet) | Block | Usable |

&#x20;/25 | 128 | 128 | 126 

&#x20;/26 | 192 | 64 | 62 

&#x20;/27 | 224 | 32 | 30 

&#x20;/28 | 240 | 16 | 14 

&#x20;/29 | 248 | 8 | 6 

&#x20;/30 | 252 | 4 | 2 



Same values apply to the 3rd octet (/17-/24) and 2nd octet (/9-/16).



&#x20;Key Notes

\- A subnet always starts at a multiple of its block size

\- Octets after the interesting octet are 0 in the network address, 255 in broadcast

\- VLSM: always assign from largest to smallest subnet

\- /30 and /31 for point-to-point links, /32 for a single host

