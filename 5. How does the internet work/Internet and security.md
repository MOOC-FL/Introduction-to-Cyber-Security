- Neither TCP nor IP protocol has any built-in security. This means, unless other measures are taken, traffic data can be intercepted or, worse, modified.
This is known as a man-in-the-middle attack, and modifying traffic can extremely sophisticated, for example, injecting (java script) code to a web browser when a user visits 3rd party websites.
- Data encryption can be done in a link layer, for example, WiFi can use WPA2 to encrypt its traffic. Similarly, data over cellular connection is encrypted. However, Ethernet (common protocol for cable-based local area networks) does not have any protection. Moreover, link layer encryption does not guarantee that the data will stay encrypted all the way to the host, if the underlying medium is changed during the transmission.
- For this reason, encryption is typically done in an application layer, with secure protocols replacing plain-text protocols. Examples include:
1. SSH over telnet for remote shell connection.
2. HTTPS over HTTP for communicating with a web server
3. SFTP over FTP for transmitting files
- The protocols establish a secure channel between two devices so that sensitive data cannot be observed. However, what can be observed is the address and the port, that is, a man-in-the-middle knows that the user has contacted the server, and he probably can guess the requested service based on the port, but the actual payload cannot be observed.
- It is possible to use the encryption protocol (known as TLS) used by HTTPS to encode normal IP traffic. Here, the user connects to a special server and establishes a secure channel. Using this channel the user sends IP data packets. The server then decrypts the stream, and forwards the packets to the address specified in the packets. The server also modifies the TCP/IP headers (similar to NAT) so that it seems that the connection is coming from the server. This also allows for a user to receive replies, as the server will forward back any incoming reply back to the user over the secure channel.
- This is essentially a version of Virtual Private Network (VPN). Note that we are wrapping an IP packet in a TLS stream, which in turns uses TCP, which again uses IP. Especially, having TCP protocol may lead to performance issues, and because of this IP Security (IPSec) is more common for VPN. IPSec data transmission protocols are implemented directly over IP (similar to TCP or ICMP) and are considered to be in network layer. Because TCP protocol is not used between the native IP packets and the encrypted payload, the latency issues are significantly smaller.
- Note that the payload is decrypted at the end point of VPN before it is forwarded to its real target. Since the IP address is also modified, an external party cannot deduce the user identity based on the IP information. However, any sensitive information that is not encrypted separately in the payload (such as passwords sent over plain HTTP) can be read after VPN.





