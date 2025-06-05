## 🔹 **Network Layer (OSI Model ka 3rd layer)**

### 📌 Kya karta hai?

# **Network Layer**

Network layer ka kaam hota hai data ko ek device se doosri device tak bhejna, chahe wo same network mein ho ya alag-alag networks mein. Ye layer routing, addressing, internetworking aur data fragmentation handle karti hai. Routing ka matlab hota hai best path chunna data bhejne ke liye. Logical addressing se har device ko unique pehchaan milti hai, jaise IP address. Fragmentation tab hoti hai jab data packet bohot bada ho aur use chhote tukdon mein todna padta hai.

---

## 1. **Routing**

Routing process hota hai jisme network devices (routers) decide karte hain ki data packets ko kaunse raaste se bhejna chahiye taaki wo sabse jaldi destination tak pahunch jayein. Ye process dynamic ya static ho sakta hai, jisme routing tables aur algorithms ka use hota hai. Routing ensures network traffic efficient rahe aur congestion na ho. Ye data delivery ko optimize karta hai. Network topology ke hisaab se routing path tayar hota hai.

**Example:**
Maan lijiye Delhi se Mumbai jaana hai, aapko shortest aur fastest raasta dhoondhna hai, toh GPS routing karta hai. Network mein router packets ko A → B → C ke through bhejta hai. Agar ek route bandh ho jaye toh router alternate route dhoondta hai.

---

## 2. **Logical Addressing**

Logical addressing ka matlab hai har device ko ek unique address assign karna jo network ke andar usse pehchane. Ye address hardware address (MAC) se alag hota hai aur IP address ke roop mein hota hai. Logical addresses devices ke beech communication ko possible banate hain, chahe wo network ke kisi bhi kone mein ho. Ye address hierarchical structure follow karta hai jaise network part aur host part. Ye addressing network layer ke liye zaroori hoti hai.

**Example:**
Aapke ghar ka ek unique address hota hai, waise hi computer ka IP address hota hai jaise 192.168.1.5. Jab aap website visit karte hain, toh aapka device apna logical address bhejta hai. Ye address internet routers ko batata hai ki packet kahaan bhejna hai.

---

## 3. **Internetworking**

Internetworking ka matlab hai alag-alag networks ko jodna taaki wo ek dusre se baat kar saken. Ye internet ka basic concept hai jisme kai networks milkar ek bada network banate hain. Internetworking ke liye routers aur gateways ka use hota hai jo different protocols ko connect karte hain. Ye ensure karta hai ki data packets ek network se doosre network mein smoothly travel kar saken. Network layer internetworking ke liye IP protocol ka use karta hai.

**Example:**
Aapke mobile ka Wi-Fi network aur internet service provider ka network connected hain. Jab aap email bhejte hain, toh wo aapke network se internet ke network tak travel karta hai. Internetworking ke bina aap ek network se doosre network ke devices se connect nahi kar sakte.

---

## 4. **Fragmentation**

Fragmentation tab hoti hai jab data packet bohot bada hota hai aur network device usse accept nahi karta. Data ko chhote tukdon mein tod kar bhejna hota hai jise fragments kehte hain. Fir receiver fragments ko assemble karke original data banata hai. Ye process data loss aur errors ko kam karta hai. Fragmentation network efficiency ko maintain karta hai aur protocols jaise IP mein use hota hai.

**Example:**
Agar aap ek bada video file bhejna chahte hain jo ek packet mein nahi ja sakta, toh wo chhote packets mein tod diya jayega. Har chhota packet alag se bheja jayega. Receiver sab packets milane ke baad video ko dobara banata hai.

---

## 5. **Point to Point Network**

Point to point network do devices ke beech direct connection hota hai, jisme beech mein koi third device nahi hota. Ye simple aur fast communication provide karta hai. Is tarah ka network mainly leased lines, telephone calls, ya serial connections mein hota hai. Isme data transfer reliable hota hai kyunki data ek fixed line se jaata hai. Point to point networks local ya wide area dono ho sakte hain.

