## 🖥️ 1. **Computer Network kya hota hai?**

Jab do ya do se zyada computers ya devices ek dusre se **connected hote hain** taaki **data, information ya resources** (jaise printer, internet, files) share kar sakein — use **Computer Network** kehte hain.

Example: Aapke ghar ka Wi-Fi — jab phone, laptop, TV sab ek Wi-Fi se connected hote hain — woh ek chhota network hota hai.

---

## 🎯 2. **Goals of Computer Network** (Network banane ke objectives)

1. **Resource Sharing**
   Ek printer ya file sab log use kar sakein – isliye network banate hain.

2. **Reliability**
   Agar ek device fail ho jaye, to dusra system kaam chalu rakh sake.

3. **Cost Saving**
   Ek hi internet connection, ek hi printer – sab use kar sakte hain, alag alag lene ki zarurat nahi.

4. **Communication**
   Email, chat, video call – sab network ke through possible hai.

5. **Scalability**
   Network ko badhaya ja sakta hai jab zarurat ho – naye devices easily add ho jate hain.

---

## 💡 3. **Applications of Computer Networks**

Computer networks ka use kahaan kahaan hota hai?

* **Education** – Online classes, notes sharing, exams.
* **Banking** – ATM, online banking, transaction alerts.
* **Business** – File sharing, meetings, emails.
* **Healthcare** – Patient records, online reports.
* **E-commerce** – Amazon, Flipkart jaise websites.

---

## 📡 4. **Categories of Network (Size aur Range ke hisaab se)**

### 🔸 1. **LAN – Local Area Network**

* Ek chhota network hota hai – jaise school, office ya ek building ke andar.
* Speed fast hoti hai.
* Example: Office ke sab computers ek router se connected.

### 🔸 2. **MAN – Metropolitan Area Network**

* City level ka network.
* Multiple LANs ko connect karta hai.
* Example: City ke sab colleges ka network.

### 🔸 3. **WAN – Wide Area Network**

* Bohot large area cover karta hai – jaise desh ya duniya.
* Internet bhi ek WAN hai.
* Speed kam ho sakti hai compared to LAN.

### 🔸 4. **PAN – Personal Area Network**

* Personal devices ke beech ka chhota network.
* Jaise mobile aur Bluetooth headphones ka connection.

---

## 🏢 5. **Organization of Computer Network**

Network ko manage karne ke liye humein **ISP** chahiye hota hai.

### 🌐 **ISP – Internet Service Provider**

* Jo humein internet connection deta hai.
* Example: Jio, Airtel, BSNL.
* ISP humein IP address, bandwidth aur data access provide karta hai.

---

## 🔄 6. **Data Communication Modes**

Ye batata hai ki data kis tarah se devices ke beech transfer hota hai.

### ▶️ 1. **Simplex Mode**

* Data **sirf ek direction** mein jaata hai.
* Jaise TV broadcast – sirf dekha jaata hai, reply nahi ja sakta.

### 🔁 2. **Half Duplex Mode**

* Dono directions mein data ja sakta hai, **lekin ek time pe ek hi direction**.
* Example: Walkie-Talkie – ek bolta hai, dusra sunta hai.

### 🔄 3. **Full Duplex Mode**

* Dono devices ek saath data send aur receive kar sakte hain.
* Example: Mobile call – dono log ek saath baat kar sakte hain.

---

## 🧱 7. **Network Structure and Architecture**

Do main types hote hain:

### 🤝 1. **Peer to Peer (P2P)**

* Sab computers barabar hote hain.
* Har computer dusre se directly data exchange kar sakta hai.
* **Advantage**: Simple, low cost.
* **Disadvantage**: Security kam hoti hai, zyada devices manage karna mushkil.

### 🖥️ 2. **Client-Server Architecture**

* Ek main computer (server) hota hai, baaki sab clients.
* Clients server se data ya service mangte hain.
* **Advantage**: Secure, centralized control.
* **Disadvantage**: Server fail ho gaya to sab ruk jaata hai, costly bhi ho sakta hai.

---

## 📚 1. **Layering Principle (Network Architecture ka base concept)**

Networking mein **layering** ka matlab hota hai ki poora communication process ko **chhoti-chhoti layers** mein divide kar dete hain.
Har layer ka **apna kaam** hota hai, aur wo sirf apni upar/neeche wali layer se interact karti hai.

### 🎯 Layering ke Fayde (Benefits):

* Complex system ko easy banata hai.
* Har layer **independent** hoti hai (agar ek layer update ho, to doosri layers ko farak nahi padta).
* **Troubleshooting** easy hoti hai.
* Design and development modular ban jaata hai.

---

## 🧾 2. **Services Offered by Layers**

### 🔗 **A. Connection-Oriented Service**

Isme **connection establish karna padta hai** data bhejne se pehle. Har step defined hota hai:

