
# Network Connectivity Investigation

## Objective

This investigation demonstrates how a computer reaches **google.com** by checking the local network configuration, resolving the domain name, testing network connectivity, and tracing the path packets take across the network.

---

## Tools Used

- Command Prompt
- `ipconfig`
- `nslookup`
- `ping`
- `tracert`

---

## Step 1: Check Network Configuration

### Command

```cmd
ipconfig
```

### Screenshot

![ipconfig](screenshots/ipconfig.png)

### Explanation

The `ipconfig` command displays the current network configuration of the computer.

From the output:

- IPv4 Address: **172.20.10.2**
- Subnet Mask: **255.255.255.240**
- Default Gateway: **172.20.10.1**

This confirms that the computer has a valid IP address and is connected to the network through its default gateway.

---

## Step 2: Resolve the Domain Name

### Command

```cmd
nslookup google.com
```

### Screenshot

![nslookup](screenshots/nslookup.png)

### Explanation

The `nslookup` command queries the DNS server to translate **google.com** into its IP address.

The output confirms that the DNS server successfully resolved the domain name, allowing the computer to locate Google's servers.

---

## Step 3: Test Connectivity

### Command

```cmd
ping google.com
```

### Screenshot

![ping](screenshots/ping.png)

### Explanation

The `ping` command sends ICMP Echo Request packets to the destination and waits for a reply.

The output shows:

- Replies received successfully
- No packet loss
- Stable response times

This confirms that the computer can communicate successfully with Google's server.

---

## Step 4: Trace the Route

### Command

```cmd
tracert google.com
```

### Screenshot

![tracert](screenshots/tracert.png)

### Explanation

The `tracert` command displays each network device (hop) that packets pass through before reaching the destination.

The trace begins with the local gateway, continues through several ISP routers, and ends at Google's server. A timeout on one hop is normal because some routers do not respond to traceroute requests.

---

## Conclusion

The investigation confirmed that the computer was properly connected to the network and could successfully communicate with Google's servers.

- The local network configuration was valid.
- DNS successfully resolved the domain name.
- The destination responded to ping requests without packet loss.
- Traceroute showed the path taken through the local gateway, ISP routers, and finally Google's network.

Overall, the network connection was functioning as expected.