**Example:**
Aapka ghar aur office ke beech ek direct leased line connection. Do computers ke beech USB cable se connection. Telephone call bhi ek point to point network ka example hai.

---

# **Basic Internetworking**

---

## 1. **IP (Internet Protocol)**

IP protocol network layer ka main protocol hai jo data packets ko source se destination tak bhejne ke liye addressing aur routing karta hai. IP addresses logical addressing ka part hain aur har device ko unique address dete hain. IP version 4 (IPv4) aur IPv6 dono common hain. IP packets ko route karne ke liye best path find karta hai. IP connectionless protocol hai, matlab packets independently travel karte hain.

---

### IP Address Classes

IP addresses ko different classes mein divide kiya gaya hai jo network size aur use ke hisaab se alag hain:

* **Class A:** Large networks ke liye (1.0.0.0 to 126.255.255.255), example: 10.0.0.1
* **Class B:** Medium size networks (128.0.0.0 to 191.255.255.255), example: 172.16.0.1
* **Class C:** Small networks (192.0.0.0 to 223.255.255.255), example: 192.168.1.1
* **Class D:** Multicast ke liye (224.0.0.0 to 239.255.255.255), example: 224.0.0.1
* **Class E:** Reserved future use (240.0.0.0 to 255.255.255.255)

**Example:**
Agar company ka network bada hai, toh wo Class A ka IP address lega. School ke chhote network mein Class C address use hota hai. Multicast TV channel broadcast karne ke liye Class D address use hota hai.

---

## 2. **CIDR (Classless Inter-Domain Routing)**

CIDR ek flexible IP addressing scheme hai jo IP addresses ko efficiently allocate karta hai, bina fixed class ke. Isme IP addresses ko prefixes ke form mein likha jaata hai, jaise 192.168.0.0/24. CIDR se address space better utilize hota hai aur routing tables chhoti hoti hain. Ye traditional class-based addressing ki limitations ko door karta hai.

**Example:**
192.168.1.0/28 ka matlab hai 16 addresses ek group mein. CIDR se ek company apne network ko chhote-chhote subnet mein divide kar sakti hai. Isse IP addresses ki bachat hoti hai.

---

## 3. **ARP (Address Resolution Protocol)**

ARP ek protocol hai jo logical IP address ko physical MAC address mein convert karta hai taaki data local network mein bheja ja sake. Jab device ko kisi IP address par packet bhejna hota hai, toh wo ARP request bhejta hai aur MAC address leta hai. Ye local area network mein communication ke liye zaroori hai.

**Example:**
Agar aapka computer 192.168.1.10 se data bhejna chahta hai 192.168.1.20 par, toh wo pehle ARP request bhejega ki “192.168.1.20 ka MAC address kya hai?” Fir packet physically MAC address ke basis par bheja jayega.

---

## 4. **DHCP (Dynamic Host Configuration Protocol)**

DHCP automatically devices ko IP addresses aur network settings assign karta hai taaki manually address configure na karna pade. Jab device network join karta hai, wo DHCP server se IP lease mangta hai. DHCP se network management asaan ho jaata hai, especially large networks mein.

**Example:**
Jab aapka phone Wi-Fi se connect hota hai, toh wo automatically IP address DHCP server se leta hai. Offices mein har naye device ko IP address DHCP se milta hai. DHCP IP conflicts ko bhi rokta hai.

---

## 5. **ICMP (Internet Control Message Protocol)**

ICMP network devices ke beech error messages aur diagnostics ke liye use hota hai. Ye network issues jaise unreachable destination, time exceeded, ping response provide karta hai. ICMP network health monitor karne mein madad karta hai.

**Example:**
Ping command ICMP ka use karta hai check karne ke liye ki ek device reachable hai ya nahi. Agar koi website down hai, toh ICMP unreachable message bhej sakta hai. Traceroute bhi ICMP packets use karta hai.

---

## 6. **RARP (Reverse Address Resolution Protocol)**

RARP ek protocol hai jo MAC address se IP address find karta hai. Ye device ko apna IP address pata karne mein madad karta hai jab wo start hota hai. RARP ab kam use hota hai, DHCP ne iska kaam le liya hai.

