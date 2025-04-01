![[file-20250327192031471.png]]

##### Key Points:

1. **Trunk Links**:
    
    - A trunk link connects two devices (usually switches or routers) and allows them to carry traffic for multiple VLANs, unlike an access link, which carries traffic for only one VLAN.
    - For example, the connection between **Switch S1** and **Switch S2** or **S3** in the figure is a trunk. It supports the transmission of multiple VLANs, like VLAN 10, 20, 30, and the **native VLAN** (VLAN 99).
2. **IEEE 802.1Q**:
    
    - This is a standard used to tag Ethernet frames to identify which VLAN the frame belongs to. When VLAN traffic is sent over a trunk link, it gets "tagged" with a VLAN ID so that devices on the other side of the trunk link know to which VLAN the traffic belongs.
    - Cisco switches use **IEEE 802.1Q** to manage VLAN trunks. It’s a method of adding a tag (identifier) to the Ethernet frame to indicate which VLAN the traffic belongs to.
3. **Native VLAN**:
    
    - A **native VLAN** is a VLAN on a trunk link that is used to carry untagged traffic (traffic that doesn’t have a VLAN ID). By default, VLAN 1 is used as the native VLAN, but it can be changed. In the figure, **VLAN 99** is the native VLAN, and untagged frames sent across the trunk link will belong to VLAN 99.
    - Trunks allow the transmission of both tagged and untagged frames, where the tagged frames belong to specific VLANs, and untagged frames default to the native VLAN.
4. **Why VLAN Trunks are Important**:
    
    - Without trunks, VLANs would only be confined to a single switch. Devices connected to different switches in the same VLAN would not be able to communicate with each other. A trunk allows VLANs to span multiple switches.
    - For example, if **PC1** is in VLAN 10 and connected to **Switch S1**, and **PC2** is also in VLAN 10 but connected to **Switch S2**, the trunk link allows **PC1** and **PC2** to communicate, even though they are on different physical switches.

## Native VLANs and 802.1Q Tagging
**Tagged Frames on the Native VLAN**

Some devices that support trunking add a VLAN tag to native VLAN traffic. Control traffic sent on the native VLAN should not be tagged. If an 802.1Q trunk port receives a tagged frame with the VLAN ID that is the same as the native VLAN, it drops the frame. Consequently, when configuring a switch port on a Cisco switch, configure devices so that they do not send tagged frames on the native VLAN. Devices from other vendors that support tagged frames on the native VLAN include IP phones, servers, routers, and non-Cisco switches.

**Untagged Frames on the Native VLAN**

When a Cisco switch trunk port receives untagged frames (which are unusual in a well-designed network), it forwards those frames to the native VLAN. If there are no devices associated with the native VLAN (which is not unusual) and there are no other trunk ports (which is not unusual), then the frame is dropped. The default native VLAN is VLAN 1. When configuring an 802.1Q trunk port, a default Port VLAN ID (PVID) is assigned the value of the native VLAN ID. All untagged traffic coming in or out of the 802.1Q port is forwarded based on the PVID value. For example, if VLAN 99 is configured as the native VLAN, the PVID is 99 and all untagged traffic is forwarded to VLAN 99. If the native VLAN has not been reconfigured, the PVID value is set to VLAN 1.

### **What is IEEE 802.1Q Trunking?**

- **IEEE 802.1Q** is a **standard** for **VLAN tagging** in Ethernet networks.
    
- It defines how VLAN information is **tagged** to Ethernet frames when they travel across trunk links between switches or between switches and routers.
    

### **Key Points to Remember:**

1. **Purpose**:
    
    - 802.1Q allows multiple VLANs to traverse a single physical link between switches or a switch and a router.
        
    - It **tags** frames with a VLAN identifier (VLAN ID) to distinguish the traffic from different VLANs.
        
2. **Trunk Links**:
    
    - A **trunk link** is a connection that carries traffic for multiple VLANs.
        
    - The trunk link is configured to allow frames from multiple VLANs to pass through.
        
    - The **802.1Q** standard is used to tag these frames to indicate which VLAN they belong to.
        
3. **VLAN Tagging**:
    
    - 802.1Q inserts a **4-byte tag** into the Ethernet frame.
        
        - The **Tag Protocol Identifier (TPID)** is **0x8100** (indicating that the frame is VLAN-tagged).
            
        - The **VLAN ID** field (12 bits) identifies the VLAN the frame belongs to, supporting up to **4096 VLANs**.
            
        - The **Priority Code Point (PCP)** (3 bits) is used for **Quality of Service (QoS)**, allowing priority traffic.
            
4. **Frame Structure**:
    
    - The **802.1Q tag** is inserted **between the source MAC address** and the EtherType field in the Ethernet frame.
        
    - It consists of:
        
        - **Tag Protocol Identifier (TPID)**: 2 bytes (always 0x8100).
            
        - **Priority Code Point (PCP)**: 3 bits for QoS.
            
        - **Drop Eligible Indicator (DEI)**: 1 bit (used for marking frames that can be dropped under congestion).
            
        - **VLAN ID**: 12 bits (for identifying the VLAN, supporting values 0 to 4095).
            
5. **Native VLAN**:
    
    - The **native VLAN** is the default VLAN for **untagged** frames on a trunk port.
        
    - Frames belonging to the **native VLAN** are **not tagged** when sent over the trunk link.
        
    - The native VLAN helps ensure backward compatibility with older non-VLAN-aware devices.
        
6. **Trunking Configuration**:
    
    - Trunk ports are typically configured on both ends (on switches or routers) using the **`switchport mode trunk`** command in Cisco devices.
        
    - The **`switchport trunk encapsulation dot1q`** command is used to specify 802.1Q encapsulation.
        
7. **Encapsulation**:
    
    - 802.1Q is the most common trunking protocol used in modern networks.
        
    - It is widely supported by switches and routers, while other trunking protocols like **ISL (Inter-Switch Link)** are Cisco-specific and less common.
        
8. **Tagging Process**:
    
    - **Tagged frames** are sent across the trunk link with the VLAN ID.
        
    - When a frame arrives at the other end of the trunk, the switch removes the tag (decapsulates it) and forwards the frame to the appropriate port for that VLAN.
        
9. **Uses in Routing**:
    
    - **Router-on-a-stick**: In inter-VLAN routing with a router, the router interface is configured as a **subinterface** for each VLAN (using 802.1Q) to route traffic between VLANs.
        
