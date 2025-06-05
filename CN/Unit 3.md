## 🔹 **Network Layer (3rd Layer of the OSI Model)**

### 📌 What does it do?

# **Network Layer**

The Network Layer's job is to send data from one device to another, whether they are on the same network or different networks. This layer handles routing, addressing, internetworking, and data fragmentation. Routing means choosing the best path to send data. Logical addressing gives each device a unique identifier, such as an IP address. Fragmentation occurs when a data packet is too large and needs to be broken into smaller pieces.

---

## 1. **Routing**

Routing is the process where network devices (routers) decide which path data packets should take to reach their destination quickly. This process can be dynamic or static, using routing tables and algorithms. Routing ensures network traffic is efficient and avoids congestion. It optimizes data delivery. The routing path is determined based on network topology.

**Example:**  
Imagine traveling from Delhi to Mumbai—you need to find the shortest and fastest route. GPS performs routing. In a network, a router sends packets via A → B → C. If one route fails, the router finds an alternate path.

---

## 2. **Logical Addressing**

Logical addressing means assigning a unique address to each device for identification within the network. This address is different from a hardware (MAC) address and is in the form of an IP address. Logical addresses enable communication between devices, regardless of their location in the network. These addresses follow a hierarchical structure, like network and host parts. Addressing is essential for the Network Layer.

**Example:**  
Just as your home has a unique address, a computer has an IP address like 192.168.1.5. When you visit a website, your device sends its logical address, telling internet routers where to send the packet.

---

## 3. **Internetworking**

Internetworking means connecting different networks so they can communicate. This is the basic concept of the internet, where multiple networks combine to form a larger one. Internetworking uses routers and gateways to connect different protocols. It ensures data packets travel smoothly from one network to another. The Network Layer uses the IP protocol for internetworking.

**Example:**  
Your mobile’s Wi-Fi network and your internet service provider’s network are connected. When you send an email, it travels from your network to the internet. Without internetworking, devices on different networks couldn’t connect.

---

## 4. **Fragmentation**

Fragmentation happens when a data packet is too large for a network device to accept. The data is broken into smaller pieces called fragments, which the receiver reassembles into the original data. This process reduces data loss and errors. Fragmentation maintains network efficiency and is used in protocols like IP.

**Example:**  
If you send a large video file that can’t fit in one packet, it’s split into smaller packets. Each packet is sent separately, and the receiver combines them to recreate the video.

---

## 5. **Point-to-Point Network**

A point-to-point network is a direct connection between two devices without any intermediate devices. It provides simple and fast communication. This type of network is used in leased lines, telephone calls, or serial connections. Data transfer is reliable because it travels over a fixed line. Point-to-point networks can be local or wide area.

**Example:**  
A direct leased line connection between your home and office. A USB cable connecting two computers. A telephone call is also a point-to-point network.

---

# **Basic Internetworking**

---

## 1. **IP (Internet Protocol)**

The IP protocol is the main Network Layer protocol that handles addressing and routing to send data packets from source to destination. IP addresses are part of logical addressing, giving each device a unique identifier. IPv4 and IPv6 are common versions. IP finds the best path to route packets. IP is a connectionless protocol, meaning packets travel independently.

---

### IP Address Classes

IP addresses are divided into classes based on network size and usage:

* **Class A:** For large networks (1.0.0.0 to 126.255.255.255), e.g., 10.0.0.1  
* **Class B:** Medium networks (128.0.0.0 to 191.255.255.255), e.g., 172.16.0.1  
* **Class C:** Small networks (192.0.0.0 to 223.255.255.255), e.g., 192.168.1.1  
* **Class D:** For multicast (224.0.0.0 to 239.255.255.255), e.g., 224.0.0.1  
* **Class E:** Reserved for future use (240.0.0.0 to 255.255.255.255)  

**Example:**  
A large company uses a Class A IP address. A small school network uses Class C. Multicast TV broadcasts use Class D.

---

## 2. **CIDR (Classless Inter-Domain Routing)**

