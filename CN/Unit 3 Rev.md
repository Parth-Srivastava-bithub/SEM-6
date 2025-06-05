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

### 🛣 **Static Routing**

Tu khud route set karta hai – *“Jaipur jaana hai? Is road se jao!”*
Manual hai, fixed hai. Change hua to tu khud update karega.

### 🤖 **Dynamic Routing**

Router bolta hai – *“Main khud best raasta dhoond lunga”*
Jaise GPS – roads badle to auto update ho jaata hai.

---

### 📦 **Forwarding**

Packet aaya? Router bolta hai – *“Isse agle wale ko bhejta hoon”*
Just delivery ka kaam – *Next Hop* ko forward karta hai.

### 🔁 **Next Hop**

Agla router jahan packet bhejna hai.
Soch, Domino’s rider ek shop se nikalta hai, next delivery point = next hop.

### 🌐 **Network**

Destination jahan packet jaana hai – routing table me likha hota hai:
*“192.168.1.0 ke packets is raste se bhejo.”*

### 🚪 **Default**

Agar kisi network ka route pata nahi, to *“sab unknown packets yahan bhej do”*
Jaise: *“Sab unknown logon ko gatekeeper ke paas bhej do.”*


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


### 🧮 **Distance Vector Routing (DVR)**

* Har router apne **neighbour routers** ko ye batata hai:
  *“Mujhe kis network tak pahuchne me kitni distance (hops/time/cost) lagti hai.”*

* **Example**:

  * Router A bolta hai: "Mujhe Network X tak 2 hops lagte hain."
  * Router B sunta hai aur bolta: "Agar mujhe A tak 1 hop lagta hai, to X tak 3 hops lagengi via A."

* **Matlab**: Har router ek *chhoti si table* banata hai:

  * Destination → Distance → Next Hop

* Ye process bar-bar repeat hoti hai jab tak sab routers ke paas best distances aa jaate hain.

* **Limitation**: Slow updates, kabhi-kabhi loop bhi ban jaate hain (Count to infinity problem).

Iska dimaag simple hai: **"Bas mujhe bata tu kitni door hai, mai dekh leta hoon kaunsa best raasta hai."**

---

### 🗺️ **Link State Routing**

* Har router apne nearby routers ka **complete map** banata hai:
  *“Mere aas-paas ye routers hain, aur un tak ye cost hai.”*

* Phir sab routers apna yeh map **sabko bhejte hain** (flooding se).

* Sab routers ke paas same map hota hai → **Har router khud best path calculate karta hai** (Dijkstra use karke).

📌 Jaise Google Maps: Har banda khud best route nikaalta hai full map dekh ke.

---

### 📡 **Multicast Routing**

* Ek hi data ko **multiple selected receivers** ko bhejna hai.

📌 Jaise online class – sirf jo students group me hain unko lecture milega, sabko nahi.

* Efficient hai: **na to sabko bhejna padta, na baar-baar same data.**

---

### 📢 **Broadcast Routing**

* Ek message **poore network me sabko** bhejna hai.

📌 Jaise loudspeaker announcement – sab log sunenge, chaahe unko zarurat ho ya nahi.

* Used in: ARP requests, initial DHCP request, etc.



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
---




### 🌐 **Network Layer**

**Kaam kya?** Packet ko ek network se doosre network tak le jaana.

#### 📍 **Routing**

Best raasta decide karta hai jisse packet destination tak jaaye.

#### 🧠 **Logical Addressing**

IP address assign karta hai — har device ka unique pehchaan.

#### 🔗 **Internetworking**

Alag-alag networks ko jodta hai ek bade Internet me.

#### ✂️ **Fragmentation**

Agar packet bada ho, to usko chhote tukdon me tod deta hai – fir receiver pe jod deta hai.

---

### 🧍‍♂️ **Point-to-Point Network**

Sirf do devices directly connected — no switch, no router.

---

### ⚙️ **Basic Internetworking**

#### 🌍 **IP (Internet Protocol)**

Jo rules banata hai ki packet kaise travel kare network ke across.

##### 🎯 **IP Address Classes**

Divide karte hain networks ko size ke basis pe.

* **Class A** – Big companies (1.0.0.0 – 126.x.x.x)
* **Class B** – Medium orgs (128.0.0.0 – 191.x.x.x)
* **Class C** – Small businesses (192.0.0.0 – 223.x.x.x)
* **Class D** – Multicast (224.x.x.x – 239.x.x.x)
* **Class E** – Research & Reserved (240.x.x.x – 255.x.x.x)

---

### ✂️ **CIDR (Classless Inter-Domain Routing)**

Class ke bina IP dena – jaise `/24` ka matlab 256 IPs. Zyada flexible hai.

---

### 📣 **ARP (Address Resolution Protocol)**

IP se MAC address nikalta hai – jaise GPS se exact house location lena.

---

### 🧙‍♂️ **DHCP (Dynamic Host Config Protocol)**

Automatically har device ko IP, Gateway, DNS assign karta hai – bina manual setting.

---

### 📬 **ICMP (Internet Control Message Protocol)**

Error ya status batane ke liye use hota hai – jaise ping ka reply.

---