10. **Advantages**:
    
    - **Efficient**: Reduces the need for multiple physical links between switches or routers.
        
    - **Scalable**: Allows you to extend VLANs over a single trunk, supporting many VLANs across the same physical infrastructure.
        
    - **Compatibility**: Supports various vendors and allows interconnection between switches from different manufacturers.
        

### **Example:**

To configure trunking on Cisco switches, you can use these commands:

```bash
Switch(config)# interface gig0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk encapsulation dot1q
```

---

##### **In Summary for IEEE 802.1Q trunk port**:

- **IEEE 802.1Q** is a standard that allows **VLAN-tagged frames** to travel across **trunk links** between switches/routers.
    
- It **inserts a tag** in each frame to indicate which VLAN the frame belongs to.
    
- Supports **multiple VLANs** on a single link, using **VLAN ID** (up to 4096 VLANs).
    
- The **native VLAN** is used for untagged frames.
    
- It is scalable, efficient, and widely supported across networks.
    

This should help you remember the essential details of **IEEE 802.1Q trunking**. Let me know if you need any more specifics!

## Access Ports 
### 🔌 What is an **Access Port**?

An **access port** is a **switch port** that is assigned to **only one VLAN**. It’s used to connect **end devices** like PCs, printers, IP phones, etc., to the network.

---

### 🧠 Key Features of Access Ports:

- Carries traffic **only for one VLAN**.
    
- It does **not tag** the Ethernet frames with VLAN IDs (unless connected to an IP phone or special device).
    
- When a frame enters an access port, the switch **assumes** it belongs to the VLAN that the port is assigned to.
    
- If a frame is sent **out** of an access port, it is sent **untagged** (just a regular Ethernet frame).
    

---

### 🖥️ Example:

If you have PC1 plugged into **port Fa0/1** of a switch, and that port is assigned to **VLAN 10**, then:

- PC1’s traffic will be treated as **belonging to VLAN 10**.
    
- PC1 has **no idea** it’s even on a VLAN. It just thinks it’s connected to a regular network.
    
- That port (Fa0/1) is now called an **access port for VLAN 10**.
    

---

### 🔁 Access Port vs Trunk Port:

| Feature       | Access Port            | Trunk Port                       |
| ------------- | ---------------------- | -------------------------------- |
| VLAN Support  | Only one VLAN          | Multiple VLANs                   |
| Frame Tagging | Untagged               | Tagged with 802.1Q (usually)     |
| Typical Use   | End device connections | Switch-to-switch or router links |

---

### 🛠️ CLI Example (Cisco):

```bash
Switch(config)# interface fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
```

This command sets **FastEthernet0/1** as an access port for **VLAN 10**.

---

Let me know if you want to see it in Packet Tracer or try it in config!
<iframe title="Cisco Tech Talk: Access and Trunk Ports for Beginners" src="https://www.youtube.com/embed/eYlX6W19dzo?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

## Data and Voice VLAN Example

Use the **switchport voice vlan** _vlan-id_ interface configuration command to assign a voice VLAN to a port.

LANs supporting voice traffic typically also have quality of service (QoS) enabled. Voice traffic must be labeled as trusted as soon as it enters the network. Use the **mls qos trust [cos | device cisco-phone | dscp | ip-precedence]** interface configuration command to set the trusted state of an interface, and to indicate which fields of the packet are used to classify traffic.

The configuration in the example creates the two VLANs (i.e., VLAN 20 and VLAN 150) and then assigns the F0/18 interface of S3 as a switchport in VLAN 20. It also assigns voice traffic to VLAN 150 and enables QoS classification based on the class of service (CoS) assigned by the IP phone.

```S3(config)# vlan 20
S3(config-vlan)# **name student**
S3(config-vlan)# **vlan 150**
S3(config-vlan)# **name VOICE**
S3(config-vlan)# **exit**
S3(config)# **interface fa0/18**
S3(config-if)# **switchport mode access**
S3(config-if)# **switchport access vlan 20**
S3(config-if)# **mls qos trust cos**
S3(config-if)# **switchport voice vlan 150**
S3(config-if)# **end**
S3#```






The **switchport access vlan** command forces the creation of a VLAN if it does not already exist on the switch. For example, VLAN 30 is not present in the **show vlan brief** output of the switch. If the **switchport access vlan 30** command is entered on any interface with no previous configuration, then the switch displays the following:


% Access VLAN does not exist. Creating vlan 

```




Absolutely! Here's the entire configuration and verification process formatted clearly and properly, step-by-step, for creating and managing VLANs on a Cisco switch:

---

## ✅ **1. Create a Data VLAN**

```bash
S1# configure terminal
S1(config)# vlan 20
S1(config-vlan)# name student
S1(config-vlan)# end
```

### Verify:

```bash
S1# show vlan brief
```

---

## ✅ **2. Create a Voice VLAN**

```bash
S1# configure terminal
S1(config)# vlan 150
S1(config-vlan)# name VOICE
S1(config-vlan)# exit
```

---

## ✅ **3. Assign Data and Voice VLANs to Port fa0/18**

```bash
S1(config)# interface fa0/18
S1(config-if)# switchport mode access
S1(config-if)# switchport access vlan 20
S1(config-if)# mls qos trust cos
S1(config-if)# switchport voice vlan 150
S1(config-if)# end
```

### Verify:

```bash
S1# show vlan brief
```

---

## ✅ **4. Delete the Data VLAN from Port fa0/18**

```bash
S1# configure terminal
S1(config)# interface fa0/18
S1(config-if)# no switchport access vlan
S1(config-if)# do show vlan brief
```

---

## ✅ **5. Assign VLAN 20 to Port fa0/11**

```bash
S1(config)# interface fa0/11
S1(config-if)# switchport mode access
S1(config-if)# switchport access vlan 20
S1(config-if)# end
```

### Verify:

```bash
S1# show vlan brief
```

---

## ✅ **6. Display VLAN Information for "student" VLAN**

```bash
S1# show vlan name student
```

---

## ✅ **7. Display VLAN Summary**

```bash
S1# show vlan summary
```

---

## ✅ **8. Display Switchport Information for fa0/11**

```bash
S1# show interface fa0/11 switchport
```

---

Sure! Here's the same list of commands **with the subheadings only** (no signs or extra formatting):

---

## **What is a VLAN Trunk?**

A **trunk** is a connection between two network devices (like switches) that allows **multiple VLANs** to travel across a **single link**.

- Trunks use **802.1Q** tagging to identify which VLAN each frame belongs to.
    
- Unlike **access ports** (which carry traffic for only **one VLAN**), a **trunk** can carry traffic for **many VLANs**.
    
- Trunks are essential to make VLANs **work across multiple switches**.
    

---

#### **Key Concepts**:

|Term|Description|
|---|---|
|**Access Port**|Carries traffic for a single VLAN. Used to connect end devices.|
|**Trunk Port**|Carries traffic for **multiple VLANs** using 802.1Q tagging.|
|**Native VLAN**|VLAN that carries **untagged** traffic on a trunk (default is VLAN 1, but can be changed).|
|**Allowed VLANs**|List of VLANs permitted to pass through the trunk.|
Sure! Here's the full list of **commands with their expected output/results** from the text you provided, all under clean subheadings (no symbols).

---

Configure a Trunk Port

```bash
interface fastEthernet 0/1
switchport mode trunk
switchport trunk native vlan 99
switchport trunk allowed vlan 10,20,30,99
end
```

Verify Trunk Configuration

```bash
show interfaces fa0/1 switchport
```

Expected output (key parts only):

```
Name: Fa0/1
Switchport: Enabled
Administrative Mode: trunk
Operational Mode: trunk
Administrative Trunking Encapsulation: dot1q
Operational Trunking Encapsulation: dot1q
Negotiation of Trunking: On
Access Mode VLAN: 1 (default)
Trunking Native Mode VLAN: 99 (VLAN0099)
Trunking VLANs Enabled: 10,20,30,99
```

```bash
show interface trunk
```

Expected output (key parts only):

```
Port        Mode         Encapsulation  Status        Native vlan
Fa0/1       on           802.1q         trunking      99

