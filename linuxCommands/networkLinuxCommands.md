> ## Network Configuration Tools

Essential utilities for managing network interfaces in Linux
systems.

### `ifconfig` command:

The ifconfig command is used in Unix-based operating systems to configure, manage, and display information about network interfaces.

By default, ifconfig only displays network interfaces that are in the UP state (active and in use).

```shell
ifconfig
```

- `Configure interface`: it means that you are able to change or adjust the settings of that particular network interface.

  ```shell
  # for example:
  sudo ifconfig eth0 192.168.1.10 netmask 255.255.255.0
  ```

- Enable interface:

  ```shell
  # First way: Using ifconfig to bring up eth0
  sudo ifconfig eth0 up

  # Second way: Using ifup to bring up eth0
  sudo ifup eth0
  ```

- Disable interface:

  ```shell
  # First way: Using ifconfig to bring down eth0
  sudo ifconfig eth0 down

  # Second way: Using ifdown to bring down eth0
  sudo ifdown eth0
  ```

### `route` command:

The route command in Unix-like operating systems is used for viewing and manipulating the IP routing table

- Displays routing table with IP addresses resolved to hostnames (if available).

  ```shell
  route
  ```

- Displays routing table with IP addresses shown in numeric form, without hostname.

  ```shell
  route -n
  ```

- Adding Routes: You can add specific routes to the routing table using route add.

  ```shell
  sudo route add -net 192.168.10.0 netmask 255.255.255.0 gw 192.168.1.1
  ```

- Deleting Routes: Routes can be removed from the routing table with route del.

  ```shell
  sudo route del -net 192.168.10.0 netmask 255.255.255.0
  ```

### `ip link show` command:

Lists network interfaces and their state(UP or DOWN).

### `ip addr show` command:

The ip addr show command is used to display detailed information about all network interfaces, including IP addresses assigned to them, along with additional configuration details such as MAC addresses and interface flags.

> ## Network Troubleshooting Tools

Essential utilities for diagnosing and resolving network
issues in Linux systems.

### `ping` command:

The ping command is used to test the reachability of a network host by sending ICMP Echo Request packets and waiting for ICMP Echo Reply packets in response.

```shell
ping google.com
```

- The -c flag in the ping command specifies the number of ICMP Echo Request packets to send.

  ```shell
  ping -c 5 google.com
  ```

- The -i flag in the ping command sets the interval between successive ICMP Echo Request packets sent to the target host.

  ```shell
  ping -i 2 google.com
  ```

### `traceroute` command:

The traceroute command is used to trace the route that packets take from your local system to a specified destination by showing the IP addresses of the routers along the path and the round-trip time to each router.

```shell
traceroute siteName
```

- The -m flag in the traceroute command sets the maximum TTL (Time-To-Live) value for the outgoing packets.

  ```shell
  traceroute -m 30 google.com
  ```

- The -I flag in the traceroute command specifies that the command should use ICMP Echo Request packets instead of the default UDP packets for tracing the route. This makes traceroute behave more like the ping command, which also uses ICMP Echo Requests.

  ```shell
  traceroute -I google.com
  ```

  **ICMP (Internet Control Message Protocol) is primarily used for network diagnostics and error reporting.**

### `/etc/services`

The `/etc/services` file contains a list of network services and their associated port numbers along with the protocol they use (TCP or UDP).

```shell
# for example:
sudo cat /etc/services  | grep "http"
# http            80/tcp          www             # WorldWideWeb HTTP
# https           443/tcp                         # http protocol over TLS/SSL
# http-alt        8080/tcp        webcache        # WWW caching service
```

### `netstat` command:

Displays network connections, routing tables, interface statistics, and more.

- The netstat -a command shows the listening and non-listening sockets for network connections

  ```shell
  netstat -a
  ```

- The -t flag shows only tcp connections.

  ```shell
  netstat -t
  ```

### `dig` command:

The dig (Domain Information Groper) command is a network administration tool used for querying DNS (Domain Name System) name servers. It is used to perform DNS lookups and troubleshoot DNS-related issues.

```shell
dig example.com
```

### `nslookup` command:

The nslookup command is a network administration tool used for querying the Domain Name System (DNS) to obtain domain name or IP address mapping information

```shell
nslookup example.com
```