### 🔁 **RARP (Reverse ARP)**

MAC address se IP nikalta hai – ab rarely use hota hai.

---

### 🧩 **Subnetting**

Bade network ko chhoti logical parts me todna – management easy hota hai.

#### 🛠️ **Fixed Length**

Sab subnet same size ke hote hain.

#### 🧠 **Variable Length**

Alag-alag size ke subnet – zyada efficient.

---

### 📦 **IPv4**

* **Version** – Header ka pehla field batata hai ki IPv4 use ho raha hai.
* **Header** – Meta info store karta hai jaise source, destination, length, checksum.
* **Services** – QoS define karta hai; kis packet ko priority milegi.
* **Total Length** – Packet ka total size in bytes batata hai.
* **Identification** – Fragmented packets ko ek group me pehchaanne ke liye.
* **Flags** – Packet me fragmentation allowed hai ya nahi, yeh batata hai.
* **Header Checksum** – Header sahi hai ya corrupted, yeh verify karta hai.
* **Source Address** – Packet kahan se aaya, uska IP address.
* **Destination Address** – Packet ko kahan jaana hai, uska IP address.

---

### 🌐 **IPv6**

* **Version** – 6 likha hota hai to bata chal jaata hai IPv6 hai.
* **Traffic Class** – Packet ki priority aur QoS control karta hai.
* **Flow Label** – Same stream ke packets ko identify karta hai (streaming, video etc).
* **Payload Length** – Data part ka size batata hai.
* **Next Header** – Next protocol (TCP, UDP, etc.) ka pointer.
* **Hop Limit** – Max routers tak jaa sakta hai packet; TTL ka upgraded version.

---

### 🔁 **IPv4 vs IPv6**

* IPv4 = 32-bit address (4.3 billion), IPv6 = 128-bit (infinite practically).
* IPv6 me built-in security, fast routing & no need for NAT.

---

### 📨 **ICMP**

* **Kya hai?** Control protocol for reporting errors (e.g., ping, unreachable).
* **Uses** – Diagnostics, packet loss, unreachable errors dikhana.
* **Error Reporting** – Notify karta hai agar packet deliver nahi ho paya.
* **Query Management** – Info requests ka jawab deta hai (like ping echo/reply).

---

### 🛣️ **Routing**

* **Static Routing** – Manually set routes; stable but not adaptive.
* **Dynamic Routing** – Routers khud se best path discover karte hain (like GPS).

---

### 📦 **Forwarding**

* **Next Hop** – Agla router jisko packet bhejna hai.
* **Network** – Destination network jiska route table me entry hai.
* **Default** – Jab koi match na mile, to ek default route follow hota hai.

---

### 🚚 **Delivery**

* **Direct** – Sender & receiver same network me hain, router nahi chahiye.
* **Indirect** – Beech me ek ya zyada routers se packet jaata hai.

---

### 💡 **The Optimality Principle**

* Best route wo hota hai jiska **cost** (delay, hops, etc.) minimum ho.
* Har routing algorithm isi principle pe based hota hai.

---

### 📍 **Shortest Path Algorithm (Dijkstra)**

* Source se sab destinations tak ka shortest path nikaalta hai.
* Har node ka cost calculate karke minimum cost wale path pe bhejta hai.

---

### 🌊 **Flooding**

* Har packet ko har outgoing link pe bhejta hai (except incoming se).
* Redundant & heavy, but guarantees delivery.

---

### 📏 **Distance Vector Routing**

* Har router neighbours ko bolta hai: "Mujhe X tak itna lagta hai."
* Based on *Bellman-Ford algorithm*, but slow updates & loops possible.

---

### 🗺️ **Link State Routing**

* Har router full map banata hai aur sabko bhejta hai.
* Khud Dijkstra laga ke best path calculate karta hai.

---

### 📡 **Multicast Routing**

* Ek hi data ko selected group tak bhejna – sabko nahi.
* Efficient for conferencing, live stream, etc.

---

### 📢 **Broadcast Routing**

* Data saare network me bhej diya jaata hai – sab devices ko.
* Used in DHCP, ARP, etc.

---

### 🔥 **Congestion**

* Jab network me zyada traffic aa jaye to slow, drop hone lagta hai.
* Control karna important hai to avoid overload.

---

### 🛠 **Congestion Control**

#### 🔓 **Open Loop**

* **Retransmission** – Lost packets ko firse bhejna.
* **Window** – Sliding window adjust karke traffic control karte hain.

#### 🔐 **Closed Loop**

* **Back Pressure** – Downstream router upstream ko slow hone ko bolta hai.
* **Choke Packet** – Special warning packet bheja jaata hai sender ko slow karne ke liye.

---

### 🧪 **QoS (Quality of Service)**

* **Reliability** – Packet loss kam ho.
* **Delay** – Timely delivery ho.
* **Jitter** – Variation in delay kam ho.
* **Bandwidth** – Enough speed ho required data ke liye.

---

### 🪣 **Congestion Algorithms**

* **Leaky Bucket** – Data fixed rate se nikalta hai – overflow drop ho jaata hai.
* **Token Bucket** – Tokens collect karo, fir data bhejo – more flexible than leaky.

---