Vlans allowed on trunk: 10,20,30,99
Vlans allowed and active in management domain: 10,20,30,99
```

Reset Trunk to Default State

```bash
interface fa0/1
no switchport trunk allowed vlan
no switchport trunk native vlan
end
```

Expected result after reset:

```bash
show interfaces fa0/1 switchport
```

```
Name: Fa0/1
Administrative Mode: trunk
Operational Mode: trunk
Trunking Native Mode VLAN: 1 (default)
Trunking VLANs Enabled: ALL
```

Remove Trunk Mode and Set to Access Port

```bash
interface fa0/1
switchport mode access
end
```

Expected output:

```bash
show interfaces fa0/1 switchport
```

```
Name: Fa0/1
Administrative Mode: static access
Operational Mode: static access
Access Mode VLAN: 1 (default)
Trunking Native Mode VLAN: 1 (default)
```

Let me know if you want this in a printable or copy-friendly format, or if you'd like another section broken down this way!


# Dynamic Trunking Protocol 

<iframe title="Cisco CCNA DTP (Dynamic Trunking Protocol)" src="https://www.youtube.com/embed/WbGUygLN_kU?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
A **trunk link** is a special type of connection between two network devices (usually switches or a switch and a router) that **carries traffic for multiple VLANs**.
A **trunk** is like a **highway** that carries **multiple lanes (VLANs)** of traffic between devices. Without trunks, VLANs would only work on one switch.





DTP is a Cisco proprietary protocol that is automatically enabled on Catalyst 2960 and Catalyst 3650 Series switches. DTP manages trunk negotiation only if the port on the neighbor switch is configured in a trunk mode that supports DTP. Switches from other vendors do not support DTP.


Perfect! Here’s a **clear and simplified explanation** of **everything in Section 3.5 – Dynamic Trunking Protocol (DTP)** with all the key points, commands, and concepts explained so it’s easy to remember.

---

### Introduction to DTP

- **DTP (Dynamic Trunking Protocol)** is a **Cisco proprietary protocol**.
    
- It automatically negotiates trunk links **between Cisco switches**.
    
- DTP only works on **point-to-point connections** and only between **Cisco devices**.
    
- It **speeds up trunk configuration** but should be used with caution.
    

#### Key Warning:

If you're connecting a Cisco switch to a **non-Cisco device**, **DTP should be turned off** to avoid misconfigurations.

---

### DTP Modes Summary (using `switchport mode` command)

```bash
switchport mode access              # Forces the port into access mode
switchport mode trunk               # Forces the port into trunk mode
switchport mode dynamic desirable  # Actively tries to form a trunk
switchport mode dynamic auto       # Waits for the other side to initiate trunking
```

---

### DTP + `nonegotiate` Command

To force trunking and stop DTP frames:

```bash
switchport mode trunk
switchport nonegotiate
```

- This sets the port to **trunk mode** but **disables DTP negotiation**.
    
- Use when connecting to devices that **don’t support DTP**.
    

---

### DTP Mode Behavior Summary

|This Side|Other Side|Result|
|---|---|---|
|trunk + nonegotiate|trunk + nonegotiate|Trunk forms|
|dynamic auto|dynamic auto|❌ No trunk|
|dynamic auto|dynamic desirable|✅ Trunk|
|dynamic desirable|dynamic desirable|✅ Trunk|

---

### Best Practice

- Use **static trunking (`mode trunk`) and `nonegotiate`** where trunking is needed.
    
- Use **`mode access`** where trunking is NOT needed and to disable DTP completely.
    

---

### Verify DTP Mode

To check current DTP settings on an interface:

```bash
show dtp interface fa0/1
```

Expected output (sample):

```
DTP information for FastEthernet0/1:
TOS/TAS/TNS: ACCESS/AUTO/ACCESS
TOT/TAT/TNT: NATIVE/NEGOTIATE/NATIVE
FSM state: S2:ACCESS
Enabled: yes
```

This shows:

- Port is **not trunking** (`ACCESS`)
    
- It's set to **dynamic auto**
    
- **DTP is enabled** and waiting for negotiation
    

---

### Commands to Remember

```bash
switchport mode trunk
switchport mode access
switchport mode dynamic auto
switchport mode dynamic desirable
switchport nonegotiate
show dtp interface [interface]
```

---

### MCQ Section (With Correct Answers)

**Question 1:**  
True or false? DTP is an open standard IEEE protocol that specifies auto negotiation of switch trunk links.  
✅ **False**  
**Explanation:** DTP is **Cisco proprietary**, not IEEE standard.

---

**Question 2:**  
What is the default switchport mode for Cisco Catalyst switches?  
✅ **Dynamic auto**

---

**Question 3:**  
True or false? Two switchports on a link both configured as dynamic auto will successfully negotiate a trunk.  
✅ **False**  
**Explanation:** Both are waiting — no one initiates trunking.

---

**Question 4:**  
Which two DTP modes will form a trunk with an interface that is configured as dynamic auto?  
✅ **Trunk**  
✅ **Dynamic desirable**

**Explanation:** Dynamic auto will trunk if the other side either actively tries (desirable) or is statically trunked.


## What is Inter-VLAN Routing?

Inter-VLAN routing is the process of forwarding network traffic from one VLAN to another VLAN.

##### **Inter-VLAN Routing Overview**

Inter-VLAN routing allows devices in different VLANs to communicate with each other. There are three main types of inter-VLAN routing:

1. **Legacy Inter-VLAN Routing**: This is the oldest method. It uses a **router** with multiple physical interfaces, each connected to a different VLAN. It has scalability issues because it requires a separate physical interface for each VLAN.
    
2. **Router-on-a-Stick (ROAS)**: This method uses a **single router interface** configured as a **trunk** to route traffic between multiple VLANs. The router uses **subinterfaces**, each associated with a VLAN, to perform routing.
    
3. **Layer 3 Switch Routing**: This solution uses a **Layer 3 switch** with **SVIs (Switched Virtual Interfaces)** for each VLAN. The switch itself performs routing directly between VLANs without needing a separate router.

<iframe title="InterVLAN Routing: 3 options" src="https://www.youtube.com/embed/NmkFzDrZsXM?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
<iframe title="Router on a Stick Inter-VLAN Routing | CISCO Certification" src="https://www.youtube.com/embed/qwJlypSanLc?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
watch this to get the understanding of inter vlan(router on a stick) and stuff its lengthy but worth it

### **1. Purpose**:

- **Normal (Access) Port**:
    
    - Used to connect **end devices** (like PCs, printers, etc.) to the network.
    - An **access port** only carries traffic for a **single VLAN**.
    - Devices connected to the access port are members of that specific VLAN.
        
- **Trunk Port**:
    
    - Used to connect **switches** to each other or to a **router** in a **router-on-a-stick** configuration.
    - A **trunk port** carries traffic for **multiple VLANs** simultaneously, allowing for inter-VLAN communication.
    - It is typically used for **backbone links** or **uplink connections**.
        

---

### **2. VLAN Handling**:

- **Normal (Access) Port**:
    
    - Assigned to **only one VLAN**.
    - Frames received on an access port are **un-tagged**, and the switch assigns them to the correct VLAN based on the port configuration.
        
- **Trunk Port**:
    
    - Handles traffic for **multiple VLANs**.
    - Frames sent on a trunk port are **tagged with the VLAN ID** (using **802.1Q tagging**) so that devices receiving the frames can determine which VLAN the traffic belongs to.
        

---

### **3. VLAN Tagging**:

- **Normal (Access) Port**:
    
    - **No VLAN tagging**. Traffic from an access port is **untagged**.
    - The switch adds the frame to the configured VLAN of the port.
        
- **Trunk Port**:
    
    - **VLAN tagging** is used. When a frame enters the trunk port, it is tagged with a **VLAN ID** using the **802.1Q** protocol.
    - A trunk port can carry traffic for multiple VLANs, and the tags ensure that the traffic is correctly associated with the right VLAN.
        

---


### **5. Use Cases**:
- **Normal (Access) Port**:
    - Used for **end devices** like PCs, servers, or printers that only need to be in one VLAN.
    - Common in office or user networks.
        
- **Trunk Port**:
    - Used to **connect switches** or a **switch to a router**.
    - Ideal for **uplink connections** or to interconnect **multiple switches** in a larger network where multiple VLANs need to be carried.
        

---

### **6. Port Security**:

- **Normal (Access) Port**:
    
    - Generally more **secure** since it is used for devices that are in a single VLAN, so there’s less risk of traffic from other VLANs.
        
- **Trunk Port**:
    
    - **Less secure** compared to access ports, because it carries traffic from multiple VLANs. Any vulnerability in one VLAN can potentially affect others.
        

---

### **Summary Table:**

|Feature|Normal (Access) Port|Trunk Port|
|---|---|---|
|**Purpose**|Connects end devices to the network|Connects switches or switches to routers|
|**VLAN Membership**|One VLAN only|Multiple VLANs|
|**Traffic**|Untagged (frames are added to the VLAN)|Tagged with VLAN ID (802.1Q)|
|**Configuration**|`switchport mode access`|`switchport mode trunk`|
|**Example Use Case**|Connecting PCs, printers, etc.|Connecting switches, routers, uplinks|
|**Security**|Higher security as only one VLAN is used|Lower security due to multiple VLANs|

---

Certainly! Let’s walk through a **real-world example** of how a **trunk port** handles multiple VLANs using **802.1Q tagging**.

### Scenario:

You have two switches, **Switch A** and **Switch B**, and they are connected via a trunk link. Each switch has multiple devices connected to it, and these devices belong to different VLANs. The trunk link between the switches is configured to carry traffic for **VLAN 10**, **VLAN 20**, and **VLAN 30**.

### **Devices and VLANs**:

- **Switch A**:
    
    - **Port 1**: VLAN 10 (PC1)
        
    - **Port 2**: VLAN 20 (PC2)
        
    - **Port 3**: VLAN 30 (PC3)
        
- **Switch B**:
    
    - **Port 1**: VLAN 10 (PC4)
        
    - **Port 2**: VLAN 20 (PC5)
        
    - **Port 3**: VLAN 30 (PC6)
        
- The **Trunk Link** between **Switch A** and **Switch B** carries **VLAN 10**, **VLAN 20**, and **VLAN 30**.
    

---

### **Step-by-Step Process of How the Trunk Port Handles Multiple VLANs**:

#### **1. VLAN Tagging (802.1Q)**:

When PC1 (on VLAN 10) sends a frame to PC4 (on VLAN 10) through **Switch A**, the frame initially does not have a VLAN tag because it's leaving an **access port**. But when the frame reaches the **trunk port** on **Switch A** (port connected to **Switch B**), it is **tagged** with **VLAN 10** using **802.1Q**.

The frame will look like this when it enters the trunk port:

- **Ethernet Frame**:
    
    - **Source MAC**: PC1’s MAC address
        
    - **Destination MAC**: PC4’s MAC address
        
    - **VLAN Tag**: VLAN 10 (added by the trunk port)
        
    - **Data**: Payload from PC1 to PC4
        

**Trunk port adds the VLAN tag** to identify the VLAN (VLAN 10).

#### **2. Frame Traverses the Trunk Link**:

The **tagged frame** (VLAN 10) is sent across the trunk link to **Switch B**. The trunk link is configured to pass traffic from **VLAN 10**, **VLAN 20**, and **VLAN 30**, so all frames are tagged with the appropriate VLAN ID and travel through this link.

#### **3. VLAN Tag Removal (on the Receiving Switch)**:

When the tagged frame arrives at **Switch B** through the trunk port, **Switch B** will look at the **VLAN tag** in the frame to decide which VLAN the frame belongs to.

- If the frame is tagged with **VLAN 10**, **Switch B** forwards it to the port assigned to **VLAN 10** (which is port 1 connected to **PC4**).
    
- The **VLAN tag is removed** (decapsulation) as the frame enters **Switch B’s access port**, and the untagged frame is forwarded to **PC4**.
    

#### **4. Process Repeats for Other VLANs**:

- Similarly, if **PC2** (VLAN 20) on **Switch A** sends traffic to **PC5** (VLAN 20) on **Switch B**, the process will be the same:
    
    - The frame is **tagged with VLAN 20** at **Switch A**.
        
    - The tagged frame travels over the trunk link to **Switch B**.
        
    - **Switch B** reads the VLAN tag, removes it, and forwards the untagged frame to **PC5**.
        
- If **PC3** (VLAN 30) on **Switch A** sends traffic to **PC6** (VLAN 30) on **Switch B**, the same process happens, but this time the frame will be tagged with **VLAN 30**.

### **Why Can't Access Ports Handle Multiple VLANs?**

- **Access ports** can only handle **one VLAN at a time**, so they can't carry traffic for multiple VLANs across the same link.
    
- **Trunk ports** allow traffic from **multiple VLANs** to pass using **VLAN tagging** (802.1Q).



## ### **What is Layer 3 Switching and Inter-VLAN Routing?**

In a network with multiple **VLANs**, devices in one VLAN can't communicate directly with devices in another VLAN because VLANs separate broadcast domains. **Inter-VLAN routing** is the process of enabling communication between different VLANs, and this is where a **Layer 3 switch** or **router** comes in.

- **Layer 3 Switch**: A Layer 3 switch is a **switch with routing capabilities**, meaning it can perform routing between VLANs, much like a router.
    
- **SVI (Switched Virtual Interface)**: Each VLAN on the switch gets a **virtual interface** (SVI) with an IP address that acts as the **default gateway** for devices in that VLAN.
    

Now, let's break down the steps you're asking about.

---

### **4.3.3 Layer 3 Switch Configuration:**

This section describes how to configure a **Layer 3 switch (S1)** to enable **VLANs and routing**.

### **Step 1: Create the VLANs**:

- You need to **create VLANs** on the switch to logically separate the network. Each VLAN will be assigned a **range of IP addresses**.
    

**Example:** If you want **VLAN 10** and **VLAN 20**, you'd use the following commands to create them:

bash

Copy

`Switch(config)# vlan 10 Switch(config-vlan)# name VLAN_10 Switch(config)# vlan 20 Switch(config-vlan)# name VLAN_20`

