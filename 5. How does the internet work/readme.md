#### How does the internet work
- Next, we are going to discuss major protocols stipulating the communication between the devices connected to the Internet.
##### Internet is like an onion
- Internet has layers. Different protocols that are responsible for communication can be grouped in 4 layers.
  1. Link layer
  2. Internet/network layer
  3. Transport layer
  4. Application layer
- Protocols at the link layer are responsible for direct communication between two entities over the same link, for example, a protocol responsible communication between a laptop and a WiFi-router establishes the frequency, as well as how bits are transferred over that frequency.
- On the other extreme, the protocols in the application layer establish common language between two applications sharing information, for example, the HTTP protocol describes how a web browser should request information from a web server.
- Note that the upper layers do not care how the lower layers are implemented as long as certain services are provided by the lower layers: HTTP does not care whether the connection is over wireless, RJ-45 cable, or a smartphone, or a combination of many. Similarly, the lower layers do not care (at least in theory) about the payload of the application layer.
> Our primary interest for now is the internet layer and the transport layer.
