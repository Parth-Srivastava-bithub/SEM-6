## 🔹 **Network Layer (OSI Model ka 3rd layer)**

### 📌 Kya karta hai?

Network layer data ko **source se destination** tak pahuchane mein madad karta hai, chahe dono alag networks mein kyun na ho.

---

### 1. **Routing**

#### ➤ Meaning:

Routing ka matlab hai **best path dhoondhna** jisse data ek device se doosri device tak jaa sake.

#### ➤ Example:

Agar Aapko Delhi se Mumbai jaana ho, toh aap Google Maps se **shortest or fastest route** dhoondhte ho — yahi routing hai.

#### ➤ Important Concepts:

* **Routing Table**: Ek table jisme likha hota hai ki kahan se kaunsa data kahan bhejna hai.
* **Router**: Device jo routing karta hai (data ka rasta tay karta hai).

---

### 2. **Logical Addressing**

#### ➤ Meaning:

Data ko sahi jagah bhejne ke liye har device ko ek **unique address** chahiye hota hai. Isay **logical address** kehte hain, jaise **IP Address**.

#### ➤ Example:

Jaise ghar ka address hota hai (123, ABC Street), waise hi computer ka address hota hai (192.168.1.1).

---

### 3. **Internetworking**

#### ➤ Meaning:

Alag-alag networks (LAN, WAN, etc.) ko jodna internetworking kehlata hai.

#### ➤ Example:

Ek office ka LAN aur ek dusre office ka LAN — in dono ko jodna internetworking hai.

#### ➤ Devices:

* **Router**: Different networks ko connect karta hai.
* **Gateway**: Different protocols ko samjhata hai (jaise translator).

---

### 4. **Fragmentation**

#### ➤ Meaning:

Jab data ka size zyada bada hota hai aur kisi network ka maximum size kam hota hai, toh data ko **chhoti-chhoti pieces** mein todna padta hai. Isay fragmentation kehte hain.

#### ➤ Example:

Agar ek 2000-byte ka packet bhejna ho aur network sirf 1000 bytes support kare, toh usay 2 packets mein tod diya jaata hai.

---

## 🔹 **Point to Point Network**

#### ➤ Meaning:

Ek aisa network jisme **sirf do devices** directly connected hote hain.

#### ➤ Example:

Ek computer se printer directly connected ho, ya do routers ke beech direct cable connection ho.

#### ➤ Features:

* Simple structure
* High speed
* Kam data loss

---

## 🔹 **Basic Internetworking**

### 1. **IP (Internet Protocol)**

#### ➤ Meaning:

IP ek rule (protocol) hai jo data ko ek network se doosre network tak le jaata hai. IP address se hi pata chalta hai data kahan jaana hai.

---

#### ➤ **IP Address Classes**

IP address 5 classes mein divided hote hain (A, B, C, D, E):

| Class | Start Address | End Address     | Use                                  |
| ----- | ------------- | --------------- | ------------------------------------ |
| A     | 1.0.0.0       | 126.255.255.255 | Large networks (e.g., Google)        |
| B     | 128.0.0.0     | 191.255.255.255 | Medium networks (e.g., Universities) |
| C     | 192.0.0.0     | 223.255.255.255 | Small networks (e.g., home/office)   |
| D     | 224.0.0.0     | 239.255.255.255 | Multicasting                         |
| E     | 240.0.0.0     | 255.255.255.255 | Research/Experimental                |

✅ **Example**:

* Class A: 10.0.0.1
* Class B: 172.16.0.1
* Class C: 192.168.1.1

---

### 2. **CIDR (Classless Inter-Domain Routing)**

#### ➤ Meaning:

CIDR IP address ko flexible banata hai, bina Class ke use karta hai.

#### ➤ Example:

192.168.1.0/24 — iska matlab hai pehle 24 bits network ke liye, baaki host ke liye.

✅ CIDR se IPs ki **waste kam hoti hai**.

---

### 3. **ARP (Address Resolution Protocol)**

#### ➤ Purpose:

IP address se **MAC address** (physical address) dhoondta hai.

#### ➤ Example:

Jaise aapke paas kisi ka naam ho par phone number nahi ho — toh aap directory se uska number nikaalte ho.