This creates **VLAN 10** and **VLAN 20** on your switch.

---

### **Step 2: Create the SVI VLAN interfaces**:

- **SVIs (Switched Virtual Interfaces)** are created to enable **inter-VLAN routing**. They are like **virtual interfaces** on a Layer 3 switch, each assigned to a VLAN and with an IP address.
    

For example, to create an SVI for **VLAN 10** with IP address `192.168.10.1`:

bash

Copy

`Switch(config)# interface vlan 10 Switch(config-if)# ip address 192.168.10.1 255.255.255.0 Switch(config-if)# no shutdown`

This interface now acts as the **default gateway** for devices in **VLAN 10**.

Repeat this for **VLAN 20** with a different IP address (e.g., `192.168.20.1`):

bash

Copy

`Switch(config)# interface vlan 20 Switch(config-if)# ip address 192.168.20.1 255.255.255.0 Switch(config-if)# no shutdown`

These SVIs allow devices in different VLANs to communicate through the switch.

---

### **Step 3: Configure access ports**:

- **Access ports** are configured for devices that are **part of a specific VLAN**. For example, if **PC1** belongs to **VLAN 10**, we would configure the port to be part of **VLAN 10**.
    

To configure a port (e.g., `GigabitEthernet1/0/1`) to be in **VLAN 10**:

