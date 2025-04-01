<iframe src="https://www.youtube.com/embed/LkolbURrtTs?list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
<iframe title="OSI Model: A Practical Perspective - Part 2 - Networking Fundamentals - Lesson 2" src="https://www.youtube.com/embed/0aGqGKrRE0g?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>



[[Intro to what are layers]]
[[NIC(Network Interface Card)]]


3.5.2 The OSI Reference Model

The OSI reference model provides an extensive list of functions and services that can occur at each layer. This type of model provides consistency within all types of network protocols and services by describing what must be done at a particular layer, but not prescribing how it should be accomplished.

It also describes the interaction of each layer with the layers directly above and below. The TCP/IP protocols discussed in this course are structured around both the OSI and TCP/IP models. The table shows details about each layer of the OSI model. The functionality of each layer and the relationship between layers will become more evident throughout this course as the protocols are discussed in more detail.

| **OSI Model Layer**  | **Description**                                                                                                                                                                                                     |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **7 - Application**  | The application layer contains protocols used for process-to-process communications.                                                                                                                                |
| **6 - Presentation** | The presentation layer provides for common representation of the data transferred between application layer services.                                                                                               |
| **5 - Session**      | The session layer provides services to the presentation layer to organize its dialogue and to manage data exchange.                                                                                                 |
| **4 - Transport**    | The transport layer defines services to segment, transfer, and reassemble the data for individual communications between the end devices.                                                                           |
| **3 - Network**      | The network layer provides services to exchange the individual pieces of data over the network between identified end devices.                                                                                      |
| **2 - Data Link**    | The data link layer protocols describe methods for exchanging data frames between devices over a common media                                                                                                       |
| **1 - Physical**     | The physical layer protocols describe the mechanical, electrical, functional, and procedural means to activate, maintain, and de-activate physical connections for a bit transmission to and from a network device. |
### **📌 OSI Model - Data Flow Through the Layers**

### **1️⃣ Application Layer (Layer 7 - OSI Model)**

- **What happens?** User applications generate data (e.g., web browsing, email, file transfer).
- **Protocols:** HTTP, FTP, SMTP, DNS.

### **2️⃣ Presentation Layer (Layer 6 - OSI Model)**

- **What happens?** Data is **formatted, compressed, or encrypted** for transmission.
- **Protocols:** SSL/TLS (encryption), JPEG (image formatting), MP3 (audio encoding).

### **3️⃣ Session Layer (Layer 5 - OSI Model)**

- **What happens?** Establishes, maintains, and terminates communication **sessions** between devices.
- **Protocols:** NetBIOS, SIP (VoIP), PPTP (VPN).

### **4️⃣ Transport Layer (Layer 4 - OSI Model)**

- **What happens?** **Segments** data and ensures **reliable or fast** delivery using TCP or UDP.
- **Protocols:** TCP (reliable, used for web & email), UDP (fast, used for streaming & gaming).

### **5️⃣ Network Layer (Layer 3 - OSI Model)**

- **What happens?** **Adds IP addresses** and **routes packets** across networks.
- **Protocols:** IP (IPv4/IPv6), ICMP (ping), OSPF, BGP (routing).

### **6️⃣ Data Link Layer (Layer 2 - OSI Model)**

- **What happens?** **Encapsulates packets into frames**, assigns **MAC addresses** for local delivery.
- **Protocols:** Ethernet, Wi-Fi (802.11), ARP.

### **7️⃣ Physical Layer (Layer 1 - OSI Model)**

- **What happens?** Converts frames into **electrical signals, radio waves, or light pulses**.
- **Protocols:** Bluetooth, Fiber Optics, USB, Coaxial Cable.

🚀 **This is how data moves from the application to the physical network!** 😊

## **How Many Layers Are There in Networking?**

There are **two primary models** used in networking:

1. **OSI Model (7 Layers)** – A theoretical framework used for learning and design.
2. **TCP/IP Model (4 Layers)** – A practical model used for real-world internet communication.

### **1️⃣ OSI Model (7 Layers)**

The **OSI (Open Systems Interconnection) Model** divides networking into **7 layers**, each with a specific function.

|**Layer Number**|**Layer Name**|**Function**|**Example Protocols**|
|---|---|---|---|
|**7**|Application|User interface & network services|HTTP, FTP, SMTP, DNS|
|**6**|Presentation|Data formatting & encryption|SSL, TLS, JPEG, MPEG|
|**5**|Session|Manages connections between devices|NetBIOS, RPC, PPTP|
|**4**|Transport|Reliable or fast data delivery|TCP, UDP|
|**3**|Network|Routing and IP addressing|IP, ICMP, ARP, OSPF, BGP|
|**2**|Data Link|MAC addressing, error detection|Ethernet, Wi-Fi, MAC, PPP|
|**1**|Physical|Transmission of raw bits (1s and 0s)|Fiber optics, Coaxial cables, Bluetooth|


---

### **2️⃣ TCP/IP Model (4 Layers)**

The **TCP/IP Model** is used in real-world networking (e.g., the internet). It simplifies OSI’s **7 layers into 4 layers**.

|**TCP/IP Layer**|**Equivalent OSI Layers**|**Function**|**Example Protocols**|
|---|---|---|---|
|**Application**|Application, Presentation, Session|Provides services & applications|HTTP, FTP, DNS, SMTP|
|**Transport**|Transport|Ensures reliable or fast data transfer|TCP, UDP|
|**Internet**|Network|IP addressing, routing|IP, ICMP, ARP, BGP, OSPF|
|**Network Access**|Data Link + Physical|Physical transmission of data|Ethernet, Wi-Fi, MAC Address|

---

## **📌 OSI Model Layers Explained with Protocols**

