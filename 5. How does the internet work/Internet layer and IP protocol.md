#### Internet layer and IP protocol
- The key protocol at the network layer is Internet Protocol (IP). An IP packet consists of the payload and a header. A real-life analogy would be a letter: the header is the envelope while the payload is the contents of the letter.
- The protocol establishes several fundamental things.
- First, and most important, each device in the network is given an IP address. In IPv4 the address consists of 4 bytes (numbers ranging between 0—255). Partly due to bad management, IP addresses using only 4 bytes are (almost) run out, so a new protocol IPv6 was introduced that uses 32 bytes as address. Both protocols are used but IPv4 is still the dominant protocol as of 2020.

![]([https://example.com/image.jpg](https://github.com/MOOC-FL/Introduction-to-Cyber-Security/blob/main/5.%20How%20does%20the%20internet%20work/Structure%20of%20the%20IPv4%20header.%20Several%20key%20fields%20are%20highlighed.svg))
Structure of the IPv4 header. Several key fields are highlighed.

- IP protocol allows data packet fragmentation if the underlying layer has a limited packet size, and is smaller than the payload. That is, if the payload is larger than what the link layer can transmit in one packet, IP protocol will chop the packet in smaller fragments, and transmit them individually. A maximum size for a single IP packet is 65535 bytes of which 20 bytes are an IP header. Naive implementations of IP fragmentation allowed for exploits such as denial-of-service attacks.
- IP also provides a checksum to make sure that the payload has not been corrupted. Note that the goal of this checksum is to protect from non-malicious errors due to, for example noisy underlying communication channel. If the packet is modified by an attacker, it is trivial to compute a new valid checksum for that particular packet.

- When a device, either the end host or a router, notices a corrupted IP packet, it is dropped, and an error message is sent back.
- Note that IP protocol does not directly tell how to deliver a packet. The decision is done by an IP routing algorithm at the router. The main idea behind such algorithm is that a router studies the IP address and compares it to a routing table. The routing table can be viewed as a set of devices (routers or hosts) connected to the router, each device associated with an IP address range. If the target IP falls into a range, then the packet is submitted to the next router (or a host) associated with that range. The routing tables can be either static, that is, written by hand, or can be dynamic, using various protocols to keep themselves up to date.
- Internet routing is designed in such a way that if the most common (and optimal) communication channel is disrupted, a router will try to establish a new, less-than-ideal route. However, if all communication lines are disrupted there is nothing that can be done to restore the connection.

- IP header has a field named protocol, indicating the type of a payload being delivered. For example, a protocol may indicate that the payload is a TCP packet (we will discuss this protocol later), or packets related to route discovery algorithms.
- A notable example among these protocols is Internet Control Message Protocol (ICMP). This protocol is used for sending errors and communication network information. The most (in)famous use of ICMP is Ping, a network utility to see whether a specific host is reachable and how long does it take to reach it. A classic denial-of-service (DoS) attack, Ping Flood, involves in flooding the victim with many ping requests hoping to overwhelm the victim's computer. Another attack is Ping of Death which is actually an IP fragmentation attack with ICMP being used as the payload.

  > The IP protocol does not care about the specifics of the lower layers except when determining whether fragmentation is needed. In fact, IP could be used over pigeons.