bash

Copy

`Switch(config)# interface gigabitEthernet 1/0/1 Switch(config-if)# switchport mode access Switch(config-if)# switchport access vlan 10`

This makes **GigabitEthernet1/0/1** an access port assigned to **VLAN 10**.

---

### **Step 4: Enable IP routing**:

- By default, Layer 3 switches don't route between VLANs. You need to enable **IP routing** to allow communication between the VLANs.
    

To enable IP routing:

bash

Copy

`Switch(config)# ip routing`

Now, **traffic can be routed** between **VLAN 10** and **VLAN 20** using the **SVIs**.

---

### **4.3.4 Layer 3 Switch Inter-VLAN Routing Verification:**

After configuration, you can verify that **inter-VLAN routing** is working.

- **Ping between devices**: Test if devices in different VLANs can communicate (e.g., PC1 in VLAN 10 should be able to ping PC2 in VLAN 20).
    

1. First, **verify the IP configuration** on **PC1** using `ipconfig`:
    
    bash
    
    Copy
    
    `C:\Users\PC1> ipconfig`
    
    You should see something like:
    
    - **IP Address**: `192.168.10.10`
        
    - **Default Gateway**: `192.168.10.1` (the **SVI for VLAN 10**)
        
2. **Ping from PC1 to PC2** to test inter-VLAN routing:
    
    bash
    
    Copy
    
    `C:\Users\PC1> ping 192.168.20.10`
    
    If successful, **inter-VLAN routing** is working, and **PC1** in **VLAN 10** can communicate with **PC2** in **VLAN 20**.
    

---

### **4.3.5 Routing on a Layer 3 Switch:**

If you want to **connect your Layer 3 switch to other Layer 3 devices** (like routers), you need to configure **routed ports**.

- **Routed port**: This is a port that acts like a **Layer 3 interface** instead of a Layer 2 port.
    

For example, to convert **GigabitEthernet0/0/1** into a routed port (no switching functionality):

bash

Copy

`Switch(config)# interface GigabitEthernet0/0/1 Switch(config-if)# no switchport Switch(config-if)# ip address 10.10.10.2 255.255.255.0 Switch(config-if)# no shutdown`

Now, this port behaves like a **router interface** and can be used to connect to another Layer 3 device, like a router.

---