### **🔹 1. Physical Layer (Layer 1)**

- **Function:** Transfers raw binary data over physical media.
- **Devices:** Hubs, cables, fiber optics, antennas.
- **Protocols:** Bluetooth, USB, Ethernet (physical signaling).

### **🔹 2. Data Link Layer (Layer 2)**

- **Function:** Manages **MAC addresses** and **error detection**.
- **Devices:** Switches, network interface cards (NICs).
- **Protocols:** Ethernet, Wi-Fi (802.11), MAC, PPP.

### **🔹 3. Network Layer (Layer 3)**

- **Function:** Assigns **IP addresses** and **routes packets**.
- **Devices:** Routers.
- **Protocols:** IP (IPv4, IPv6), ICMP, ARP, OSPF, BGP.

### **🔹 4. Transport Layer (Layer 4)**

- **Function:** Ensures **reliable (TCP) or fast (UDP) transmission**.
- **Devices:** Firewalls.
- **Protocols:** TCP (for reliable transmission), UDP (for speed).

### **🔹 5. Session Layer (Layer 5)**

- **Function:** Establishes and maintains **network sessions**.
- **Protocols:** NetBIOS, PPTP, SIP.

### **🔹 6. Presentation Layer (Layer 6)**

- **Function:** **Encrypts, compresses, and translates data**.
- **Protocols:** SSL/TLS (secure communication), JPEG (image format).

### **🔹 7. Application Layer (Layer 7)**

- **Function:** Provides **network services and applications**.
- **Protocols:** HTTP (web browsing), FTP (file transfer), DNS (domain resolution), SMTP (email).

---

## **📌 TCP/IP Model Layers Explained with Protocols**

### **🔹 1. Network Access Layer (OSI Layers 1 & 2)**

- **Function:** Handles physical transmission of data.
- **Protocols:** Ethernet, Wi-Fi, MAC Addressing.

### **🔹 2. Internet Layer (OSI Layer 3)**

- **Function:** Provides **IP addressing** and **packet forwarding**.
- **Protocols:** IP, ICMP, ARP, OSPF, BGP.

### **🔹 3. Transport Layer (OSI Layer 4)**

- **Function:** Ensures **data is transmitted correctly**.
- **Protocols:** TCP (error-checked), UDP (fast).

### **🔹 4. Application Layer (OSI Layers 5, 6, 7)**

- **Function:** Provides **network services**.
- **Protocols:** HTTP, FTP, DNS, SMTP.

---

## **🛠️ OSI vs. TCP/IP: Which One is Used Today?**

|**Feature**|**OSI Model (7 Layers)**|**TCP/IP Model (4 Layers)**|
|---|---|---|
|**Use Case**|Theoretical model|Practical model (used on the internet)|
|**Complexity**|More detailed, **7 layers**|Simplified, **4 layers**|
|**Example Protocols**|Ethernet, TCP, IP, HTTP|TCP, IP, HTTP, DNS|
|**Status**|Used in education & reference|Used in real-world networking|

📌 **Real-world networking follows the TCP/IP model because it is simpler and practical.** However, **the OSI model is still used for learning and troubleshooting.**


### **📌 Purpose of TCP/IP Layers in Networking**

Each layer in the **TCP/IP Model** has a **specific role** in ensuring smooth **communication between devices over networks, including the internet**.

### **1️⃣ Network Access Layer (Equivalent to OSI Layers 1 & 2)**

**🔹 Purpose:**

- This layer handles the **physical connection** between network devices.
- It ensures that data can be **transmitted and received** over cables, wireless signals, or fiber optics.
- It defines how devices **identify each other using MAC addresses**.

**🔹 Real-World Example:**

- Your **Wi-Fi router or Ethernet cable** helps connect your computer to the internet.
- When sending an email, your device’s **network card (NIC)** ensures the data is correctly transmitted through the network.

---

### **2️⃣ Internet Layer (Equivalent to OSI Layer 3)**

**🔹 Purpose:**

- This layer is responsible for **logical addressing (IP addresses)** and **routing**.
- It ensures data packets are **sent to the correct destination**, even if they travel through multiple networks.

**🔹 Real-World Example:**

- When you **visit a website**, your computer's **IP address** and the **web server’s IP address** are used to establish a connection.
- If you're in **India** and access a website hosted in **the USA**, routers use **IP routing** to send data across different networks.

---

### **3️⃣ Transport Layer (Equivalent to OSI Layer 4)**

**🔹 Purpose:**

- This layer **manages end-to-end communication** between devices.
- It ensures **data integrity and proper sequencing**.
- It uses **TCP (reliable, error-checked delivery)** or **UDP (fast, no error checking)** depending on the application.

**🔹 Real-World Example:**

- **When watching YouTube**, UDP is used because speed is more important than 100% accuracy.
- **When logging into a bank website**, TCP ensures that every bit of information is received correctly.

---

### **4️⃣ Application Layer (Equivalent to OSI Layers 5, 6, 7)**

**🔹 Purpose:**

- This is where **end-user applications** operate.
- It provides **services like web browsing, email, and file transfers**.
- It interacts with **HTTP, FTP, DNS, SMTP, etc.** to allow users to send and receive data over the network.

**🔹 Real-World Example:**

- **Web Browsing:** HTTP/HTTPS allows you to access websites.
- **Emails:** SMTP and IMAP help send and receive emails.
- **File Transfers:** FTP allows you to download/upload files.

---

### **📌 Why is the TCP/IP Model Important?**

✔ **It is the backbone of the internet and networking.**  
✔ **It allows devices from different manufacturers to communicate seamlessly.**  
✔ **It helps troubleshoot network issues using protocol layers.**  
✔ **It ensures reliable and fast data transmission worldwide.**



