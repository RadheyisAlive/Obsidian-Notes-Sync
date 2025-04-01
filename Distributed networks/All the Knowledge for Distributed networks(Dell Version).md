
## 🔌 **What is DHCPv4?** (7.1.1)

**DHCPv4** automatically assigns:

- IPv4 address
    
- Subnet mask
    
- Default gateway
    
- DNS server ...to devices (like computers, phones, printers) when they join the network.
    

### 🧠 Why is DHCPv4 useful?

- Saves time for network admins (no manual IP setup).
    
- Especially useful in networks with **many clients** (like offices or homes).
    

### 🚀 Where does DHCP run?

- On a **dedicated DHCP server**, or
    
- On a **router** (like in small networks – Cisco routers can do it).
    

---

## 🔁 **How DHCPv4 Works – Basic Idea** (7.1.2)

- A **client (PC)** asks the **DHCP server** for an IP.
    
- The server **leases** an IP from a pool (like a hotel renting rooms).
    
- The lease lasts for a set time (e.g., 24 hours or a week).
    
- When the lease ends, the client either:
    
    - Renews it (if it's still on the network), or
        
    - Releases it (if it left the network).
        

---

## 📦 **Steps to Get an IP – 4-Step Process** (7.1.3)

When your device joins the network, it does this:

### 1️⃣ DHCPDISCOVER

- Sent by the **client**.
    
- **Broadcast** message: “Hey! Is there any DHCP server out there?”
    

### 2️⃣ DHCPOFFER

- Sent by **DHCP server** in response.
    
- “Yes! Here's an IP you can use, plus your gateway, DNS, etc.”
    

### 3️⃣ DHCPREQUEST

- Sent by **client**.
    
- “Thanks, I’d like to take the offer from you!”
    

### 4️⃣ DHCPACK

- Sent by **server**.
    
- “Cool! That IP is yours now. You’re good to go.”
    

---

### 📶 Visualization:

```
Client      →      Server
[DISCOVER]  →  (I need an IP)

Server      →      Client
[OFFER]     →  (Here's one)

Client      →      Server
[REQUEST]   →  (I want that IP)

Server      →      Client
[ACK]       →  (You got it!)
```

---

## 🔄 **How IP Lease Renewal Works** (7.1.4)

Before the lease expires, the client tries to **renew it**:

### 1️⃣ DHCPREQUEST (Unicast)

- The client **asks the same server**:  
    “Can I keep using this IP?”
    

### 2️⃣ DHCPACK (Unicast)

- The server says:  
    “Yes, I acknowledge — lease extended.”
    

If the server doesn't respond, the client will **broadcast** the request again to other servers, just in case.

---

### 🔥 Key Concepts Recap:

|**Term**|**Meaning**|
|---|---|
|DHCP Server|The device giving out IPs (dedicated server or a router)|
|Lease|The “rental” of an IP address|
|DHCPDISCOVER|Client asks: “Is any DHCP server here?”|
|DHCPOFFER|Server replies: “Here’s an IP for you.”|
|DHCPREQUEST|Client says: “I accept this offer.”|
|DHCPACK|Server confirms: “It’s yours now.”|
|Unicast|One-to-one message (used during renewal)|
|Broadcast|One-to-all message (used when the client doesn’t know who the server is)|
No worries! Let’s break down **everything from 7.2.1 to 7.2.9** into **simple, organized points** so it’s easy to understand and remember:

---

## 🛠️ **7.2.1 – Cisco IOS DHCPv4 Server**

If you **don’t have a separate DHCP server**, you can **turn your router into a DHCP server** using Cisco IOS.

### Example Topology:

- R1 is the router (also acting as DHCP server)
    
- PC1 is on `192.168.10.0/24`
    
- PC2 and DNS Server are on `192.168.11.0/24`
    

---

## 🧾 **7.2.2 – Steps to Configure DHCP on a Router**

### ✅ **Step 1: Exclude Static IP Addresses**

These IPs won’t be given out to clients (for routers, printers, servers, etc.)

```bash
R1(config)# ip dhcp excluded-address 192.168.10.1 192.168.10.9
R1(config)# ip dhcp excluded-address 192.168.10.254
```

### ✅ **Step 2: Create a DHCP Pool**

This starts the DHCP config section:

```bash
R1(config)# ip dhcp pool LAN-POOL-1
```

### ✅ **Step 3: Configure Pool Settings**

```bash
R1(dhcp-config)# network 192.168.10.0 255.255.255.0      # Address range
R1(dhcp-config)# default-router 192.168.10.1             # Gateway
R1(dhcp-config)# dns-server 192.168.11.5                 # DNS server IP
R1(dhcp-config)# domain-name example.com                 # Optional domain
R1(dhcp-config)# end
```

---

## 📌 **7.2.3 – Example Configuration Recap**

```bash
ip dhcp excluded-address 192.168.10.1 192.168.10.9
ip dhcp excluded-address 192.168.10.254
ip dhcp pool LAN-POOL-1
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1
 dns-server 192.168.11.5
 domain-name example.com
```

---

## 🔍 **7.2.4 & 7.2.5 – DHCPv4 Verification Commands**

|**Command**|**What it does**|
|---|---|
|`show running-config|section dhcp`|
|`show ip dhcp binding`|Shows IPs leased to clients|
|`show ip dhcp pool`|Shows DHCP pool usage and stats|
|`ipconfig /renew` (on PC)|Forces PC to get new IP via DHCP|
|`ipconfig /all` (on PC)|Shows full IP config of the PC|

---

## 🧯 **7.2.6 – DHCP Syntax Checker (Example Task)**

### Task:

Configure DHCP for **192.168.11.0/24**, and **exclude**:

- `.1 to .9`
    
- `.254`
    

### Example:

```bash
R1(config)# ip dhcp excluded-address 192.168.11.1 192.168.11.9
R1(config)# ip dhcp excluded-address 192.168.11.254
R1(config)# ip dhcp pool LAN-POOL-2
R1(dhcp-config)# network 192.168.11.0 255.255.255.0
R1(dhcp-config)# default-router 192.168.11.1
R1(dhcp-config)# dns-server 192.168.11.6
R1(dhcp-config)# end
```

---

## 🚫 **7.2.7 – Disabling the DHCP Service**

Sometimes you want to disable the DHCP service temporarily:

```bash
R1(config)# no service dhcp      # Turns off DHCP service
R1(config)# service dhcp         # Turns it back on
```

⚠️ **Note**: Stopping DHCP may temporarily cause **duplicate IPs** if clients re-request leases.

---

## 🌐 **7.2.8 – DHCPv4 Relay**

### Problem:

- DHCP uses **broadcasts**, and routers don’t forward broadcasts.
    
- If PC1 is in subnet A, and DHCP server is in subnet B, it won’t get an IP.
    

### ✅ Solution: Use **ip helper-address**

```bash
R1(config)# interface g0/0/0
R1(config-if)# ip helper-address 192.168.11.6
```

This tells the router to **forward DHCP messages** from PC1 to the DHCP server at `192.168.11.6`.

---

## 📦 **7.2.9 – Other Services Relayed by ip helper-address**

When you use `ip helper-address`, it **automatically forwards** these 8 types of UDP broadcasts:

| **Port** | **Service**                  |
| -------- | ---------------------------- |
| 37       | Time                         |
| 49       | TACACS (Authentication)      |
| 53       | DNS                          |
| 67       | DHCP server                  |
| 68       | DHCP client                  |
| 69       | TFTP (Trivial File Transfer) |
| 137      | NetBIOS name service         |
| 138      | NetBIOS datagram service     |
**
---

## ✅ TL;DR Summary

|**Topic**|**Key Points**|
|---|---|
|Cisco Router as DHCP|Easy to set up using excluded-address and ip dhcp pool commands|
|Verification|Use `show running-config`, `show ip dhcp binding`, and `ipconfig` on PC|
|Disabling DHCP|Use `no service dhcp` and `service dhcp`|
|DHCP Relay|Use `ip helper-address` to forward DHCP across networks|
|Helper-address|Also forwards other important services (DNS, TFTP, NetBIOS, etc.)|

## ✅ **7.2.6 Syntax Checker – Configure DHCPv4 Server and Client**

### 🧩 **Part 1: Configure R1 as a DHCPv4 Server**
**Exclude the following addresses from the 192.168.11.0/24 address range:**

- Exclude the `.1` through `.9`
- Exclude the `.254`
    

```bash
R1(config)# ip dhcp excluded-address 192.168.11.1 192.168.11.9
R1(config)# ip dhcp excluded-address 192.168.11.254
```

---

**Define the pool name as `LAN-POOL-2`.**

```bash
R1(config)# ip dhcp pool LAN-POOL-2
```

---

**Configure the network address.**

```bash
R1(dhcp-config)# network 192.168.11.0 255.255.255.0
```

---

**Configure the default gateway address.**

```bash
R1(dhcp-config)# default-router 192.168.11.1
```

---

**Configure the DNS server address.**

```bash
R1(dhcp-config)# dns-server 192.168.11.6
```

---

**Configure `example.com` as the domain name.**

```bash
R1(dhcp-config)# domain-name example.com
```

---

**Return to privileged EXEC mode.**

```bash
R1(dhcp-config)# end
```

✅ _You have successfully configured the DHCPv4 server._

---

### 🧩 **Part 2: Configure SOHO Router as a DHCPv4 Client**

---

**Enter interface configuration mode. Use `g0/0/1` as the interface name.**

```bash
SOHO(config)# interface g0/0/1
```

---

**Configure the interface to acquire IPv4 addressing information from the ISP.**

```bash
SOHO(config-if)# ip address dhcp
```

---

**Activate the interface.**

```bash
SOHO(config-if)# no shutdown
```

🟢 _System Log Output:_  
`%DHCP-6-ADDRESS_ASSIGN: Interface GigabitEthernet0/0/1 assigned DHCP address 209.165.201.12, mask 255.255.255.224, hostname SOHO`

---

**Return to privileged EXEC mode.**

```bash
SOHO(config-if)# end
```

---

**Use the `show ip interface g0/0/1` command to verify the IPv4 information.**

```bash
SOHO# show ip interface g0/0/1
```

✅ _Expected Output:_

```
GigabitEthernet0/0/1 is up, line protocol is up
  Internet address is 209.165.201.12/27
  Broadcast address is 255.255.255.255
  Address determined by DHCP
(output omitted)
```

✅ _You have successfully configured the router as a DHCPv4 client._

---
#### This are the full commands for that
### ✅ **1. Configure R1 as a DHCPv4 Server**

```bash
R1> enable
R1# configure terminal
R1(config)# ip dhcp excluded-address 192.168.11.1 192.168.11.9
R1(config)# ip dhcp excluded-address 192.168.11.254
R1(config)# ip dhcp pool LAN-POOL-2
R1(dhcp-config)# network 192.168.11.0 255.255.255.0
R1(dhcp-config)# default-router 192.168.11.1
R1(dhcp-config)# dns-server 192.168.11.6
R1(dhcp-config)# domain-name example.com
R1(dhcp-config)# end
R1#
```

---

### ✅ **2. Configure SOHO Router Interface as a DHCP Client**

```bash
SOHO> enable
SOHO# configure terminal
SOHO(config)# interface g0/0/1
SOHO(config-if)# ip address dhcp
SOHO(config-if)# no shutdown
SOHO(config-if)# end
SOHO#

SOHO# show ip interface g0/0/1
```

You should see output like:

```
GigabitEthernet0/0/1 is up, line protocol is up
  Internet address is 209.165.201.12/27
  Broadcast address is 255.255.255.255
  Address determined by DHCP
```

## ✅ **7.3 Configure a DHCPv4 Client**

---

### 🧩 **7.3.1 Cisco Router as a DHCPv4 Client**

---

**Scenario:**  
You are connecting a **SOHO router** to the **ISP** using interface `G0/0/1`. The ISP provides IP addresses via DHCP (from the **209.165.201.0/27** network).  
You will configure this interface to **dynamically receive an IP address**.

---

### 🧪 **7.3.2 Configuration Example**

---

**Step 1:** Enter interface configuration mode for G0/0/1.

```bash
SOHO(config)# interface g0/0/1
```

---

**Step 2:** Configure the interface to receive an IPv4 address from DHCP.

```bash
SOHO(config-if)# ip address dhcp
```

---

**Step 3:** Activate the interface.

```bash
SOHO(config-if)# no shutdown
```

🟢 _Sample log message:_

```
%DHCP-6-ADDRESS_ASSIGN: Interface GigabitEthernet0/0/1 assigned DHCP address 209.165.201.12, mask 255.255.255.224, hostname SOHO
```

---

**Step 4:** Return to privileged EXEC mode.

```bash
SOHO(config-if)# end
```

---

**Step 5:** Verify the IP address using the show command.

```bash
SOHO# show ip interface g0/0/1
```

✅ _Expected output:_

```
GigabitEthernet0/0/1 is up, line protocol is up
  Internet address is 209.165.201.12/27
  Broadcast address is 255.255.255.255
  Address determined by DHCP
(output omitted)
```

✅ _You have successfully configured the Cisco router as a DHCPv4 client._

---

### 🏠 **7.3.3 Home Router as a DHCPv4 Client**

In most **home routers**, the **WAN/Internet port** is already set to:

> `Internet Connection Type: Automatic Configuration – DHCP`

This means the router acts as a **DHCPv4 client**, just like a Cisco router does when configured with `ip address dhcp`.

✅ No CLI configuration needed — it's plug-and-play!

### ✅ Syntax Checker – Configure a Cisco Router as a DHCPv4 Client

---

**Enter interface configuration mode. Use `g0/0/1` as the interface name.**

```bash
SOHO(config)# interface g0/0/1
```

---

**Configure the interface to acquire IPv4 addressing information from the ISP.**

```bash
SOHO(config-if)# ip address dhcp
```

---

**Activate the interface.**

```bash
SOHO(config-if)# no shutdown
```

🟢 _Log output:_

```
Sep 12 10:01:25.773: %DHCP-6-ADDRESS_ASSIGN: Interface GigabitEthernet0/0/1 assigned DHCP address 209.165.201.12, mask 255.255.255.224, hostname SOHO
```

---

**Return to privileged EXEC mode.**

```bash
SOHO(config-if)# end
```

---

**Use the `show ip interface g0/0/1` command to verify the IPv4 information.**

```bash
SOHO# show ip interface g0/0/1
```

✅ _Expected output:_

```
GigabitEthernet0/0/1 is up, line protocol is up
  Internet address is 209.165.201.12/27
  Broadcast address is 255.255.255.255
  Address determined by DHCP
(output omitted)
```

---

✅ **You have successfully configured the router as a DHCP client.**