1. **Listen** – Receiver wait karta hai kisi se connection ke liye.
2. **Connect** – Sender receiver se connection banata hai.
3. **Receive** – Receiver data accept karta hai.
4. **Send** – Sender data bhejta hai.
5. **Disconnect** – Dono connection close karte hain.

🟢 Example: **TCP (Telephone call jaisa)**

---

### 📤 **B. Connectionless Service**

Isme **connection banane ki zarurat nahi hoti**. Bas data bhejo.

* **Unidata** – Ek hi direction mein data jaata hai.
* **Faculty Report** – (Ye shayad example diya gaya hai?) Matlab directly ek message/packet bhejna without expecting a reply.

🟢 Example: **UDP (SMS jaisa)**

---

## 🧱 3. **OSI Reference Model (7 Layers)**

OSI model ek **theoretical model** hai jo batata hai kaise data ek device se dusre device tak jata hai — **7 layers** ke through:

1. **Physical Layer**

   * Bits ko cables ya signals mein convert karta hai.
   * Example: Cables, voltages, connectors.

2. **Data Link Layer**

   * Frames banata hai.
   * Error detection karta hai.
   * MAC address yahi hota hai.
   * Example: Switch.

3. **Network Layer**

   * Path decide karta hai.
   * IP address yahi hota hai.
   * Example: Router.

4. **Transport Layer**

   * Data ko chhote parts mein todta hai (segments).
   * TCP/UDP yahi pe kaam karte hain.
   * Ensures reliable ya fast delivery.

5. **Session Layer**

   * Session banata hai (start-stop control).
   * Example: Video conferencing session.

6. **Presentation Layer**

   * Data ka format set karta hai (encryption/decryption).
   * Example: JPEG, MP3, PDF format.

7. **Application Layer**

   * User ke saath direct interact karta hai.
   * Example: Browser, Email client.

💡 Trick to Remember:
**A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing

---

## 🌐 4. **TCP/IP Model (4 Layers)**

Ye real-world mein use hone wala model hai. OSI ka practical version samjho:

1. **Application Layer**

   * OSI ke Application + Presentation + Session layers ka combined version.
   * Browser, Email, etc.

2. **Transport Layer**

   * TCP/UDP yahi hota hai.
   * Data ko send/receive manage karta hai.

3. **Internet Layer**

   * IP addressing & routing.
   * Example: Routers, IP packets.

4. **Network Access Layer (Link Layer)**

   * Hardware level pe kaam karta hai.
   * MAC address, Ethernet, etc.

💡 TCP/IP model zyadatar networking systems mein use hota hai, including Internet.

---

## 📦 5. **TCP vs UDP vs SCIP**

### 🔁 **TCP (Transmission Control Protocol)**

* **Connection-oriented**
* Reliable (data loss nahi hota)
* Slow but accurate
* Example: Web browsing, email

### ⚡ **UDP (User Datagram Protocol)**

* **Connectionless**
* Fast but unreliable
* Real-time apps mein use hota hai
* Example: Video streaming, gaming

### 🔐 **SCIP (Secure Communications Interoperability Protocol)**

* Security protocol used mostly by **military or government**
* Secure encrypted voice/data communication
* Kaafi specific usage hota hai, general public ke liye nahi

---

## 🛠️ 6. **Network Devices and Components**

Bilkul bhai 😎 Hinglish version ready hai:

---

### 🔹 1. **Hub**

* Sabse simple network device hota hai.
* Jo data aata hai, sab connected devices ko bhej deta hai.
* Na filtering karta hai, na security, na koi smartness.
* Ab outdated hai, switches ne replace kar diya.

---

### 🔹 2. **Bridge**

* Do LAN segments ko connect karta hai.
* MAC address ke basis pe data filter karta hai.
* Sirf jis device ko data chahiye, usi ko bhejta hai.
* Basically do LANs ko jodne ke kaam aata hai.

---

### 🔹 3. **Switch**

* Fast aur secure device hota hai.
* Data sirf intended device ko bhejta hai.
* MAC address check karke decide karta hai kisko bhejna hai.
* Mostly star topology me use hota hai.

---

### 🔹 4. **Router**

* Powerful device hai jo multiple networks ko connect karta hai.
* IP address dekhke decide karta hai data kahan bhejna hai.
* Internet se connect karne ke liye use hota hai.
* Example: Ghar ka Wi-Fi router.

---

### 🔹 5. **WAP (Wireless Access Point)**

* Wireless devices ko network se connect karta hai.
* Wi-Fi ke liye use hota hai.
* Wireless aur wired network ke beech bridge ka kaam karta hai.

---

## ⚙️ **1. Physical Layer – Kya hota hai?**

Ye OSI model ki **sabse neeche wali layer** hoti hai.
Iska kaam hota hai:

