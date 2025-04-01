
![[file-20250316202311949.png]]
### **🛠️ Key Concepts**

1. **Encapsulation:**
    
    - The IP packet (Layer 3) is placed inside a **data link frame** (Layer 2).
    - The **frame has a new source and destination MAC address** at each hop.
2. **Role of Data Link Layer (Layer 2):**
    
    - Responsible for moving packets from one device (NIC) to another on the same network.
    - Each **network segment** has different MAC addresses.
3. **How the Router Handles Layer 2 Information:**
    
    - When a router **receives a frame**, it **removes the Layer 2 (data link) header**.
    - It **examines the Layer 3 (IP address)** to determine the next hop.
    - It **creates a new Layer 2 header** with:
        - **New source MAC address:** The router’s **outgoing NIC**.
        - **New destination MAC address:** The **next hop router or the final device**.

---

### **🖧 Example: Host-to-Router-to-Router-to-Host**

Let’s consider a scenario where **PC1 (192.168.1.10)** wants to send a packet to **Web Server (172.16.1.99)**. The data moves through **two routers**.

#### **🔹 Step-by-Step Breakdown**

1. **PC1 to Router1 (First Network Segment)**
    
    - **IP Packet:**
        - Source IP: **192.168.1.10**
        - Destination IP: **172.16.1.99**
    - **Data Link (MAC) Frame:**
        - **Source MAC:** PC1’s NIC MAC address
        - **Destination MAC:** Router1’s NIC MAC address
2. **Router1 to Router2 (Second Network Segment)**
    
    - **Router1 removes the old MAC addresses** and checks the IP address.
    - **Creates a new Layer 2 frame:**
        - **Source MAC:** Router1’s outgoing NIC MAC address
        - **Destination MAC:** Router2’s NIC MAC address
3. **Router2 to Web Server (Final Network Segment)**
    
    - **Router2 removes the old MAC addresses** and checks the IP address.
    - **Creates a new Layer 2 frame:**
        - **Source MAC:** Router2’s outgoing NIC MAC address
        - **Destination MAC:** Web Server’s MAC address