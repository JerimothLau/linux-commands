# linux-commands
linux daily commands

# Top 10 Linux Networking Commands

| Command | Description | Example |
|---------|-------------|---------|
| `ip` | Manage network interfaces, IP addresses, and routing | `ip addr show` |
| `ping` | Test network connectivity | `ping google.com` |
| `ss` | Display sockets and network connections | `ss -tulnp` |
| `traceroute` | Trace the route packets take | `traceroute google.com` |
| `dig` | Query DNS records | `dig example.com` |
| `curl` | Test HTTP/HTTPS services and APIs | `curl https://example.com` |
| `tcpdump` | Capture and analyze network traffic | `sudo tcpdump -i eth0` |
| `nc` (Netcat) | Test ports and transfer data | `nc -vz example.com 443` |
| `ip neigh` | Display the ARP/Neighbor table | `ip neigh show` |
| `ethtool` | View and configure Ethernet device settings | `sudo ethtool eth0` |

---

## 1. `ip`

The modern networking utility that replaces `ifconfig`, `route`, and `arp`.

### Examples

```bash
# Show IP addresses
ip addr

# Show routing table
ip route

# Show network interfaces
ip link

# Show neighbor (ARP) table
ip neigh

# Bring an interface up
sudo ip link set eth0 up

# Bring an interface down
sudo ip link set eth0 down

# Assign an IP address
sudo ip addr add 192.168.1.100/24 dev eth0
```

---

## 2. `ping`

Tests connectivity and measures latency to a remote host.

### Examples

```bash
# Ping a host
ping google.com

# Send only 4 packets
ping -c 4 8.8.8.8

# Set packet size
ping -s 1024 google.com
```

---

## 3. `ss`

Displays active sockets and listening ports. It is the modern replacement for `netstat`.

### Examples

```bash
# Show listening TCP/UDP ports
ss -tuln

# Show listening ports with processes
sudo ss -tulnp

# Show established TCP connections
ss -tan

# Show UDP sockets
ss -uan
```

---

## 4. `traceroute`

Shows each hop packets take to reach a destination.

### Examples

```bash
traceroute google.com

# Numeric output only
traceroute -n google.com

# Alternative command
tracepath google.com
```

---

## 5. `dig`

Performs DNS lookups and troubleshooting.

### Examples

```bash
# Lookup A record
dig example.com

# Query a specific DNS server
dig @8.8.8.8 example.com

# MX records
dig example.com MX

# NS records
dig example.com NS

# TXT records
dig example.com TXT
```

---

## 6. `curl`

Transfers data using various protocols, commonly HTTP and HTTPS.

### Examples

```bash
# Fetch a webpage
curl https://example.com

# Show response headers only
curl -I https://example.com

# Follow redirects
curl -L https://example.com

# Send a POST request
curl -X POST https://api.example.com

# Download a file
curl -O https://example.com/file.zip
```

---

## 7. `tcpdump`

Captures and analyzes network packets.

### Examples

```bash
# Capture packets
sudo tcpdump -i eth0

# Capture HTTP traffic
sudo tcpdump port 80

# Capture DNS traffic
sudo tcpdump port 53

# Save capture to a file
sudo tcpdump -w capture.pcap

# Read a capture file
tcpdump -r capture.pcap
```

---

## 8. `nc` (Netcat)

A versatile networking tool for testing, debugging, and transferring data.

### Examples

```bash
# Test if a port is open
nc -vz example.com 443

# Start a TCP listener
nc -l 9000

# Connect to a server
nc example.com 80

# Send a file
nc host 9000 < file.txt
```

---

## 9. `ip neigh`

Displays the ARP/Neighbor table.

### Examples

```bash
# Show all neighbors
ip neigh

# Show reachable neighbors
ip neigh show nud reachable

# Flush neighbor cache
sudo ip neigh flush all
```

---

## 10. `ethtool`

Displays and configures Ethernet interface settings.

### Examples

```bash
# Show interface information
ethtool eth0

# Show driver information
sudo ethtool -i eth0

# Show statistics
ethtool -S eth0

# Check link status
ethtool eth0 | grep "Link detected"
```

---


# Replace localhost with server01
sed -i 's/localhost/server01/g' config.txt