---

### 4. **DHCP (Dynamic Host Configuration Protocol)**

#### ➤ Purpose:

Automatic IP address assign karta hai jab device network se connect hota hai.

#### ➤ Example:

Jaise aap Wi-Fi connect karte ho aur automatically IP mil jaata hai.

---

### 5. **ICMP (Internet Control Message Protocol)**

#### ➤ Purpose:

Network errors aur diagnostics ke liye use hota hai.

#### ➤ Example:

`ping` command ICMP ka use karti hai ye check karne ke liye ki koi device network par hai ya nahi.

---

### 6. **RARP (Reverse ARP)**

#### ➤ Purpose:

MAC address se IP address dhoondta hai (ARP ka ulta kaam).

#### ➤ Use:

Old systems jinke paas IP nahi hota, unko IP assign karne ke liye.

---

## 🔹 **Subnetting**

Subnetting se ek bada network **chhote parts** (subnets) mein divide kiya jaata hai.

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

### 📌 **Types of Routing**

### 1. **Static Routing**

* Routes manually configure kiye jaate hain.
* Changes manually karne padte hain.

#### 🔹 Example:

Small office network — admin manually set karta hai:
`If destination is 192.168.2.0 → Go to Router B`

### ✅ Pros:

* Simple & secure

### ❌ Cons:

* Manual update required

---

### 2. **Dynamic Routing**

* Routers **automatically routes** choose karte hain.
* Routing protocols ka use hota hai: RIP, OSPF, EIGRP, BGP

#### 🔹 Example:

Agar ek path fail ho jaata hai, router dusra best path choose kar leta hai.

### ✅ Pros:

* Auto updates

### ❌ Cons:

* Thoda complex

---

## 🔷 **Forwarding**

### ✅ **What is Forwarding?**

Forwarding ka matlab hai: **router ke paas aaya hua packet** ko **next hop (agla router)** ki taraf bhejna.

📍 Forwarding actual kaam hai (data ko bhejna), routing planning ka kaam hai (kaise bhejna).

---

### 📌 **Types of Forwarding**

#### 1. **Next Hop Forwarding**

Router packet ko **next router** (not final destination) tak bhejta hai.

> Jaise GPS aapko bolta hai "turn left after 2 km" – final location ke liye step-by-step guidance deta hai.

#### 2. **Network Specific Forwarding**

Agar router ke paas full network info ho, to packet directly **target network** ki taraf bheja jaata hai.

#### 3. **Default Forwarding**

Agar specific route na mile, to packet **default route** pe bheja jaata hai.

> Jaise aapko kisi unknown jagah jaana ho aur aap kehte ho: “Google Maps khol lo.”

---

## 🔷 **Delivery**

### ✅ **What is Delivery?**

Delivery ka matlab hai **data packet ka destination device tak pahunchna**.

### 📌 **Types of Delivery**

#### 1. **Direct Delivery**

* Jab sender aur receiver **same network** par ho.

> 🧾 Example:
> Laptop A → Printer (connected on same Wi-Fi)

#### 2. **Indirect Delivery**

* Jab sender aur receiver **different networks** mein ho aur routers ke through jaaye.

> 🧾 Example:
> Aapka PC (home) → Server (USA) → via routers

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

### 1. **The Optimality Principle**

Optimality principle networking mein ek bahut important concept hai, jo kehta hai ki agar aap ek source se destination tak ka shortest (sabse chhota) rasta nikal rahe hain, toh us raste ke beech ke har segment ko bhi apne aap mein shortest path hona chahiye. Matlab, agar aap Delhi se Mumbai ke liye shortest rasta lete ho jo Jaipur ke through jaata hai, toh Jaipur se Mumbai ka rasta bhi sabse chhota rasta hona chahiye. Ye principle routers ko apni routing decisions ko logically organize karne mein madad karta hai, taki har step par best possible choice ki ja sake aur network efficient tareeke se kaam kare.

---

### 2. **Shortest Path Algorithm - Dijkstra’s Algorithm**

