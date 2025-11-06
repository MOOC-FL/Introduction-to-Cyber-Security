#### LAN and NAT
- Most of the internet users, home or at work, are not directly connected to the internet. Instead they are connected to a local area network (LAN). The local network is connected to the internet via a router. In home setting the router is often the WiFi station. Such station often provides other services such as

1. Firewall, blocking selectively incoming (and outgoing) connections.
2. DHCP server, dynamically assigning new IP addresses to new devices appearing in the LAN
3. NAT service, which maps local IP address, TCP/UDP port combinations to global IP address, ports. This is specifically handy,
if the internet service provider (ISP) provides only one IP address but a user wishes to have multiple devices connected.
NAT allows users to have local unique IP addresses that are mapped to the same global IP address. The mapping is done using either TCP or UDP ports.
