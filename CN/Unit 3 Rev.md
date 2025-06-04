### **Network Layer**

* **Routing**: Data packets ko source se destination tak best path se bhejna.
* **Logical Addressing**: Devices ko unique IP addresses assign karna.
* **Internetworking**: Multiple networks ko jodna to act as a single network.
* **Fragmentation**: Large packets ko chhote parts mein todna for transmission.

---

### **Point to Point Network**

* **Point to Point**: Direct connection between two devices for data transfer.

---

### **Basic Internetworking**

#### **IP**

* **IP Address Classes**: IPs categorized as A, B, C, D, E based on size and use.

  * **Class A**: For very large networks (1-126.x.x.x)
  * **Class B**: For medium networks (128-191.x.x.x)
  * **Class C**: For small networks (192-223.x.x.x)
  * **Class D**: For multicast (224-239.x.x.x)
  * **Class E**: Reserved for future/research (240-255.x.x.x)

* **CIDR**: Removes class concept, allows flexible IP ranges using slash notation.

* **ARP**: Resolves IP address to MAC address.

* **DHCP**: Automatically assigns IP addresses to devices.

* **ICMP**: Helps report errors and diagnose network issues.

* **RARP**: Converts MAC address to IP address (opposite of ARP).

* **Subnetting**: Divides a large network into smaller sub-networks.

  * **Fixed Length**: All subnets have equal number of hosts.
  * **Variable Length**: Subnets can have different sizes based on need.

---

### **IPv4**

* **Version**: Indicates IP version (IPv4 = 4).
* **Header**: Contains control information for delivery.
* **Services**: Includes fragmentation, error handling, addressing.
* **Total Length**: Total size of the packet (header + data).
* **Identification**: Unique ID for packet fragments.
* **Flags**: Used to control and identify fragments.
* **Header Checksum**: Error-checking for the header.
* **Source Address**: IP address of sender.
* **Destination Address**: IP address of receiver.

---

### **IPv6**

* **Version**: Indicates IP version (IPv6 = 6).
* **Traffic Class**: Priority of packet.
* **Flow Label**: Identifies flow of packets needing special handling.
* **Payload Length**: Length of data excluding header.
* **Next Header**: Type of next header (like TCP/UDP).
* **Hop Limit**: Max hops before packet is discarded (like TTL).

---

### **IPv4 vs IPv6**

* IPv6 provides larger address space, better security, and simplified headers compared to IPv4.

---

### **ICMP**

* **What is it?**: Control protocol for sending error and status messages.
* **Uses**: Ping, traceroute, and error messaging.
* **Error Reporting**: Informs sender about delivery issues.
* **Query Management**: Helps diagnose network behavior via echo and reply.

---

### **Routing**

* **Static Routing**: Manually configured routes.
* **Dynamic Routing**: Routers automatically discover and update paths.
* **Forwarding**: Sending packet to next hop toward destination.

  * **Next Hop**: Immediate router to forward packet.
  * **Network**: Destination network in routing table.
  * **Default**: Used when no specific route matches.

---

### **Delivery**

* **Direct**: Sender and receiver are on the same network.
* **Indirect**: Packet travels through one or more routers.

---

### **The Optimality Principle**

* Best path minimizes overall cost (e.g., delay, hops, etc.).

---

### **Shortest Path Algorithm**

* **Dijkstra**: Finds the shortest path from source to all other nodes.

---

### **Flooding**

* Every incoming packet is sent out on all outgoing links (except incoming).

---

### **Distance Vector Routing**

* Routers share distance to all known networks with neighbors.

---

### **Link State Routing**

* Routers share entire network topology info and compute best paths.

---

### **Multicast Routing**

* Delivers data to a group of destinations efficiently.

---

### **Broadcast Routing**

* Sends data to all nodes in the network.

---

### **Congestion**

* **Control**: Techniques to prevent or handle network overload.

  * **Open Loop**:

    * **Retransmission**: Resend lost packets.
    * **Window**: Controls data in transit to avoid overload.
  * **Closed Loop**:

    * **Back Pressure**: Source slowed down if network is congested.
    * **Choke Packet**: Receiver sends warning to slow data flow.

---

### **QoS (Quality of Service)**

* **Reliability**: Delivery without loss.
* **Delay**: Time taken for data to reach.
* **Jitter**: Variability in delay.
* **Bandwidth**: Data capacity of the link.

---

### **Congestion Algorithms**

* **Leaky Bucket**: Fixed-rate output, smoothens traffic burst.
* **Token Bucket**: Allows bursty traffic up to certain limit using tokens.

---

