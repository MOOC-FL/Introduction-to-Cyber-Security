A **DDoS attack** (Distributed Denial-of-Service attack) is a malicious attempt to disrupt the normal traffic of a targeted server, service, or network by overwhelming it with a flood of Internet traffic from multiple sources.

### How it Works

1.  **Botnet Creation:** An attacker gains control over a large number of internet-connected devices (like computers, IoT devices, servers) by infecting them with malware. This group of compromised machines is called a **"botnet."**

2.  **Attack Launch:** The attacker sends a command to the botnet. All the devices in the botnet then simultaneously send a massive volume of requests to the target's IP address.

3.  **Overwhelming the Target:** The target server or network becomes overwhelmed by the sheer number of incoming messages. This consumes all available bandwidth, processing power, or memory, causing a **"denial-of-service"** for legitimate users. The target becomes extremely slow or completely unreachable.

### Key Difference from DoS

*   **DoS (Denial-of-Service):** Comes from a **single** source or a small number of sources.
*   **DDoS (Distributed Denial-of-Service):** Comes from **many distributed sources** (a botnet), making it much harder to block and much more powerful.

### Common Types of DDoS Attacks

*   **Volumetric Attacks:** The most common type. The goal is to saturate the target's bandwidth. Examples include UDP floods and ICMP (Ping) floods.
*   **Protocol Attacks:** These consume the actual processing resources of servers or intermediate communication equipment (like firewalls and load balancers). A common example is the **SYN flood**.
*   **Application Layer Attacks:** These are more sophisticated and target specific web applications (like a login page or a search function). The goal is to crash the web server with a seemingly low volume of traffic that is computationally expensive to handle. An example is an **HTTP flood**.

### Why Are They Carried Out?

*   **Extortion:** Demanding a ransom to stop the attack.
*   **Competitive Sabotage:** Disrupting a competitor's online services.
*   **Hacktivism:** As a form of protest.
*   **Cyber Warfare:** To disrupt a country's critical infrastructure.
*   **A Smokescreen:** To distract security teams while another type of attack (like data theft) is happening.

### How to Mitigate DDoS Attacks

*   **DDoS Mitigation Services:** Use specialized services (like Cloudflare, AWS Shield, Akamai) that can absorb and filter out malicious traffic before it reaches your server.
*   **Rate Limiting:** Restricting the number of requests a user can send to a server in a given time frame.
*   **Web Application Firewalls (WAF):** Can help filter out malicious application-layer traffic.
*   **Network Monitoring:** Continuously monitoring traffic to identify unusual patterns early.