**Example:**
Network printer ya booting computer apna IP address RARP request bhej kar pata karta hai. Agar device ko IP pata nahi hai, toh wo RARP se network se poochta hai. Ye specially purane systems mein common tha.

---

## 7. **Subnetting**

Subnetting ka matlab hai ek bade network ko chhote subnetworks mein divide karna taaki network management aur security behtar ho. Do prakar ke subnetting hote hain:

* **Fixed Length Subnetting (FLSM):** Sab subnet equal size ke hote hain.
* **Variable Length Subnetting (VLSM):** Subnet size alag-alag ho sakte hain, jisse address space efficiently use hota hai.

**Example:**
Company ke network ko department-wise alag subnets mein divide karna. FLSM mein sab departments ko equal IPs milte hain. VLSM mein HR ko kam aur IT ko zyada IPs diye jaate hain.

---

### 1. **Fixed Length Subnetting**

#### ➤ Sabhi subnets same size ke hote hain.

#### ➤ Example:

Agar 192.168.1.0/24 ko 4 parts mein divide karna ho:

* 192.168.1.0/26
* 192.168.1.64/26
* 192.168.1.128/26
* 192.168.1.192/26

---

### 2. **Variable Length Subnetting (VLSM)**

#### ➤ Alag-alag size ke subnets banaye jaate hain need ke hisaab se.

#### ➤ Example:

* Ek subnet 100 logon ke liye chahiye → /25
* Doosra subnet sirf 10 logon ke liye chahiye → /28

✅ **VLSM** efficient hai kyunki IPs waste nahi hote.

---


## 🔷 **IPv4 (Internet Protocol Version 4)**

### 📌 Kya hai?

IPv4 ek **network protocol** hai jo devices ko internet par ek **unique address** deta hai (jaise 192.168.1.1), taaki data sahi jagah pahunch sake.

### ➤ Format:

IPv4 address: `32-bit` ka hota hai (e.g. `192.168.0.1`)

---

### ✅ **IPv4 Header (Structure)**

IPv4 packet ke upar ek **header** hota hai — isme important information hoti hai jise routers use karte hain data ko forward karne ke liye.

#### 1. **Version**

* 4-bit field
* Batata hai ki ye **IPv4** hai (value: `4`)

#### 2. **Header Length**

* Batata hai header kitna bada hai (minimum 20 bytes)

#### 3. **Services (Type of Service or DSCP)**

* Priority batata hai (jaise: video call high priority, file download low)
* Aaj ke time mein **DSCP (Differentiated Services Code Point)** ka use hota hai

#### 4. **Total Length**

* Pure IPv4 packet ka size (header + data)
* Max: `65,535 bytes`

#### 5. **Identification**

* Har packet ko ek unique ID milti hai
* Agar packet fragments mein bheja jaaye, to yahi ID unhe jodne mein madad karti hai

#### 6. **Flags**

