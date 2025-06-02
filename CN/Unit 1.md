# 🧠 1. **Introductory Concepts (Network ka Basic Overview)**

---

### 🔹 **Goals and Applications of Networks**

#### ✅ **Goals of Computer Networks:**

1. **Resource Sharing** – Network ka main goal hota hai resources ko share karna, jaise printer, files, internet connection.
2. **Communication** – Users easily email, messaging, video conferencing kar saken.
3. **Centralized Data Access** – Data ek central server pe store hota hai, jahan se har user access kar sakta hai.
4. **Reliability & Backup** – Network se data loss kam hota hai, regular backup hota hai.
5. **Cost Efficiency** – Shared devices se cost reduce hoti hai.

#### ✅ **Applications of Networks:**

* **Education:** Online learning platforms (Coursera, Byju’s), virtual classes.
* **Business:** Cloud services, video meetings, shared project files.
* **Healthcare:** Telemedicine, EHR (Electronic Health Records).
* **Banking:** Online banking, ATMs, core banking system.
* **Entertainment:** Netflix, YouTube, online gaming.

---

### 🔹 **Categories of Networks (Types of Networks)**

#### 1. **LAN (Local Area Network)**

* Ek choti geographical area jaise home, office, ya school lab.
* High speed hoti hai (100 Mbps to several Gbps).
* Devices directly connected hote hain (wired ya wireless).
* **Example:** Office WiFi, college computer lab.

#### 2. **MAN (Metropolitan Area Network)**

* Ek city ya campus area cover karta hai.
* Multiple LANs ko connect karta hai.
* **Example:** City-wide cable TV network, metro rail network.

#### 3. **WAN (Wide Area Network)**

* Large area cover karta hai – countries, continents.
* Internet bhi ek WAN hi hai.
* Slower than LAN/MAN but covers huge distances.
* **Example:** Internet, BSNL network across India.

#### 4. **PAN (Personal Area Network)**

* Ek individual user ke personal devices ka network.
* Range bahut choti hoti hai (\~10 meters).
* **Example:** Bluetooth connection between mobile and earphones.

---

### 🔹 **Organization of the Internet (Internet ka structure)**

* Internet billions of interconnected networks ka system hai.
* Ye **hierarchical** (levels-based) structure mein organized hota hai:

#### 📌 Levels:

1. **End Systems (Users)** – Computers, mobiles.
2. **Access ISP (Internet Service Provider)** – Jio, Airtel, BSNL.
3. **Regional ISP** – Multiple access ISPs ko connect karta hai.
4. **Backbone ISP** – High-speed international fiber optic lines.

---

### 🔹 **ISP (Internet Service Provider)**

* ISP wo company hoti hai jo internet access provide karti hai.
* **Types of ISP:**

  * **Tier-1 ISP:** Global level pe operate karte hain (e.g., Tata Communications).
  * **Tier-2 ISP:** Regional pe operate karte hain.
  * **Tier-3 ISP:** Local users ko direct internet dete hain.

---

### 🔹 **Network Structure and Architecture**

#### 📘 **Layering Principles:**

* Complex network ko samajhne ke liye usse **layers** mein divide kiya jata hai.
* Har layer ek specific function handle karti hai (jaise transmission, addressing, error control).

#### 📘 **Services:**

* Layer ke through upper layer ko jo functionality milti hai usse service kehte hain.

  * Jaise: Reliable delivery, error-free transmission.

#### 📘 **Protocols:**

* Rules ka set jo network communication mein follow kiya jata hai.

  * Jaise: TCP, IP, HTTP, FTP.

#### 📘 **Standards:**

* Guidelines jo networking devices banane wali companies follow karti hain.

  * Organizations: IEEE, ITU, IETF.

---

### 🔹 **OSI Reference Model (7-Layer Model)**

| Layer Number | Layer Name   | Function (Brief)                |
| ------------ | ------------ | ------------------------------- |
| 7            | Application  | User interface (e.g., browsers) |
| 6            | Presentation | Data format & encryption        |
| 5            | Session      | Session management              |
| 4            | Transport    | Reliable delivery (TCP/UDP)     |
| 3            | Network      | Logical addressing (IP)         |
| 2            | Data Link    | MAC addressing, frame handling  |
| 1            | Physical     | Bits transmission via cables    |