CIDR is a flexible IP addressing scheme that allocates IP addresses efficiently without fixed classes. IP addresses are written with prefixes, like 192.168.0.0/24. CIDR optimizes address space and reduces routing table size, overcoming limitations of class-based addressing.

**Example:**  
192.168.1.0/28 means 16 addresses in a group. A company can divide its network into smaller subnets, saving IP addresses.

---

## 3. **ARP (Address Resolution Protocol)**

ARP converts logical IP addresses to physical MAC addresses for local network communication. When a device needs to send a packet to an IP address, it sends an ARP request to get the MAC address. This is essential for LAN communication.

**Example:**  
If your computer wants to send data to 192.168.1.20, it first sends an ARP request: “What is the MAC address for 192.168.1.20?” The packet is then sent physically using the MAC address.

---

## 4. **DHCP (Dynamic Host Configuration Protocol)**

DHCP automatically assigns IP addresses and network settings to devices, eliminating manual configuration. When a device joins a network, it requests an IP lease from the DHCP server. DHCP simplifies network management, especially in large networks.

**Example:**  
When your phone connects to Wi-Fi, it automatically gets an IP from DHCP. Offices use DHCP to assign IPs to new devices, preventing IP conflicts.

---

## 5. **ICMP (Internet Control Message Protocol)**

ICMP is used for error messages and diagnostics between network devices. It reports issues like unreachable destinations, time exceeded, and ping responses. ICMP helps monitor network health.

**Example:**  
The `ping` command uses ICMP to check if a device is reachable. If a website is down, ICMP sends an unreachable message. Traceroute also uses ICMP packets.

---

## 6. **RARP (Reverse Address Resolution Protocol)**

RARP finds an IP address from a MAC address. It helps devices discover their IP at startup. RARP is rarely used now, as DHCP has replaced it.

**Example:**  
A network printer or booting computer uses RARP to find its IP. Older systems commonly used this.

---

## 7. **Subnetting**

Subnetting divides a large network into smaller subnets for better management and security. There are two types:

* **Fixed Length Subnetting (FLSM):** All subnets are equal in size.  
* **Variable Length Subnetting (VLSM):** Subnets vary in size, using address space efficiently.  

**Example:**  
A company divides its network by department. FLSM gives equal IPs to all departments. VLSM assigns more IPs to IT and fewer to HR.

---

### 1. **Fixed Length Subnetting**

#### ➤ All subnets are the same size.

#### ➤ Example:

Dividing 192.168.1.0/24 into 4 parts:

* 192.168.1.0/26  
* 192.168.1.64/26  
* 192.168.1.128/26  
* 192.168.1.192/26  

---

### 2. **Variable Length Subnetting (VLSM)**

#### ➤ Subnets are created in different sizes based on need.

#### ➤ Example:

* One subnet needs 100 hosts → /25  
* Another needs only 10 hosts → /28  

✅ **VLSM** is efficient because IPs aren’t wasted.

---

## 🔷 **IPv4 (Internet Protocol Version 4)**

### 📌 What is it?

IPv4 is a **network protocol** that gives devices a **unique address** (e.g., 192.168.1.1) to ensure data reaches the right destination.

### ➤ Format:

IPv4 address: `32-bit` (e.g., `192.168.0.1`)

---

### ✅ **IPv4 Header (Structure)**

The IPv4 packet has a **header** containing important information routers use to forward data.

#### 1. **Version**

* 4-bit field  
* Indicates **IPv4** (value: `4`)  

#### 2. **Header Length**

* Shows header size (minimum 20 bytes)  

#### 3. **Services (Type of Service or DSCP)**

* Indicates priority (e.g., video call = high, file download = low)  
* Modern networks use **DSCP (Differentiated Services Code Point)**  

#### 4. **Total Length**

* Entire IPv4 packet size (header + data)  
* Max: `65,535 bytes`  

#### 5. **Identification**

* Unique ID for each packet  
* Helps reassemble fragmented packets  

#### 6. **Flags**

* 3 bits:  
  * **DF (Don’t Fragment):** Do not fragment  
  * **MF (More Fragments):** More fragments are coming  
  * 1 reserved bit  