### **4.3.7 Routing Configuration on a Layer 3 Switch:**

When connecting a **Layer 3 switch** (D1) to a **router** (R1), you need to configure **routing protocols** like **OSPF** if needed.

For example, if you’re configuring **OSPF** for routing, you can enter the **OSPF configuration**:

bash

Copy

`Switch(config)# router ospf 1 Switch(config-router)# network 10.10.10.0 0.0.0.255 area 0 Switch(config-router)# network 10.20.20.0 0.0.0.255 area 0`

- This tells the Layer 3 switch to advertise its **VLAN networks** to **R1** using OSPF.
    

---

### **In Summary**:

1. **Create VLANs** and **SVIs** to give each VLAN an IP address.
    
2. **Configure access ports** to assign devices to their VLANs.
    
3. Enable **IP routing** on the Layer 3 switch to allow communication between VLANs.
    
4. Verify connectivity by **pinging** between hosts in different VLANs.


## Common inter - VLAN issues solution
![[file-20250330174152761.png]]

### **5.1.1 Redundancy in Layer 2 Switched Networks**

Redundancy in a network means providing **alternate paths** between devices to **ensure availability** if one path fails. However, having **multiple paths** in a **Layer 2 Ethernet network** can lead to **loops**, where data keeps circulating endlessly between switches. This is a major problem because it can cause network **instability**.

---

### **5.1.2 Spanning Tree Protocol (STP)**

**Spanning Tree Protocol (STP)** is used to prevent these **Layer 2 loops**. It helps in designing a **loop-free topology** even with **redundant paths**.

- **STP ensures that only one path is active between switches** and it **blocks** other redundant paths.
    
- If a primary path fails, STP will **unblock** the next best path to maintain connectivity.
    

**IEEE 802.1D** is the original standard for STP, and it ensures network redundancy **without loops**.

### **How STP Works:**

- Switches running STP exchange information to create a **loop-free path**.
    
- **Broadcast frames** (e.g., ARP requests) are forwarded out of all ports except the one they came in through, to ensure every device on the network gets the frame. However, without STP, a **loop** can form if the broadcast frame keeps circulating.
    

---

### **5.1.3 STP Recalculation**

When a **failure occurs**, such as a **link failure**, STP recalculates the network topology. For example, if a link between **Switch S2 and S1** fails:

- **Switch S2** will unblock the alternate path and forward the broadcast again, but it will use the other available switch ports for forwarding.
    

---

### **5.1.4 Issues with Redundant Switch Links**

Without STP:

- **Redundant switch links** can create **Layer 2 loops**, which cause:
    
    - **MAC address table instability**: Constant changes in the MAC address table due to endless forwarding of frames.
        
    - **CPU utilization**: High CPU usage on switches as they constantly update their MAC tables.
        
    - **Link saturation**: Links can get overwhelmed with **broadcast traffic**.
        

### **How Loops Happen**:

- In a **Layer 2 loop**, Ethernet frames (like broadcast frames or unknown unicast frames) can loop forever because there's no limit (like TTL in Layer 3). This leads to **broadcast storms**.
    

---

### **5.1.5 Layer 2 Loops**

Without **STP**, **Layer 2 loops** can:

- Cause **broadcast frames** (e.g., ARP requests) to circulate endlessly, bringing down the network.
    
- **MAC address table instability** occurs when a switch keeps learning new paths for the same MAC address because the frames keep circulating.
    

When a frame loops endlessly, the switch's **MAC address table keeps updating** with different ports for the same address, making it impossible to properly forward frames.

---

### **5.1.6 Broadcast Storm**

A **broadcast storm** happens when there’s a **Layer 2 loop**, causing **broadcast traffic** to increase massively and overwhelm the network. This can happen very quickly, and within **seconds**, the network can become unusable due to:

- **Switches unable to process frames** because their **MAC address tables** are constantly changing.
    
- **End devices** being flooded with broadcast frames, which they can't process.
    

---

### **5.1.7 The Spanning Tree Algorithm (STA)**

The **Spanning Tree Algorithm (STA)** was invented by **Radia Perlman** to prevent loops. It creates a **loop-free topology** by:

1. **Selecting a Root Bridge**: One switch becomes the **root bridge**.
    
2. **Blocking Redundant Paths**: STA **blocks** other paths to eliminate loops.
    
3. **Calculating the Best Path**: Other switches determine the best path to the **root bridge** and block less optimal paths.
    

**STA Steps**:

1. **Elect the Root Bridge**: The root bridge is the central switch in the network.
    
2. **Block Redundant Paths**: Redundant links are placed into a **blocked state** to avoid loops.
    
3. **Loop-Free Topology**: Once the best path is chosen, switches only forward frames along that path.
    
4. **Recalculation After Failure**: If a path fails, STP recalculates the network topology and **unblocks** the next best path


## 🔁 Steps to a Loop-Free Topology (STP)**

**Spanning Tree Protocol (STP)** builds a loop-free Layer 2 network in **4 steps**:

1. **Elect the Root Bridge**
    
2. **Elect the Root Ports**
    
3. **Elect Designated Ports**
    
4. **Elect Alternate (Blocked) Ports**
    

To do this, switches use messages called **BPDUs (Bridge Protocol Data Units)** to share information about themselves. These BPDUs contain a **Bridge ID (BID)**.

🧠 **BID = Bridge Priority + Extended System ID + MAC Address**

- **Bridge Priority**: Default is 32768. Lower is better.
    
- **Extended System ID**: Usually the **VLAN ID**.
    
- **MAC Address**: If priorities are equal, the switch with the **lowest MAC address** wins.
    

---

## 🏆 **5.2.2 – Step 1: Elect the Root Bridge**

- All switches first think **they’re the root bridge**, then they exchange BPDUs.
    
- The switch with the **lowest BID** becomes the **root bridge**.
    
- Example: If S1 has a lower BID than S2 and S3, S1 becomes the **Root Bridge**.
    
- All other switches will use this switch as a reference point.
    

📌 **TIP**: You can control which switch becomes root by manually setting its **priority lower**.

---

## 🧮 **5.2.3 – Impact of Default BIDs**

If **all switches have the same priority** (default 32768), the switch with the **lowest MAC address** becomes the root bridge.

🧠 Example:

- All switches have priority 32769 (32768 + VLAN 1).
    
- MAC addresses decide the root:
    
    - S2: 000A.0011.1111 → This is the lowest MAC → S2 is the root.
        

✅ Best practice: **Manually set the root bridge’s priority lower** so you decide the root, not the MAC.

