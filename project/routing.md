# Network Connectivity Investigation

## Objective

The aim of this investigation was to check how my computer connects to **google.com** using basic Windows networking commands.

---

## Tools Used

- Command Prompt
- ipconfig
- nslookup
- ping
- tracert

---

## 1. Check the Network Configuration

### Command

```cmd
ipconfig
```

### Screenshot

![ipconfig](screenshots/ipconfig.png)

### What I observed

The command displayed the IP configuration of my computer.

- IPv4 Address: 172.20.10.2
- Subnet Mask: 255.255.255.240
- Default Gateway: 172.20.10.1

This shows that my PC has a valid IP address and is connected to the network through the default gateway.

---

## 2. Resolve the Domain Name

### Command

```cmd
nslookup google.com
```

### Screenshot

![nslookup](screenshots/nslookup.png)

### What I observed

The DNS server successfully translated **google.com** into an IP address.

This confirms that DNS resolution is working properly.

---

## 3. Test Connectivity

### Command

```cmd
ping google.com
```

### Screenshot

![ping](screenshots/ping.png)

### What I observed

The command sent four packets to Google's server and received replies successfully.

- 4 packets sent
- 4 packets received
- 0% packet loss

This shows that my computer can reach Google's server.

---

## 4. Trace the Route

### Command

```cmd
tracert google.com
```

### Screenshot

![tracert](screenshots/tracert.png)

### What I observed

The route started from my local gateway and passed through several routers before reaching Google's server.

One hop timed out, which is normal because some routers do not reply to traceroute requests.

---

## Conclusion

The investigation showed that my computer is connected to the network correctly. DNS resolved the website successfully, the server responded to ping requests, and traceroute showed the path taken to reach Google's network.
Overall, the network connection was functioning as expected.
