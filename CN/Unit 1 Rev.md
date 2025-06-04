### **Computer Network**

* Devices ke beech data exchange karne ka system hai.

---

### **Goals of Network**

* Data sharing, hardware sharing, software sharing, communication easy banana.

---

### **Applications of CN**

* Email, video calling, file sharing, online banking, cloud computing, etc.

---

### **Categories**

#### **LAN (Local Area Network)**

* Chhoti jagah jaise ghar ya office mein network banaya jata hai.

#### **MAN (Metropolitan Area Network)**

* Ek city ya bade area mein multiple LANs ko connect karta hai.

#### **WAN (Wide Area Network)**

* Alag-alag cities ya countries ke networks ko connect karta hai.

#### **PAN (Personal Area Network)**

* Ek person ke personal devices ko connect karta hai (e.g., Bluetooth, hotspot).

---

### **Organization of CN**

* Network ko kis tarah se design aur manage kiya gaya hai uska structure.

---

### **ISP (Internet Service Provider)**

* Wo companies jo humein internet connection provide karti hain.

---

### **Data Communication**

#### **Simplex Mode**

* Data sirf ek hi direction mein jaata hai (e.g., TV broadcast).

#### **Half Duplex Mode**

* Dono direction mein data ja sakta hai, par ek time pe ek hi direction (e.g., Walkie-Talkie).

#### **Full Duplex Mode**

* Dono direction mein data ek saath ja sakta hai (e.g., Phone call).

---

### **Network Structural and Architectural**

#### **Peer to Peer**

* Sab devices barabar hote hain aur directly connect kar sakte hain.

#### **Client/Server**

* Server se service milti hai aur client use karta hai.

#### **Advantages**

* Centralized control, easy backup, better security.

#### **Disadvantages**

* Server failure pe poora system down ho sakta hai, costly hota hai.

---

### **Layering Principle**

* Network ko layers mein divide karte hain taaki complex system ko manage kar sakein.

#### **Services Offered by Layer**

##### **Connection-Oriented**

* Connection banake data bhejna (Steps: Listen → Connect → Receive → Send → Disconnect).

##### **Connectionless**

* Bina connection banaye data bhejna (e.g., UDP), data directly bheja jaata hai.

---

### **OSI Reference Model (7 Layers)**

1. **Physical** – Actual transmission medium (cables, signals).
2. **Data Link** – Error detection/correction aur MAC address ka kaam.
3. **Network** – Routing aur IP addressing (e.g., IP protocol).
4. **Transport** – Reliable delivery (TCP/UDP).
5. **Session** – Session management between systems.
6. **Presentation** – Data translation, encryption, compression.
7. **Application** – User interface (e.g., browsers, email).

---

### **TCP/IP Protocol (4 Layers)**

1. **Network Access** – Physical + Data link layer combined.
2. **Internet** – Data routing, IP address handling (like OSI Network).
3. **Transport** – Reliable (TCP) ya fast (UDP) delivery.
4. **Application** – User services like HTTP, FTP, DNS.

---

### **UDP (User Datagram Protocol)**

* Fast, connectionless protocol, no guarantee of delivery.

---

### **TCP (Transmission Control Protocol)**

* Reliable, connection-oriented protocol, data loss check karta hai.

---

### **SCIP**

* Secure communication protocol military/secure data ke liye use hota hai.

---

### **Network Devices and Components**

#### **Hub**

* Data sab devices ko broadcast karta hai; smart nahi hota.

#### **Bridge**

* Do LANs ko connect karta hai aur traffic filter karta hai.

#### **Switch**

* Smart device jo data ko sahi destination device tak bhejta hai.

#### **Router**

* Alag-alag networks ko connect karta hai aur best route choose karta hai.

#### **WAP (Wireless Access Point)**

* Wireless devices ko network se connect karta hai.

---

### **Physical Layer**

#### **Network Topology**

* Network ka physical structure ya layout.

##### **Bus** – Single cable mein sab devices connected.

##### **Ring** – Devices ring shape mein connected hote hain.

##### **Star** – Sab devices ek central hub se connected.

##### **Mesh** – Har device har doosre se connected hota hai.

##### **Hybrid** – Mix hota hai different topologies ka.

##### **Tree** – Hierarchical star + bus combination.

#### **Transmission Media**

##### **Guided Media (Wired)**

* Physical wires mein data travel karta hai.

###### **Coaxial** – TV cable jaise wire.

###### **Twisted Pair** – Telephone wire jaise, twisted for noise reduction.

###### **Fiber Optics** – Light se fast data transfer hota hai.

###### **Stripline/Microstrip** – PCB ke andar ya surface pe signal path.

##### **Unguided Media (Wireless)**

* Air ke through signal travel karta hai.

###### **Radio Waves** – AM/FM, Wi-Fi.

###### **Microwaves** – Satellite, long-distance wireless.

###### **Infrared** – Remote control, short-range communication.

---

### **Digital to Digital Encoding**

#### **Line Coding**

* Digital signal ko encode karna for transmission.

##### **Unipolar** – Sirf ek polarity ka use karta hai.

##### **Polar**

* Two polarities ka use karta hai:

###### **NRZ-L** – Level based encoding.

###### **NRZ-I** – Inversion based on 1.

###### **RZ** – Signal midpoint pe zero hota hai.

###### **Manchester** – Clock + data dono include karta hai.

###### **Differential Manchester** – Transition pe based hota hai, more reliable.

##### **Bipolar** – 1s alternate polarities mein, 0s ke liye no signal.

---

### **Network Performance**

#### **Bandwidth** – Maximum data transfer capacity.

#### **Throughput** – Actual data transfer rate.

#### **Latency** – Time delay in data transmission.

#### **Bandwidth ≠ Delay Product** – Data amount that can be in transit at a time.

---

### **Transmission Impairment**

#### **Attenuation** – Signal weak ho jana.

#### **Distortion** – Signal shape change ho jana.

#### **Noise** – Unwanted signal/data.

---

### **Switching Techniques**

#### **Circuit Switching**

* Pura dedicated path banaya jata hai.

##### **Space** – Physical path reserved.

##### **Time** – Time slot reserve kiya jata hai.

#### **Message Switching**

* Message store and forward hota hai.

#### **Packet Switching**

* Data chhote packets mein split hota hai.

##### **Datagram** – Packets independent hote hain.

##### **Virtual Circuit** – Logical path banaya jata hai.

---

### **Multiplexing**

* Multiple signals ko ek medium pe bhejna.

#### **FDM (Frequency Division Multiplexing)** – Alag-alag frequencies use karta hai.

#### **TDM (Time Division Multiplexing)** – Alag time slots assign karta hai.

#### **WDM (Wavelength Division Multiplexing)** – Light wavelength use karta hai (optical).

#### **CDM (Code Division Multiplexing)** – Alag-alag code assign karta hai signals ko.

---