#### 7. **Header Checksum**

* Verifies header integrity (error detection)  
* Every router checks this  

#### 8. **Source Address**

* Sender’s IP  

#### 9. **Destination Address**

* Receiver’s IP  

---

## 🔷 **IPv6 (Internet Protocol Version 6)**

### 📌 What is it?

IPv6 is an **updated version** of IPv4 with **more addresses** and **better security & performance**.

### ➤ Format:

IPv6 address: `128-bit` (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`)  

---

### ✅ **IPv6 Header (Simplified compared to IPv4)**

#### 1. **Version**

* 4-bit value (value: `6`) → indicates IPv6 packet  

#### 2. **Traffic Class**

* For QoS (Quality of Service) — similar to IPv4’s Type of Service  

#### 3. **Flow Label**

* Tracks special packets (e.g., video/audio) with a unique flow  

#### 4. **Payload Length**

* Actual data size (excluding header), in bytes  

#### 5. **Next Header**

* Indicates the next protocol (TCP, UDP, ICMPv6, etc.)  

#### 6. **Hop Limit**

* Maximum hops a packet can take — each router decrements this  
* Called **TTL (Time to Live)** in IPv4  

#### 7. **Source Address**

* Sender’s 128-bit IPv6 address  

#### 8. **Destination Address**

* Receiver’s 128-bit IPv6 address  

---

## 🔶 **IPv4 vs IPv6 – Comparison Table**

| Feature               | IPv4                       | IPv6                           |
| --------------------- | -------------------------- | ------------------------------ |
| **Address Size**      | 32-bit (e.g., 192.168.1.1) | 128-bit (e.g., 2001:db8::1)    |
| **Total Addresses**   | ~4.3 billion               | ~3.4×10³⁸ (almost unlimited)   |
| **Header Size**       | 20–60 bytes                | Fixed 40 bytes                 |
| **Configuration**     | Manual or DHCP             | Auto-configuration supported   |
| **Security**          | Optional (via IPsec)       | Mandatory (IPsec built-in)     |
| **Fragmentation**     | Routers & Sender           | Only sender                    |
| **Checksum**          | Yes                        | No (handled by upper layers)   |
| **Broadcast Support** | Yes                        | No (uses multicast instead)    |
| **Example Address**   | 192.168.1.1                | 2001:0db8:85a3::8a2e:0370:7334 |

---

### ✅ **Summary in Simple Words:**

| IPv4                              | IPv6                              |
| --------------------------------- | --------------------------------- |
| Older version, limited addresses  | New version, unlimited addresses  |
| Smaller header                    | Simplified but bigger header      |
| More manual settings              | More automation                   |
| Security optional                 | Security built-in                 |

---

## 🔷 **ICMP (Internet Control Message Protocol)**

### ✅ **What is it?**

ICMP is a **network protocol** that sends **messages** when there’s an **error** or when network **information** is needed.

> 🧠 ICMP is not for data transfer but for **checking network conditions**.

### ✅ **Uses of ICMP**

1. **Error Reporting** (sending messages when something goes wrong)  
2. **Query Management** (e.g., checking device status)  

---

### 📌 **1. Error Reporting**

ICMP informs routers or hosts if:

* Destination is unreachable  
* TTL expires  
* Fragmentation fails  

#### 🔹 Example:

Sending a message to a wrong IP → router sends:  
**"Destination Unreachable"**.  

🧾 Common ICMP Error Messages:

* **Destination Unreachable**  
* **Time Exceeded**  
* **Parameter Problem**  

---

### 📌 **2. Query Management**

ICMP queries help check network status. Devices send requests to each other.

#### 🔹 Example:

When you use **`ping`**, your computer sends an ICMP echo request, and the destination replies.  

🧾 Common ICMP Query Messages:

* **Echo Request / Reply** (used in `ping`)  
* **Timestamp Request / Reply**  

---

## 🔷 **Routing**

### ✅ **What is Routing?**

Routing means choosing the **best path** for data to travel efficiently from source to destination.

📍 **Routers** do this using routing tables.

---

# **Routing**

Routing is the process where network devices (like routers) send data packets from source to destination. Routing decides which path packets take to reach quickly and efficiently. There are two main types—**Static Routing** and **Dynamic Routing**.

---

## 1. **Static Routing**

In static routing, a network administrator manually configures routes on routers. Routes are fixed and don’t change automatically. This is useful for small, simple networks. Static routing is fast because the routing table isn’t updated, but manual updates are needed if the network changes.

**Example:**  
A small company has 3 offices manually connected. If one office’s network changes, the admin must manually update routers. This is static routing.

---

## 2. **Dynamic Routing**

In dynamic routing, routers share routing information and automatically find the best paths. This is useful for large, complex networks. Dynamic routing uses protocols like RIP, OSPF, and BGP. The advantage is that network changes update automatically.

**Example:**  
On the internet, different networks use dynamic routing protocols to update routes. If a link fails, routers find alternate paths automatically.

---

# **Forwarding**

Forwarding means sending incoming data packets to the correct output interface so they reach their destination.

Routers use **routing tables** for forwarding decisions, which include:

---

### 1. **Next Hop**

Next Hop is the next device or router to which the packet is sent. The router knows which device to forward the packet to next.

**Example:**  
If a packet is at Router A and needs to go to Router B, then B is the next hop for A.

---

### 2. **Network**

A network is an IP range representing a subnet. Each routing table entry is a network the router knows.

**Example:**  
192.168.1.0/24 is a network with 256 IP addresses.

---

### 3. **Default**

The default route is used when no specific route is found. Routers call this the "gateway of last resort." If no matching network is found, the packet is sent via the default route.

**Example:**  
If a router doesn’t know the route for 10.10.10.5, it sends the packet via the default route.

---

# **Delivery**

Delivery means physically sending packets to the destination device. There are two types:

---

### 1. **Direct Delivery**

Direct delivery happens when source and destination are on the same network/subnet. Packets are sent directly without intermediate devices.

**Example:**  
If your computer and printer are on the same office network, data is sent directly to the printer.

---

### 2. **Indirect Delivery**

Indirect delivery happens when source and destination are on different networks. Packets first go to a router, which forwards them to the destination network.

**Example:**  
When your home computer accesses a website, data first goes to your router, which sends it to the website’s server.

---

## 🔚 **Quick Summary Table**

| Term                 | Meaning                                                   |
| -------------------- | --------------------------------------------------------- |
| **ICMP**             | Protocol for network errors and test messages             |
| **Error Reporting**  | ICMP reports packet delivery issues                       |
| **Query Management** | ICMP checks network status (`ping`, etc.)                 |
| **Routing**          | Choosing the best path for data                           |
| **Static Routing**   | Manually set routes                                       |
| **Dynamic Routing**  | Automatically chooses the best path                       |
| **Forwarding**       | Sending packets to the next device                        |
| **Next Hop**         | The next router                                           |
| **Default**          | General path used when no specific route exists           |
| **Delivery**         | Getting packets to their destination                      |
| **Direct**           | Same network                                              |
| **Indirect**         | Different networks (via routers)                          |

---

# **The Optimality Principle**

The Optimality Principle states that if the shortest path from Router A to Router C passes through Router B, then the path from B to C is also the shortest. This means every intermediate node selects the best route, helping routing algorithms make efficient decisions.

**Example:**  
If the shortest Delhi-Mumbai route passes through Jaipur, then Jaipur-Mumbai is also the shortest. Routers update their tables accordingly.

---

# **Shortest Path Algorithm**

The Shortest Path Algorithm finds the smallest (shortest) and best path for data in a network.

---

## **Dijkstra’s Algorithm**

Dijkstra’s algorithm finds the shortest path from each node to the destination. It calculates distances and selects the path with the minimum distance. Used in link-state routing protocols.

**Example:**  
A graph with 4 connected cities—Dijkstra’s algorithm finds the shortest Delhi-Mumbai route. Each connection has a weight (distance/time), and the algorithm picks the path with the lowest sum.

---

# **Flooding**

Flooding is a simple routing technique where a router sends every incoming packet to all interfaces except the one it came from. The advantage is guaranteed delivery, but it increases network traffic (overhead).

**Example:**  
Sending a message to everyone without knowing the route—like broadcasting in a group chat.

---

# **Distance Vector Routing**

In distance vector routing, each router shares its routing table (with network distances) with neighbors. Routers update tables when neighbors have new routes. This algorithm converges slowly and has a count-to-infinity problem.

**Example:**  
RIP (Routing Information Protocol) uses distance vector routing. Router A tells neighbors a network is 5 hops away. Neighbors share their data, and all update their tables.

---

# **Link State Routing**

In link-state routing, each router broadcasts its directly connected links’ status to all routers. All routers know the full network topology and use Dijkstra’s algorithm to find the shortest path. Fast and reliable.

**Example:**  
OSPF (Open Shortest Path First) uses link-state routing. Each router shares its connections, and all build the same network map.

---

# **Multicast Routing**

Multicast routing efficiently sends data from one source to multiple selected destinations (group). Unlike broadcast, data goes only to interested devices.

**Example:**  
Live sports streaming—only users watching get the data.

---

# **Broadcast Routing**

Broadcast routing sends data packets to all devices on a network. Used in local networks (e.g., ARP requests).

**Example:**  
Your computer asking the network, “Who has IP 192.168.1.5?” is a broadcast.

---

# **Congestion**

Congestion occurs when network traffic exceeds capacity, causing delays and packet loss.

---

## **Congestion Control**

Congestion control techniques prevent network overload and ensure smooth traffic flow.

---

### Open Loop Congestion Control

Open loop control applies measures before congestion happens.

* **Retransmission:** Lost packets are resent.  
* **Window:** Flow control manages how many packets are sent at once.  

**Example:**  
TCP uses retransmission and sliding windows for reliability.

---

### Closed Loop Congestion Control

Closed loop control reacts after detecting congestion.

* **Back Pressure:** A congested switch signals upstream devices to stop traffic.  
* **Choke Packet:** A router sends a special packet asking the source to slow down.  

**Example:**  
A busy router sends a choke packet to reduce data speed.

---


# **QoS (Quality of Service)**

QoS ensures high-quality data transmission, especially for real-time apps like video calls, gaming, and VoIP where delay or loss is unacceptable. Key QoS parameters:

---

## 1. **Reliability**

Reliability means data is delivered correctly without loss. Reliable networks retransmit lost packets. TCP ensures reliability.

**Example:**  
If an email packet is lost, it’s resent automatically.

---

## 2. **Delay**

Delay is the time taken for a packet to reach its destination. Low delay means a fast network. Critical for real-time apps.

**Example:**  
High delay in video calls causes gaps in conversation.

---

## 3. **Jitter**

Jitter is delay variation—packets arriving inconsistently. Causes issues in real-time streaming.

**Example:**  
High jitter in online games makes movements irregular.

---

## 4. **Bandwidth**

Bandwidth is the network’s data transfer capacity. Higher bandwidth means more data can be handled.

**Example:**  
A 100 Mbps internet connection lets you download 100 Mbps per second. HD streaming needs good bandwidth.

---

# **Congestion Algorithms**

Congestion algorithms control traffic to prevent congestion and ensure smooth data flow. Two popular algorithms:

---

## 1. **Leaky Bucket Algorithm**

The Leaky Bucket regulates traffic like water leaking from a bucket. If the bucket overflows, excess packets are dropped. It maintains a constant flow rate.

**Example:**  
Filling a leaky pipe—if too much water is poured, it overflows. Similarly, excess packets are dropped.

---

## 2. **Token Bucket Algorithm**

Tokens are generated at a fixed rate. A packet needs a token to be sent. If no tokens are available, packets wait. Allows bursty traffic.

**Example:**  
Tokens are like pool passes—if available, you enter immediately; otherwise, you wait. Handles sudden traffic bursts.

---

