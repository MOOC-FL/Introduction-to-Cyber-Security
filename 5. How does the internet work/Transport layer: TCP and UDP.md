#### Transport layer: TCP and UDP
- IP lacks several key features making it directly unusable.
1- Firstly, IP does not distinguish between different applications at the same host. For example, if a user has an open SSH shell connection and downloads a web page through a browser, IP does not have means to direct the incoming data to a web browser instead of a shell.
2- Secondly, IP is stateless, meaning that each packet is processed individually. This means that while IP provides some protection against corrupted packets, it does not guarantee that the packets arrive in order. Moreover, packets can be duplicated. Finally, if a packet is lost for some reason, IP does not provide reliable mechanism to resend the packet.
> Transmission Control Protocol (TCP) solves these issues.
- TCP connection is between two agents: a server is waiting for a connection while the client initates the connection. Here the server could be a web server while the client is the web browser.
- TCP has a state: upon connection a client and a server undergo a handshake protocol where several packets are sent back and forth making sure that both parties are on the same page. Integrity of the data stream is maintained by counters on both sides, and sending an acknowledgment packet every time a data packet arrives. If the sender does not receive acknowledgment reply for a data packet within a certain amount of time, he will resubmit the packet.
- TCP also introduces a concept of a port: each connection has two ports, one for both sides. A port is an integer between 0 and 65535. A server typically waits for a new connection at a well-known port. Default ports for widely-used protocols are well-established and are typically small numbers, for example, HTTP uses port 80. A client also needs its own port. These ports are typically large numbers selected automatically by an operating system, based on what ports are available.
- 





