# Network Vulnerabilties

## Slowloris Attack on a Website
A Denial-of-Service attack tool that contniously sending patial HTTP requests to a web server to overwelm the server and eventually make it deny legitimate requests due to maximum connection limit is reached.   

Possible mitigations:
* Use hardware-based load balancers that do not accept the partial http requests
* Limit the connections to the Web server in a firewall - Limit the number of connections a single IP address is allowed to attempt
* Configure the timeout in the Web server configuration
* Increase the maximum number of clients the Web server will allow
* Place restrictions on the minimum transfer speed a connection is allowed
* Constrain the amount of time a client is permitted to stay connected.


Slowloris implementation in various languages [in github](https://github.com/search?q=slowloris) 
* Example Usage in [python implementation](https://github.com/gkbrk/slowloris): `> python3 slowloris.py <hostname>`


## ARP Poisoning (ARP Spoofing) via Ettercap
ARP Poisoning (ARP Spoofing) is a technique to gain MiTM (Man in the Middle) abilities by linking attacker system’s MAC address with the IP addresses of one or more legitimate systems on the network. That enables attackers to receive all the messages back and forth in the same broadcast domain.


## Sniffing via Ettercap
After ARP poisioning via Ettercap, the traffic can be sniffed (e.g. user credentials can be obtained) by defining Targets (one or bidirectional).


## DNS Spoofing via Ettercap
DNS spoofing is to divert a domain name to an incorrect IP address. Such a case is when an attacker wants to redirect legitimate traffic from a domain to the maliccious web site.
In ettercap `dns_spoof` plugin is used to conduct spoofing attack after arp poisoning.  


### Additional
To search for any Network Internet Cards(NICs) in promiscous mode, that is able to listen all traffic.
Usage: `> ettercap -TQP search_promisc`