---

### 🔹 **TCP/IP Protocol Suite (Real-world Networking Model)**

| Layer (TCP/IP) | OSI Equivalent | Examples       |
| -------------- | -------------- | -------------- |
| Application    | 5, 6, 7        | HTTP, FTP, DNS |
| Transport      | 4              | TCP, UDP       |
| Internet       | 3              | IP, ICMP, ARP  |
| Network Access | 1 & 2          | Ethernet, WiFi |

---

### 🔹 **Network Devices and Components**

| Device           | Function                                                         |
| ---------------- | ---------------------------------------------------------------- |
| **Router**       | Networks ko connect karta hai (Layer 3)                          |
| **Switch**       | LAN ke andar devices connect karta hai (Layer 2)                 |
| **Hub**          | Basic device, data broadcast karta hai sabko                     |
| **Modem**        | Analog-digital signal convert karta hai                          |
| **Access Point** | Wireless device jo LAN extend karta hai                          |
| **NIC**          | Network Interface Card, computer ko network se connect karta hai |
| **Firewall**     | Security device, unauthorized access rokta hai                   |

---

## 📡 2. **Physical Layer (Network ka Neev/Foundation)**

---

### 🔹 **Network Topology Design**

Network topology matlab kaise devices ek dusre se connected hain.

#### Types of Topology:

| Type       | Description                           | Pros                    | Cons                         |
| ---------- | ------------------------------------- | ----------------------- | ---------------------------- |
| **Bus**    | Ek hi cable sab devices connect karta | Simple & cheap          | Cable failure → network down |
| **Star**   | Sab devices central switch se connect | Easy to manage          | Switch fail → all down       |
| **Ring**   | Devices ek circular path mein hote    | Predictable performance | One break → network issue    |
| **Mesh**   | Har device directly connect hota hai  | High reliability        | Costly, complex              |
| **Hybrid** | Combination of above topologies       | Flexible, scalable      | Expensive sometimes          |

---

### 🔹 **Types of Connections**

1. **Point-to-Point:** Two devices ke beech direct connection. Example: Laptop ↔ Printer.
2. **Multipoint:** Ek connection multiple devices share karte hain. Example: Bus topology.

---

### 🔹 **Transmission Media**

#### 1. **Guided Media (Wired):**

* **Twisted Pair Cable:** Telephone lines, LAN (cheap, short distance)
* **Coaxial Cable:** Cable TV (better shielding)
* **Fiber Optic Cable:** Light-based transmission, fastest & longest distance

#### 2. **Unguided Media (Wireless):**

* **Radio Waves:** Long range, used in FM, mobile phones.
* **Microwaves:** Point-to-point line of sight, satellite communication.
* **Infrared:** Remote control systems.

---

### 🔹 **Signal Transmission and Encoding**

* **Analog Signal:** Continuous wave (e.g., radio, old telephones).
* **Digital Signal:** Discrete binary 0s and 1s (used in modern computers).
* **Encoding Techniques:** NRZ, Manchester encoding etc. convert digital data into signals.

---

### 🔹 **Network Performance Factors**

* **Bandwidth:** Maximum data transfer rate (bps, Mbps, Gbps).
* **Latency:** Time lag (delay) between sender & receiver.
* **Throughput:** Actual data successfully delivered.
* **Jitter:** Variation in delay (bad for voice/video).

---

### 🔹 **Transmission Impairments**

* **Attenuation:** Signal weak ho jana.
* **Noise:** Unwanted signals (e.g., static).
* **Distortion:** Signal shape change ho jana.
* **Latency:** Delay in delivery.

---

### 🔹 **Switching Techniques**

1. **Circuit Switching:** Dedicated path (used in telephone networks).
2. **Packet Switching:** Data in packets, best path per packet (used in internet).
3. **Message Switching:** Whole message store & forward (slow, not common now).

---

### 🔹 **Multiplexing Techniques**

1. **FDM (Frequency Division Multiplexing):** Different signals on different frequencies.
2. **TDM (Time Division Multiplexing):** Time slots assign kiye jaate hain.
3. **WDM (Wavelength Division Multiplexing):** Fiber optic ke liye, alag light wavelengths.
4. **CDM (Code Division Multiplexing):** Every user gets a unique code.

---


