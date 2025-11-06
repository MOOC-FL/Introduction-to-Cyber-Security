The `ping` command on Debian is used to test network connectivity between your system and another host. Here's how to use it:

## Basic Ping Commands

**Test connectivity to a host:**
```bash
ping google.com
ping 8.8.8.8
```

**Stop after specific count:**
```bash
ping -c 4 google.com
```

**Specify interval between pings:**
```bash
ping -i 2 google.com  # 2 seconds between pings
```

## Common Ping Options

```bash
# Count of packets to send
ping -c 5 google.com

# Timeout in seconds
ping -W 3 google.com

# Specify source interface
ping -I eth0 google.com

# Flood ping (for stress testing)
ping -f google.com

# Set packet size
ping -s 1000 google.com

# Continuous ping (until Ctrl+C)
ping google.com
```

## Useful Examples

**Quick connectivity test:**
```bash
ping -c 3 -W 2 google.com
```

**Test with specific packet size:**
```bash
ping -s 1472 -c 4 google.com
```

**Check if a local network device is reachable:**
```bash
ping -c 3 192.168.1.1
```

## Understanding Ping Output

```
PING google.com (142.251.42.206) 56(84) bytes of data.
64 bytes from 142.251.42.206: icmp_seq=1 ttl=117 time=12.3 ms
64 bytes from 142.251.42.206: icmp_seq=2 ttl=117 time=11.8 ms
64 bytes from 142.251.42.206: icmp_seq=3 ttl=117 time=12.1 ms

--- google.com ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2003ms
rtt min/avg/max/mdev = 11.879/12.112/12.389/0.207 ms
```

## Troubleshooting

**If ping is not installed:**
```bash
sudo apt update
sudo apt install iputils-ping
```

**Permission denied error:**
```bash
# You might need to run with sudo in some cases
sudo ping google.com
```

**Test local network interface:**
```bash
ping -c 3 127.0.0.1  # Loopback test
```

Ping is one of the most fundamental network troubleshooting tools - it helps verify basic network connectivity and measure latency!
