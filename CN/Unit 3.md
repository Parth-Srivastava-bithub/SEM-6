## 🌐 **Network Layer – Short Notes (3–5 line explanation for each topic)**

---

### 🔸 1. **Point-to-Point Networks**

* Ye ek direct communication hota hai do devices ke beech.
* Sirf 1 sender aur 1 receiver involved hote hain.
* Common example: Serial cable se connected PC aur router.
* Simple aur reliable hota hai but scalable nahi.

---

### 🔸 2. **Logical Addressing**

* Network layer logical (IP) address ka use karti hai, jo globally unique hota hai.
* IP address 2 parts ka hota hai: network ID + host ID.
* Ye address independent hota hai hardware (MAC) se.
* IPv4 (32-bit), IPv6 (128-bit) versions available hain.

---

### 🔸 3. **IP (Internet Protocol)**

* IP packets ko source se destination tak bhejta hai.
* It is **connectionless** and **best-effort delivery** karta hai (no guarantee).
* Do versions hain: IPv4 & IPv6.
* Header mein source, destination IP, TTL, version hota hai.

---

### 🔸 4. **CIDR (Classless Inter-Domain Routing)**

* IP addresses ko efficiently allocate karne ka method hai.
* Format: `IP/prefix_length` (e.g., 192.168.1.0/24).
* Ye IP classes (A, B, C) ko replace karta hai.
* Routing table size reduce karta hai.

---

### 🔸 5. **ARP (Address Resolution Protocol)**

* IP address se MAC address find karta hai.
* ARP request broadcast hoti hai; ARP reply unicast hoti hai.
* Used in IPv4-based LANs.
* Layer 3 to Layer 2 address mapping karta hai.

---

### 🔸 6. **RARP (Reverse ARP)**

* MAC address se IP address find karta hai.
* Mainly diskless devices ke liye use hota tha.
* Ab obsolete ho chuka hai; replaced by DHCP.
* Works opposite to ARP.

---

### 🔸 7. **DHCP (Dynamic Host Configuration Protocol)**

* Devices ko automatically IP, subnet mask, gateway, DNS assign karta hai.
* DHCP Discover → Offer → Request → Acknowledge (DORA process).
* Server-based system hota hai.
* Temporary (leased) IP deta hai.

---

### 🔸 8. **ICMP (Internet Control Message Protocol)**

* Diagnostic aur error-reporting protocol hai.
* Ping aur traceroute jaise tools isi pe based hain.
* Agar destination unreachable ho to ICMP message bhejta hai.
* Works with IP but is not a transport protocol.

---

### 🔸 9. **Routing**

* Packet ko best path se destination tak le jane ka process.
* Routing table mein IP aur next-hop address store hota hai.
* Static ya dynamic routing protocols ka use hota hai.
* Internet ka backbone routing pe hi depend karta hai.

---

### 🔸 10. **Forwarding and Delivery**

* Forwarding: Packet ko next-hop tak bhejna based on routing table.
* Delivery: End-to-end transmission from source to final destination.
* Forwarding fast hota hai; routing relatively slow.
* Routers is process ko handle karte hain.

---

### 🔸 11. **Static Routing**

* Routes manually set kiye jaate hain by admin.
* Simple but fail-safe nahi; link down hone pe reroute nahi hota.
* Chhote networks ke liye suitable hai.
* No overhead, lekin manual configuration zaroori.

---

### 🔸 12. **Dynamic Routing**

* Routers automatically route discover karte hain via protocols.
* Self-healing: Agar ek link fail ho jaye to alternative path lete hain.
* Protocols: RIP, OSPF, BGP.
* Scalable and adaptable to big networks.

---

### 🔸 13. **Routing Algorithms**

#### a. **Distance Vector:**

* Routers apne neighbors ko apni distance table bhejte hain.
* Count-to-infinity problem hoti hai.
* Protocol: RIP

#### b. **Link State:**

* Routers network ki poori map bana lete hain.
* Flooding and Dijkstra algorithm ka use hota hai.
* Protocol: OSPF

---

### 🔸 14. **Routing Protocols**

* **RIP**: Distance vector protocol, max hop count = 15.
* **OSPF**: Link state protocol, fast and hierarchical.
* **BGP**: Used in internet-level routing between ISPs (Path Vector).
* Ye protocols dynamic routing enable karte hain.

---

### 🔸 15. **Congestion Control Algorithms**

#### a. **Leaky Bucket:**

* Fixed rate pe packets bhejta hai; burst traffic ko smooth karta hai.
* Queue full hone pe packets drop hote hain.

#### b. **Token Bucket:**

* Packets tabhi send ho sakte hain jab token available ho.
* Burst traffic allow karta hai.

#### c. **RED (Random Early Detection):**

* Congestion se pehle random packets drop karta hai.
* TCP sender slow ho jata hai (congestion avoidance).

---

### 🔸 16. **IPv6**

* IPv6 is 128-bit address system with huge address space (2¹²⁸).
* No need for NAT; supports auto-configuration & better security.
* Format: Hexadecimal, e.g., `2001:0db8:85a3::8a2e:0370:7334`
* Simplified header structure for faster routing.
* Required due to IPv4 address exhaustion.

---