* Bits ko **signals mein convert karna** (electrical ya optical ya wireless).
* Devices ko **physically connect karna**.
* Cable, connector, voltage level, frequency etc. ye sab yahin decide hota hai.

Physical Layer sirf **data bhejti hai**, uska matlab ya format nahi samajhti.

---

## 🔗 **2. Network Topology (Network ka Physical Design)**

**Topology** ka matlab hota hai ki devices ko kaise physically connect kiya gaya hai.

### 🔹 A. **Bus Topology**

* Ek single cable hoti hai jisme sab devices connected hote hain.
* Cheap hai but agar main cable fail ho gayi to pura network down.

### 🔹 B. **Ring Topology**

* Devices ek circular ring mein connected hote hain.
* Data ek hi direction mein move karta hai.
* Agar ek node fail ho jaye, to poora ring ruk sakta hai (unless dual ring ho).

### 🔹 C. **Star Topology**

* Sab devices ek central device (usually switch) se connected hote hain.
* Easy to manage, fast performance.
* Agar central device fail ho gaya to network down.

### 🔹 D. **Mesh Topology**

* Har device, har dusre device se connected hota hai.
* Very reliable, lekin costly.
* Zyada cables lagte hain.

### 🔹 E. **Tree Topology**

* Combination of **Star + Bus**.
* Hierarchical structure hota hai.
* Big networks ke liye useful.

### 🔹 F. **Hybrid Topology**

* Combination of two or more topologies.
* Flexible and scalable.

---

## 🌐 **3. Transmission Media (Data travel ka rasta)**

Do type ke media hote hain:

---

### 🧵 **A. Guided Media (Wired Media)**

Data ek **physical path** ke through travel karta hai.

#### 🔸 1. **Coaxial Cable**

* Inner copper wire + outer insulation.
* TV cable mein use hoti hai.
* Speed moderate, interference kam.

#### 🔸 2. **Twisted Pair Cable**

* Do copper wires twist kiye hote hain.
* Two types:

  * **UTP** – Unshielded
  * **STP** – Shielded
* Internet LAN mein commonly use hota hai.

#### 🔸 3. **Fiber Optic Cable**

* Data light signals ke form mein travel karta hai.
* **Very high speed**, long distance.
* Expensive, but secure.

#### 🔸 4. **Stripline**

* PCB (printed circuit board) ke andar signal lines hoti hain.
* RF circuits mein use hota hai.

#### 🔸 5. **Microstrip Line**

* Ek side grounded hoti hai, doosri side signal line.
* High-frequency signals ke liye.

---

### 📡 **B. Unguided Media (Wireless Media)**

Data air ke through transmit hota hai — bina kisi wire ke.

#### 🔸 1. **Radio Waves**

* Wireless communication mein use hote hain.
* FM/AM radio, Wi-Fi.

#### 🔸 2. **Microwaves**

* Line of sight (seedhe rasta) chahiye hota hai.
* Satellite communication mein use hota hai.

#### 🔸 3. **Infrared**

* Short range ke liye.
* TV remote, wireless mouse mein hota hai.

---

## 💡 **4. Digital to Digital Encoding (Line Coding)**

Digital data ko **digital signals** mein convert karne ke technique ko bolte hain **Line Coding**.

Line coding 3 main types mein hota hai:

---

### 🔸 A. **Unipolar**

* Sirf 1 voltage level hota hai (positive only).
* Simple but inefficient.
* Zyada power consume karta hai.

---

### 🔸 B. **Polar**

* 2 voltage levels use karta hai: Positive & Negative.
* 3 subtypes:

#### ✅ **1. NRZ (Non-Return to Zero)**

Data 0 ya 1 ke hisaab se signal level change karta hai.

* **NRZ-L (Level)**:
  1 = High Voltage, 0 = Low Voltage (fixed pattern).
  Signal directly bit value pe depend karta hai.

* **NRZ-I (Invert)**:
  1 = Voltage change hoti hai,
  0 = No change.
  Change bit ke according hoti hai.

#### ✅ **2. RZ (Return to Zero)**

* Signal har bit ke bich mein **0 pe wapas aata hai**.
* Zyada bandwidth use karta hai.

#### ✅ **3. Manchester**

* Each bit ke liye ek **transition hoti hai** middle mein:

  * 0 = High to Low
  * 1 = Low to High
* Clocking built-in hoti hai.
* Reliable, but bandwidth high.

#### ✅ **4. Differential Manchester**

* Har bit ke liye **transition hoti hi hoti hai** middle mein.
* 0 = Starting mein transition
* 1 = No transition at start
* Noise resistance achha hota hai.

---

### 🔸 C. **Bipolar**

* 3 levels: Positive, Negative, and Zero.
* 0 = No voltage
* 1 = Alternate between + and –
* Zyada efficient hota hai unipolar se.

---