* 3 bits hote hain:

  * **DF (Don't Fragment)**: Fragment mat karo
  * **MF (More Fragments)**: Aur fragments baaki hain ya nahi
  * 1 reserved bit

#### 7. **Header Checksum**

* Header sahi hai ya nahi, yeh verify karta hai (error detection)
* Har router isay check karta hai

#### 8. **Source Address**

* Data jahan se aaya hai (sender ka IP)

#### 9. **Destination Address**

* Data kahan jaana hai (receiver ka IP)

---

## 🔷 **IPv6 (Internet Protocol Version 6)**

### 📌 Kya hai?

IPv6, IPv4 ka **updated version** hai jisme **zyada addresses** aur **security & performance improvements** hain.

### ➤ Format:

IPv6 address: `128-bit` ka hota hai (e.g. `2001:0db8:85a3:0000:0000:8a2e:0370:7334`)

---

### ✅ **IPv6 Header (Simplified compared to IPv4)**

#### 1. **Version**

* 4-bit value (value: `6`) → batata hai ki ye IPv6 packet hai

#### 2. **Traffic Class**

* QoS (Quality of Service) ke liye hota hai — same as Type of Service in IPv4

#### 3. **Flow Label**

* Special packets (like video/audio) ko track karta hai — unka unique flow banata hai

#### 4. **Payload Length**

* Data ka actual size (header ke alawa), in bytes

#### 5. **Next Header**

* Batata hai agla protocol kaunsa hai (TCP, UDP, ICMPv6 etc.)

#### 6. **Hop Limit**

* Maximum kitne routers tak packet jaa sakta hai — har router is value ko 1 se kam karta hai
* IPv4 me ise **TTL (Time to Live)** kehte hain

#### 7. **Source Address**

* Sender ka 128-bit IPv6 address

#### 8. **Destination Address**

* Receiver ka 128-bit IPv6 address

---

## 🔶 **IPv4 vs IPv6 – Comparison Table**

| Feature               | IPv4                       | IPv6                           |
| --------------------- | -------------------------- | ------------------------------ |
| **Address Size**      | 32-bit (e.g., 192.168.1.1) | 128-bit (e.g., 2001\:db8::1)   |
| **Total Addresses**   | \~4.3 billion              | \~3.4×10³⁸ (almost unlimited)  |
| **Header Size**       | 20–60 bytes                | Fixed 40 bytes                 |
| **Configuration**     | Manual or DHCP             | Auto-configuration supported   |
| **Security**          | Optional (via IPsec)       | Mandatory (IPsec is built-in)  |
| **Fragmentation**     | Routers & Sender           | Only sender                    |
| **Checksum**          | Yes                        | No (handled by upper layers)   |
| **Broadcast Support** | Yes                        | No (uses multicast instead)    |
| **Example Address**   | 192.168.1.1                | 2001:0db8:85a3::8a2e:0370:7334 |

---

### ✅ **Summary in Simple Words:**

| IPv4                              | IPv6                              |
| --------------------------------- | --------------------------------- |
| Purana version, limited addresses | Naya version, unlimited addresses |
| Chhota header                     | Simple but bigger header          |
| Manual settings zyada             | Zyada automation                  |
| Security optional                 | Security built-in                 |

---

## 🔷 **ICMP (Internet Control Message Protocol)**

### ✅ **What is it?**

ICMP ek **network protocol** hai jo **messages** bhejta hai jab koi **error hoti hai** ya jab hume network ke baare mein kuch **information** chahiye hoti hai.

> 🧠 ICMP ko data bhejne ke liye nahi, **network ki condition check karne** ke liye use kiya jaata hai.

### ✅ **Uses of ICMP**

1. **Error Reporting** (galti hone par message dena)
2. **Query Management** (jaise: kisi device ka status check karna)

---

### 📌 **1. Error Reporting**

ICMP routers ya hosts ko inform karta hai agar:

* Destination nahi mila
* TTL expire ho gaya
* Fragmentation problem hui

#### 🔹 Example:

Aapne kisi wrong IP pe message bheja — router ICMP message bhejta hai:
**"Destination Unreachable"**.

🧾 Common ICMP Error Messages:

* **Destination Unreachable**
* **Time Exceeded**
* **Parameter Problem**

---

### 📌 **2. Query Management**

Ye ICMP ka part network status ke liye hota hai. Devices ek dusre se query karte hain.

#### 🔹 Example:

Jab aap **`ping`** command chalate ho, to aapka computer ICMP echo request bhejta hai, aur saamne wala echo reply karta hai.

🧾 Common ICMP Query Messages:

* **Echo Request / Reply** (used in `ping`)
* **Timestamp Request / Reply**

---

## 🔷 **Routing**

### ✅ **What is Routing?**

Routing ka matlab hai **data ke liye best path** choose karna taaki wo source se destination tak efficiently pahunch sake.

📍 **Router** ye kaam karta hai — routing table ki madad se.

---


# **Routing**

Routing ka matlab hota hai network devices (jaise routers) ke dwara data packets ko source se destination tak bhejne ka process. Routing mein decide kiya jata hai ki packets kaunse raaste (path) se jayenge takki wo jaldi aur efficiently pohonch saken. Routing ke do main types hote hain — **Static Routing** aur **Dynamic Routing**.

---

## 1. **Static Routing**

Static routing mein network administrator manually routers ke routes configure karta hai. Isme routes fixed hote hain, aur automatically change nahi hote. Ye chhote aur simple networks ke liye useful hota hai. Static routing fast hota hai kyunki routing table update nahi hoti, lekin agar network mein change ho toh manual update karna padta hai.

**Example:**
Ek chhoti company ke 3 offices hain jise manually ek dusre se connect kar diya gaya hai. Agar ek office ka network change ho toh admin ko manually routers mein update karna padega. Ye static routing ka ek example hai.

---

## 2. **Dynamic Routing**

Dynamic routing mein routers khud apas mein baat kar ke routing information share karte hain aur automatically best routes find karte hain. Ye large aur complex networks ke liye useful hota hai. Dynamic routing mein routing protocols jaise RIP, OSPF, BGP use hote hain. Iska fayda ye hai ki network changes automatically update ho jate hain.

**Example:**
Internet mein alag-alag networks dynamically routing protocols ka use karke apni routes update karte hain. Agar koi link down ho jata hai, toh routers automatically alternate route dhoond lete hain.

---

# **Forwarding**

Forwarding ka matlab hota hai router ke paas aane wale data packets ko sahi output interface se bhejna, taaki wo apne destination tak pahunch saken.

Forwarding decisions lene ke liye router **routing table** ka use karta hai, jisme kuch terms hote hain:

---

### 1. **Next Hop**

Next Hop ka matlab hai agla device ya router jise packet bhejna hai. Router ke paas ye information hoti hai ki packet ko agle step mein kis device ko dena hai.

**Example:**
Agar packet A router par hai aur usse B router tak jaana hai, toh router A ke liye B hi next hop hoga.

---

### 2. **Network**

Network se matlab hai ek IP address range jo ek particular subnet ko represent karta hai. Routing table mein har entry ek network hoti hai jiska pata router ko hota hai.

**Example:**
192.168.1.0/24 ek network hai jisme 256 IP addresses hain.

---

### 3. **Default**

Default route wo route hota hai jo tab use hota hai jab kisi destination ke liye specific route nahi milta. Isse routers “gateway of last resort” bhi kehte hain. Agar router ko packet ke liye matching network nahi milta toh packet default route se bhej diya jata hai.

**Example:**
Agar router ko 10.10.10.5 IP address ka route nahi pata, toh wo packet ko default route pe bhej dega.

---

# **Delivery**

Delivery ka matlab hai packet ko destination device tak physically pohonchana. Isme do types hain:

---

### 1. **Direct Delivery**

Direct delivery tab hoti hai jab source aur destination devices same network ya subnet mein hote hain. Is case mein data packet directly destination device ko bheja jaata hai bina kisi intermediate device ke.

**Example:**
Agar aapka computer aur printer dono same office network mein hain, toh data directly printer ko bheja jayega.

---

### 2. **Indirect Delivery**

Indirect delivery tab hoti hai jab source aur destination alag networks mein hote hain. Is case mein data packet pehle router ko jata hai, fir router packet ko destination network mein forward karta hai.

**Example:**
Aapke ghar ka computer internet par kisi website ko access karta hai, toh data pehle router ko jayega, phir router website ke server tak bhejega.

---

## 🔚 **Quick Summary Table**

| Term                 | Meaning                                                   |
| -------------------- | --------------------------------------------------------- |
| **ICMP**             | Network errors aur test messages ke liye protocol         |
| **Error Reporting**  | ICMP batata hai agar packet delivery mein koi problem ho  |
| **Query Management** | ICMP network ke status check karta hai (`ping`, etc.)     |
| **Routing**          | Best path choose karna for data                           |
| **Static Routing**   | Manually set routes                                       |
| **Dynamic Routing**  | Automatically choose best path                            |
| **Forwarding**       | Packet ko next device tak bhejna                          |
| **Next Hop**         | Agla router                                               |
| **Default**          | Jab specific route na ho, to ek general path follow karna |
| **Delivery**         | Packet ka destination tak pahunchna                       |
| **Direct**           | Same network                                              |
| **Indirect**         | Alag network (routers ke through)                         |

---

# **The Optimality Principle**

Optimality principle kehta hai ki agar router A se router C tak ka shortest path pata hai, toh agar ye path router B se bhi guzarta hai, toh B se C tak ka path bhi shortest hoga. Matlab, network mein har intermediate node par bhi best route select hota hai. Is principle ki wajah se routing algorithms efficient decisions le pate hain.

**Example:**
Agar Delhi se Mumbai ka shortest route Jaipur se guzarta hai, toh Jaipur se Mumbai ka bhi wahi shortest route hoga. Isi tarah routers apni routing tables update karte hain.

---

# **Shortest Path Algorithm**

Shortest Path Algorithm ka kaam hota hai network mein data ke liye sabse chhota (shortest) aur best path find karna.

---

## **Dijkstra’s Algorithm**

Dijkstra ka algorithm network mein har node se destination tak ka shortest path find karta hai. Ye har node ka distance calculate karta hai aur minimum distance wala path select karta hai. Ye algorithm link state routing protocols mein use hota hai.

**Example:**
Ek graph jisme 4 cities connected hain, Dijkstra algorithm se hum pata karenge Delhi se Mumbai ka shortest raasta kaunsa hai. Har connection ka weight (distance/time) hota hai, aur algorithm minimum sum wala path batata hai.

---

# **Flooding**

Flooding ek simple routing technique hai jisme har incoming packet ko router apne sabhi interfaces par bhej deta hai, except jis interface se packet aaya ho. Iska fayda ye hai ki packet apni destination tak jarur pahunchta hai, lekin network traffic bahut badh jata hai (overhead).

**Example:**
Agar aap ek message sabko bhejna chahte hain bina pata ki kis route se jayega, toh sabko message forward kar dena flooding hai. Jaise ek group chat mein sabko ek baar mein message bhejna.

---

# **Distance Vector Routing**

Distance vector routing mein har router apne neighbours ko apni routing table deta hai, jisme har network ka distance (vector) hota hai. Routers apni tables update karte hain jab unke neighbours ke pass naye routes hote hain. Ye algorithm slow converge karta hai aur count-to-infinity problem hota hai.

**Example:**
RIP (Routing Information Protocol) distance vector routing use karta hai. Router A apne neighbours ko batata hai ki 5 hops door ek network hai. Neighbours bhi apne data share karte hain aur sab apni tables update karte hain.

---

# **Link State Routing**

Link state routing mein har router apni directly connected links ki state network mein sabhi routers ko broadcast karta hai. Sab routers complete network ka topology jante hain aur Dijkstra algorithm se shortest path calculate karte hain. Ye fast aur reliable hota hai.

**Example:**
OSPF (Open Shortest Path First) protocol link state routing use karta hai. Har router apne connections ke baare mein sabko batata hai, fir sabhi routers ek jaisa map banate hain network ka.

---

# **Multicast Routing**

Multicast routing mein ek source se data ko multiple selected destinations (group) tak efficiently bheja jata hai. Ye broadcast se alag hota hai kyunki data sirf interested devices tak jata hai, unnecessary devices tak nahi.

**Example:**
Live sports streaming mein jab ek broadcaster apne signal ko ek group of users tak bhejta hai, multicast routing use hota hai. Sirf jo users stream dekhna chahte hain unko data milta hai.

---

# **Broadcast Routing**

Broadcast routing mein data packet network ke sabhi devices tak bheja jata hai. Ye local networks mein hota hai jaise ARP requests, jisme sabko packet forward kar diya jata hai.

**Example:**
Jab aapka computer apne network par sab devices se poochta hai ki “Is IP address 192.168.1.5 kisi ka hai?” toh wo broadcast hota hai.

---

# **Congestion**

Congestion tab hota hai jab network mein data traffic zyada ho jata hai aur devices packets ko process nahi kar pate, jisse delay aur packet loss hota hai.

---

## **Congestion Control**

Congestion control techniques ka goal hota hai network ko congested hone se bachana aur traffic smooth chalana.

---

### Open Loop Congestion Control

Open loop control mein congestion hone se pehle hi control measures lagaye jaate hain.

* **Retransmission:** Agar packet lost ho jata hai toh use dobara bheja jata hai.
* **Window:** Flow control ke liye window size manage ki jati hai, jisse ek time par kitne packets bheje jayenge decide hota hai.

**Example:**
TCP protocol retransmission aur sliding window ka use karta hai taaki data reliable rahe.

---

### Closed Loop Congestion Control

Closed loop control mein congestion detect hone ke baad measures liye jate hain.

* **Back Pressure:** Switch ya router congested hone par apne upstream devices ko signal deta hai traffic rokne ke liye.
* **Choke Packet:** Router congested hone par source device ko ek special packet bhejta hai jisme kaha jata hai ki traffic slow karo.

**Example:**
Jab router busy ho jata hai, wo source ko choke packet bhej kar data bhejne ki speed kam karne ke liye kehta hai.

---


# **QoS (Quality of Service)**

QoS network mein data transmission ki quality ko ensure karta hai, taaki important data timely aur reliably pohonche. QoS ka use especially real-time applications jaise video calls, online gaming, aur VoIP mein hota hai jahan data ka delay ya loss unacceptable hota hai. QoS ke kuch main parameters hain:

---

## 1. **Reliability**

Reliability ka matlab hai data ka sahi aur bina loss ke delivery hona. Reliable network mein data packets drop nahi hote ya agar drop hote hain toh wo dobara bheje jate hain. TCP protocol is reliability ko ensure karta hai.

**Example:**
Email bhejte waqt, agar packet loss hota hai, toh wo automatically retransmit hota hai, taaki aapka email pura receiver tak pahunch jaye.

---

## 2. **Delay**

Delay ka matlab hota hai packet ke source se destination tak pahunchne mein lagne wala samay. Kam delay ka matlab network fast hai. Real-time applications mein delay kaafi important hota hai.

**Example:**
Video call mein agar delay zyada ho toh conversation mein gap lagega. Jaise aap kisi se baat kar rahe ho aur dusra banda aapki baat sunne mein late ho.

---

## 3. **Jitter**

Jitter delay ka variation hota hai, yani packets randomly late ya jaldi pohonchna. Ye real-time streaming mein problem create karta hai kyunki packets ke timing consistent nahi hote.

**Example:**
Online game khelte waqt agar jitter zyada ho toh aapke character ke moves irregular ho jayenge.

---

## 4. **Bandwidth**

Bandwidth network ki capacity hoti hai ki wo kitna data ek second mein transfer kar sakta hai. Zyada bandwidth matlab network zyada data ko handle kar sakta hai.

**Example:**
Agar aapke ghar ka internet 100 Mbps ka hai, toh aap ek second mein 100 Megabits data download kar sakte ho. Streaming HD video ke liye bandwidth important hoti hai.

---

# **Congestion Algorithms**

Congestion algorithms network mein traffic control karte hain taaki congestion na ho aur data smoothly flow kare. Do popular algorithms hain:

---

## 1. **Leaky Bucket Algorithm**

Leaky Bucket algorithm network traffic ko regulate karta hai jaise ek bucket se paani thoda-thoda nikalta hai. Agar bucket bhar jaye toh extra packets drop ho jate hain. Ye traffic ko constant rate se flow karata hai.

**Example:**
Aap ek pipe se paani bhar rahe hain jo thoda thoda nikal raha hai. Agar paani bahut zyada aane lage toh overflow ho jayega, waise hi agar packets zyada aaye toh drop honge.

---

## 2. **Token Bucket Algorithm**

Token Bucket mein tokens generate hote hain ek fixed rate se. Packet bhejne ke liye token chahiye hota hai. Agar tokens available hain toh packets bheje jate hain, nahi toh wait karna padta hai. Ye bursty traffic ko allow karta hai.

**Example:**
Aapko token lena hota hai swimming pool mein enter karne ke liye. Agar tokens hain toh turant jaa sakte hain, nahi toh line mein wait karna padega. Isse sudden bursts handle ho jate hain.

---