---

## 🛣️ **5.2.4 – Determine the Root Path Cost**

Once the **root bridge** is elected, each switch needs to find its **best path** to reach it.

- STP calculates a **cost** based on **port speed**:
    
    - **10 Mbps** = 100
        
    - **100 Mbps** = 19
        
    - **1 Gbps** = 4
        
    - **10 Gbps** = 2
        

Each switch **adds up the costs** of the path to the root. The **lowest cost** path becomes the preferred path.

---

## 🔌 **5.2.5 – Step 2: Elect the Root Ports**

- Every **non-root switch** chooses **1 port** that has the **lowest cost path to the root bridge**. This port is called the **Root Port**.
    
- Example: If S2 has two paths to root:
    
    - Path 1 cost = 19
        
    - Path 2 cost = 38 ✅ Path 1 wins → that port becomes the root port.
        

Each switch can have **only one root port**.

---

## 🔰 **5.2.6 – Step 3: Elect Designated Ports**

- **Every network segment** (the cable between 2 switches) must have **1 designated port**.
    
- The **designated port** is the one **closest to the root** (lowest cost).
    

🧠 Rules:

- **All ports on the root bridge** are automatically **designated ports**.
    
- If a switch’s port is not a root port but it’s the **best on its link**, it becomes a **designated port**.
    

---

## ⛔ **5.2.7 – Step 4: Elect Alternate (Blocked) Ports**

- If a port is **not a root** or **designated**, it becomes an **alternate (blocked) port**.
    
- This port is in a **blocking state** – it doesn’t forward traffic.
    

Why? To **prevent loops**. If the main path fails, STP can **recalculate** and unblock the alternate port.

---

## ⚖️ **5.2.8 – Elect Root Port from Equal-Cost Paths**

What if a switch has **2 equal-cost paths** to the root? It uses this tie-breaker order:

1. **Lowest sender BID** (neighbor switch with lowest BID wins)
    
2. **Lowest sender port priority**
    
3. **Lowest sender port number**
    

📌 Example:

- S2 is connected to S3 and S4
    
- Both paths have the same cost
    
- S4 has a **lower BID** → S2 uses the port to S4 as the root port
    

---

## ⏲️ **5.2.9 – STP Timers and Port States**

STP uses **timers** to manage transitions between states:

|**Timer**|**Default**|**Purpose**|
|---|---|---|
|Hello Timer|2 sec|Time between BPDU messages|
|Forward Delay|15 sec|Time in Listening & Learning states|
|Max Age|20 sec|Wait time before switching topology|

### 🌐 STP Port States:

|**State**|**Function**|
|---|---|
|**Blocking**|No data passes. Listens for BPDUs.|
|**Listening**|Prepares to forward, but not learning MACs yet.|
|**Learning**|Learns MAC addresses but doesn’t forward data.|
|**Forwarding**|Forwards data normally.|
|**Disabled**|Port is administratively shut down.|

🧠 Switches go from **Blocking → Listening → Learning → Forwarding**

---

## 🧩 **5.2.10 – Operational Details of Each Port State**

Here’s a quick cheat sheet:

|**Port State**|**Learns MACs?**|**Sends/Receives Frames?**|**Part of STP?**|
|---|---|---|---|
|Blocking|❌|❌|✅|
|Listening|❌|❌|✅|
|Learning|✅|❌|✅|
|Forwarding|✅|✅|✅|
|Disabled|❌|❌|❌|

---

## 🌐 **5.2.11 – Per-VLAN Spanning Tree (PVST)**

- When you have **multiple VLANs**, you don’t want just one root bridge for everything.
    
- **PVST** (Per-VLAN Spanning Tree) runs **a separate STP instance for each VLAN**.
    
- This allows:
    
    - Different VLANs to have **different root bridges**
        
    - Better use of backup links
        
    - More optimized traffic paths
        

📌 Example:

- VLAN 10 uses **S1 as root bridge**
    
- VLAN 20 uses **S2 as root bridge**
    

---

## ✅ In Short — STP Process:

1. Elect **Root Bridge** (lowest BID wins)
    
2. Each switch picks **one Root Port**
    
3. Each link picks **one Designated Port**
    
4. Any other port becomes **Alternate (Blocked)**
    

This creates a **loop-free** Layer 2 topology.

---

Here’s a simplified but **complete explanation** of **everything in section 5.3** — about **different types of STP, faster versions like RSTP, how PortFast helps, and modern alternatives to STP**.

---

## 🔄 **5.3.1 – Different Versions of STP**

🧠 **STP (Spanning Tree Protocol)** isn’t just one thing — it has different **versions**:

|**Name**|**Standard**|**Key Point**|
|---|---|---|
|**STP**|IEEE 802.1D|The original spanning tree protocol|
|**RSTP**|IEEE 802.1w|Faster version of STP|
|**PVST+**|Cisco|Per-VLAN version of STP|
|**Rapid PVST+**|Cisco|Per-VLAN version of RSTP|
|**MSTP**|IEEE 802.1s|Supports multiple VLANs in one STP instance|

> 💡 **Cisco switches use PVST+ by default** and support Rapid PVST+ if configured.

---

## ⚡ **5.3.2 – RSTP Concepts**

- **RSTP = Rapid Spanning Tree Protocol (IEEE 802.1w)**
    
- It’s **faster than original STP** (can converge in **milliseconds** instead of seconds).
    
- Uses **same logic and terminology** as STP — so it's easy to learn if you already know STP.
    
- **Cisco’s Rapid PVST+** is RSTP but works **per VLAN** (one STP instance for each VLAN).
    

---

## 🔌 **5.3.3 – RSTP Port States & Roles**

### 🚦 **Port States:**

STP had 5 states; RSTP simplifies it into **3 main states**:

|**STP**|**RSTP**|
|---|---|
|Disabled|Discarding|
|Blocking|Discarding|
|Listening|Discarding|
|Learning|Learning|
|Forwarding|Forwarding|

✅ **RSTP discarding = disabled/blocking/listening**

---

### 🔑 **Port Roles (Same in STP & RSTP):**

- **Root Port (RP)** – best path to root bridge.
    
- **Designated Port (DP)** – forwards traffic on a network segment.
    
- **Alternate/Backup Port** – used as backup; stays blocked unless needed.
    

💡 **RSTP can immediately switch an Alternate Port to Forwarding**, making it **much faster** than STP.

---

## ⚙️ **5.3.4 – PortFast & BPDU Guard**

### 🕒 Problem with STP:

When a device connects, its port **waits ~30 seconds** before forwarding traffic. This delay can **break DHCP or slow connections**.

### ✅ **PortFast Fixes This**

- **PortFast** skips the waiting time and **immediately puts the port in Forwarding state**.
    
- ✅ Use it only on ports connected to **end devices** (like PCs or printers), **not to other switches**.
    

---

### 🚫 **BPDU Guard**

- **BPDUs** are only expected from other switches.
    
- If a PortFast-enabled port **receives a BPDU**, something is wrong (like someone plugged in a switch).
    
- **BPDU Guard** immediately **shuts down** (errdisables) that port to **prevent a loop**.
    

✅ Use **PortFast + BPDU Guard** together on **access ports** for safety.

---

## 🚀 **5.3.5 – Alternatives to STP**

Modern networks are much bigger, with **more switches and VLANs**. STP, while useful, is **slower** than Layer 3 routing and not always the best for large networks.

### 🔀 Newer Designs:

- Use **Layer 2 only at the access layer**
    
- Use **Layer 3 routing between access → distribution → core**
    
- **No loops**, no blocking — routing handles it
    

### 🧠 Modern Alternatives to STP:

- **MLAG (Multi-System Link Aggregation)** – link aggregation across multiple switches.
    
- **SPB (Shortest Path Bridging)** – uses shortest path like routing.
    
- **TRILL (Transparent Interconnect of Lots of Links)** – Layer 2 + Layer 3 hybrid.
    

> 💡 These are advanced technologies — not covered deeply in this course.

---

## ✅ Summary: What You Should Remember

|**Topic**|**Key Idea**|
|---|---|
|**STP vs RSTP**|RSTP is faster, with fewer port states (discarding, learning, forwarding).|
|**Rapid PVST+**|Cisco’s version of RSTP for each VLAN.|
|**PortFast**|Skips STP delay. Use only on end devices.|
|**BPDU Guard**|Shuts down a PortFast port if a BPDU is received.|
|**Modern networks**|Prefer Layer 3 routing to avoid STP limitations.|
|**Other STP versions**|MSTP, PVST+, Rapid PVST+, etc.|
|**STP Still Matters**|Especially on access switches in enterprise networks.|

---
---

## 🔗 **6.1.1 – Link Aggregation (Why We Use EtherChannel)**

- **Problem:** STP blocks **redundant links** to prevent loops — so you can’t use multiple links for more speed.
    
- **Solution:** **EtherChannel** lets you **combine multiple physical links** into one **logical link** that **STP sees as one connection**, so **no links get blocked**.
    

---

## ⚙️ **6.1.2 – What is EtherChannel?**

- EtherChannel = **Cisco’s technology** for link aggregation.
    
- **Groups multiple Ethernet ports** into a **single port-channel**.
    
- You configure the **port-channel interface** instead of individual links.
    

---

## ✅ **6.1.3 – Advantages of EtherChannel**

1. **One configuration** on the port channel affects all member ports.
    
2. **More bandwidth** without upgrading cables or ports.
    
3. **Load balancing** across links (MAC/IP-based).
    
4. **Seen as one link by STP** – no blocked paths.
    
5. **Redundancy** – if one physical link fails, others still carry traffic.
    
6. **No topology recalculation** needed unless all links fail.
    

---

## 📋 **6.1.4 – EtherChannel Restrictions (on Catalyst 2960)**

- All ports must be **same type** (e.g., all Gigabit).
    
- Up to **8 ports** per EtherChannel.
    
- Can make up to **6 EtherChannels**.
    
- Both sides must have **matching settings**:
    
    - Speed, duplex, trunking, VLANs, mode (access/trunk), etc.
        
- **Configure the port channel**, not the physical ports.
    
- All ports must be **Layer 2** (not routed).
    

---

## 🤝 **6.1.5 – EtherChannel Protocols**

You can configure EtherChannel:

- **Statically** (manually)
    
- Or with **auto negotiation** using one of:
    
    - **PAgP (Cisco proprietary)**
        
    - **LACP (IEEE standard, multi-vendor)**
        

---

## 🔁 **6.1.6 – PAgP (Port Aggregation Protocol)**

- **Cisco-only**
    
- Helps build EtherChannel by **negotiating** between switches.
    

### 📡 PAgP Modes:

|Mode|Description|
|---|---|
|**on**|Forces EtherChannel (no PAgP used)|
|**desirable**|Actively tries to form EtherChannel|
|**auto**|Passive — waits for the other side to start|

📌 **Important**:

- **Desirable + Auto = works** ✅
    
- **Auto + Auto = no EtherChannel** ❌
    
- **On + On = works (manual)**
    
- **On + Auto/Desirable = no match** ❌
    

---

## 📊 **6.1.7 – PAgP Mode Examples**

|S1 Mode|S2 Mode|EtherChannel Formed?|
|---|---|---|
|On|On|✅ Yes|
|Desirable|Auto|✅ Yes|
|Desirable|Desirable|✅ Yes|
|Auto|Auto|❌ No|
|On|Auto|❌ No|

---

## 🌐 **6.1.8 – LACP (Link Aggregation Control Protocol)**

- **IEEE Standard (802.3ad / now 802.1AX)**
    
- Same purpose as PAgP but **multi-vendor compatible**
    

### 📡 LACP Modes:

|Mode|Description|
|---|---|
|**on**|Forces EtherChannel (no LACP)|
|**active**|Actively starts negotiation|
|**passive**|Waits for the other side to start|

📌 Just like PAgP:

- **Active + Passive = works** ✅
    
- **Passive + Passive = no EtherChannel** ❌
    
- **On + anything = only works with On** ❌
    

---

## 🔁 **6.1.9 – LACP Mode Examples**

|S1 Mode|S2 Mode|EtherChannel Formed?|
|---|---|---|
|On|On|✅ Yes|
|Active|Passive|✅ Yes|
|Active|Active|✅ Yes|
|Passive|Passive|❌ No|
|On|Active|❌ No|

---

## 🧠 Quick Recap:

|**Feature**|**PAgP**|**LACP**|
|---|---|---|
|Vendor|Cisco only|IEEE standard|
|Mode 1|On|On|
|Mode 2|Auto (passive)|Passive|
|Mode 3|Desirable (active)|Active|
|Works with:|Cisco switches|Multi-vendor|
|BPDUs exchanged?|Yes (PAgP/LACP)|Yes|

---

Let me know if you want a **cheat sheet**, **diagram**, or **practice questions** to review this!