Dijkstra’s algorithm ek famous algorithm hai jo network mein ek source node se baaki sabhi nodes tak shortest path dhoondhta hai. Is algorithm mein har node ko ek initial distance di jaati hai, source ka 0 aur baaki ka infinity. Fir algorithm un nodes ko step by step select karta hai jinke distance sabse kam hain, aur unke neighbours ke distance update karta hai. Jab tak sab nodes ka shortest distance nahi mil jaata, ye process chalta rehta hai. Ye algorithm GPS navigation jaisa kaam karta hai, jahan se aap start karte hain aur sabse chhoti doori nikalte hain. Network routing mein Dijkstra ki madad se routers decide karte hain ki data packets kaunse route se bhejne hain taaki sabse tezi se destination tak pahunch sake.

---

### 3. **Flooding**

Flooding ek simple but inefficient routing technique hai jisme router ko milne wala har packet network ke har outgoing link par forward kar deta hai, bina kisi routing table ya decision ke. Matlab, agar aap ek packet bhejte hain, to wo network mein har jagah fail jaata hai. Ye method simple hone ke bawajood network mein bahut zyada traffic create kar sakta hai aur loops ke wajah se packet baar-baar circulate kar sakte hain, jis se network congest ho sakta hai. Flooding ko rokne ke liye routers TTL (Time To Live) value use karte hain, jo har hop par kam hoti hai aur jab 0 ho jaati hai toh packet discard kar diya jaata hai.

---

### 4. **Distance Vector Routing**

Distance Vector Routing mein routers apne directly connected neighbors ko apne routing table se distance information bhejte hain. Har router apne neighbors se yeh information receive karta hai aur apne routing table ko update karta hai, jisme likha hota hai ki har network tak kitni doori (distance) hai. Ye method simple hai lekin kuch problems hoti hain, jaise routing loops aur slow convergence. RIP (Routing Information Protocol) is technique ka ek example hai jisme routers har 30 second mein apne neighbors ko apni routing table bhejte hain. Distance vector routing mein routers ko network ke baare mein limited information hoti hai, isliye wo apne neighbors ke data par depend karte hain.

---

### 5. **Link State Routing**

Link State Routing thoda advanced technique hai jisme har router apne directly connected links ke status ka poora network ko pata hota hai. Ismein har router apni link state information ko sab routers tak broadcast karta hai, taaki sabhi routers ek jaise network map bana sakein. Jab ye map ban jaata hai, tab har router Dijkstra’s algorithm ka use karke apne liye shortest path calculate karta hai. Is technique se routers ke paas network ki poori jankari hoti hai, isliye ye zyada accurate aur fast hoti hai. OSPF (Open Shortest Path First) ek popular link state routing protocol hai jo ye kaam karta hai.

---

### 6. **Multicast Routing**

Multicast Routing mein ek source se data ko unhi users ko bheja jaata hai jo interested hain ya jis group ka part hain. Iska matlab hai ki data har device ko nahi, balki sirf ek select group ko bheja jata hai. Ye method bahut efficient hoti hai jab aapko video conferencing, live streaming, ya online lectures mein ek hi data ko multiple users tak bhejna ho. Multicast routing mein routers multicast group addresses manage karte hain aur data packets ko aise paths par bhejte hain jo us group ke sabhi members ko cover karte hain bina data ko baar-baar bheje.

---

### 7. **Broadcast Routing**

Broadcast Routing mein ek source se data ko network ke sabhi devices ko ek saath bheja jaata hai. Iska matlab hai ki data packet sab nodes ko milta hai chahe wo us data mein interested ho ya nahi. IPv4 networks mein broadcasting hoti hai, jaise ki DHCP requests jab network ke sabhi devices ko pata chalna hota hai. Lekin broadcasting network pe bahut zyada load create kar sakti hai aur network congestion badha sakti hai, isliye IPv6 mein multicast ka use hota hai jisse network efficiency improve hoti hai.

---

## 1. **Congestion Kya Hai?**

Sochiye ek sadak par bahut zyada gadiyaan ek saath chal rahi hain. Agar gadiyaan zyada ho jayein, toh traffic jam ho jaata hai, gaadiyaan dheere chalti hain, ya ruk jaati hain. Network mein bhi aise hi hota hai jab ek time pe bohot zyada data packets ek jagah aane lagte hain — routers aur switches overload ho jaate hain, aur data packets delay hone lagte hain, ya kho jaate hain (lost ho jaate hain).

Is problem ko **congestion** kehte hain.

---

## 2. **Congestion Control Kya Hai?**

Congestion control wo tareeke hain jisse network apne aap ko congestion se bachata hai ya congestion kam karta hai. Ye control do tarah ka hota hai:

### A. Open Loop Congestion Control (Sender-Receiver ke beech)

Isme sender aur receiver apne communication ko aise design karte hain ki congestion na ho ya kam ho.

* **Retransmission (Dobara bhejna):**
  Agar data packet khoya ya damage ho jaata hai, toh sender us packet ko firse bhejta hai. Jaise aapne message bheja, agar dost ne nahi padha toh aap dubara bhejte ho.

* **Windowing (Sliding Window):**
  Sender ek time mein kitne packets bhejega isse control karta hai. Matlab ek limit set karta hai ki ek baar mein zyada packets nahi bhejega. Jaise aap kisi elevator mein ek time mein kitne log jaa sakte hain, ek limit hoti hai.

---

### B. Closed Loop Congestion Control (Network ke andar feedback)

Isme routers aur switches network ki condition monitor karte hain, aur agar congestion detect hota hai, toh sender ko signal bhejte hain ki data bhejna slow karo.

* **Back Pressure:**
  Jab router congested ho jaata hai, toh wo apne peeche wale router ko signal bhejta hai ki data bhejna temporarily rok do, warna mera load badh jaayega.

* **Choke Packet:**
  Router sender ko ek special message bhejta hai jisme likha hota hai “network congested hai, thoda data bhejna kam karo.” Sender phir apni speed slow kar deta hai.

---

## 3. **Quality of Service (QoS) Kya Hai?**

QoS ka matlab hai network ki service ki quality ko maintain karna, jisse data jaldi, sahi, aur consistent speed par pohonche.

Iske kuch important parts hain:

* **Reliability:** Data sahi tarah se pohonche bina lose hue.
* **Delay:** Data jaldi pohonche, zyada der na lage.
* **Jitter:** Delay mein variation kam ho, jaise video calls mein awaaz aur video sync rahe.
* **Bandwidth:** Network mein data bhejne ki maximum speed.

---

## 4. **Congestion Control Algorithms**

### A. **Leaky Bucket Algorithm**

Ye algorithm sochne mein ek bucket ki tarah hai jisme paani (data packets) girta hai, lekin bucket mein ek chhota hole hai jisse paani ek fix speed se bahar nikalta hai.

* Agar data zyada aaye toh bucket overflow karega (packet loss hoga).
* Iska matlab hai ki data network mein ek fixed rate se hi bheja jaa raha hai.

**Example:**
Sochiye ek paani bharne wala bucket hai jisme paani lagataar gir raha hai, lekin bahar nikalne ka rate fixed hai. Agar paani zyada girta hai, toh bucket se paani bahar girne lagta hai.

---

### B. **Token Bucket Algorithm**

Isme data bhejne ke liye tokens chahiye hote hain. Tokens ek fixed speed se generate hote hain.

* Har packet bhejne ke liye ek token chahiye.
* Agar tokens available hain toh packet turant bheja jaata hai.
* Agar tokens nahi hain, toh packet ko wait karna padta hai.

**Example:**
Sochiye aapko cinema hall mein jaane ke liye ticket (token) lena padta hai. Tickets har kuch samay mein milte hain. Agar ticket mil jaye to aap andar jaa sakte hain, nahi to wait karna padta hai.

Is algorithm se network ko short burst mein zyada data bhejne ki permission milti hai, par overall control mein rakhta hai.

---

## **Summary Example for Congestion Control:**

Maan lijiye aap online video dekh rahe hain:

* Agar network congested hai, toh **router** aapke device ko signal dega (choke packet) ki data speed kam karo.
* Aapka device phir apni request speed kam karega (closed loop).
* Agar packet kho jata hai, toh device us packet ko dobara maangega (retransmission - open loop).
* Video smooth chalne ke liye QoS ensure karega ki delay aur jitter kam rahe.

---

