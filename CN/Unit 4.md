### 🔸 **Transport Layer**

**Explanation:**
Transport layer network ka 4th layer hota hai jo sender aur receiver ke beech data ko reliable tareeke se bhejne ka kaam karta hai.
Yeh layer data ko chhote-chhote segments mein todta hai aur unka order maintain rakhti hai.
Iska kaam process-to-process communication karwana hota hai, jaise ek app se dusri app tak data bhejna.

**Example:**
Jab aap WhatsApp pe message bhejte ho, to transport layer ensure karta hai ki wo message sahi order mein aur bina kisi error ke receiver tak pahunche.
TCP (Transmission Control Protocol) transport layer ka ek example hai jo reliable delivery deta hai.

---

### 🔸 **Working of Transport Layer**

**Explanation:**
Yeh layer sender ke data ko break karke segments mein convert karti hai aur har segment ke saath header add karti hai.
Phir yeh segments ko receiver tak bhejti hai jahan unka order check karke wapas assemble kiya jata hai.
Yeh error detection aur correction ka bhi kaam karti hai.

**Example:**
Sochiye aap ek email bhej rahe ho — transport layer us email ko parts mein todkar bhejti hai, aur receiver side par usko sahi se jod diya jata hai.
Agar koi part corrupt ho jaye, to transport layer usko dobara mangti hai.

---

### 🔸 **At the Sender's Side**

**Explanation:**
Sender side par transport layer data ko break karta hai, sequence number assign karta hai, aur ensure karta hai ki har segment properly bheja jaaye.
Yeh multiplexing ka use karta hai — matlab multiple apps ke data ko alag-alag track karta hai.
Yeh ensure karta hai ki data correct destination tak jaaye.

**Example:**
Agar aap ek hi time pe music stream kar rahe ho aur file upload kar rahe ho, to transport layer dono ka data alag-alag handle karta hai.
Yeh dono ke liye unique port number assign karta hai.

---

### 🔸 **At the Receiver's Side**

**Explanation:**
Receiver side par transport layer segments ka order check karta hai, unhe jodta hai aur fir actual application ko data deta hai.
Agar koi segment missing ho, to request bhej kar fir se mangta hai.
Yeh demultiplexing karta hai — matlab multiple sources ke data ko identify karta hai.

**Example:**
Agar aapko YouTube video stream ho raha hai aur saath hi chat bhi kar rahe ho, to transport layer dono data streams ko alag pehchanta hai.
Video aur chat data alag-alag ports se process hote hain.

---

### 🔸 **Functions of Transport Layer**

**Explanation:**

1. **Segmentation and Reassembly** – Data ko todna aur jodna.
2. **Error Control** – Galtiyan detect karna aur correct karna.
3. **Flow Control** – Dono devices ki speed match karna.
4. **Connection Control** – Reliable (TCP) ya unreliable (UDP) connection establish karna.
5. **Multiplexing/Demultiplexing** – Alag apps ka data handle karna.

**Example:**
Jab aap ek game khel rahe ho aur call bhi kar rahe ho, to transport layer dono ka data handle karta hai bina mix kiye.
TCP call ke liye reliable connection provide karta hai, UDP game ke liye fast delivery.

---

### 🔸 **Process to Process Delivery**

**Explanation:**
Iska matlab hai data ek device ke andar specific application (process) se dusre device ke specific application tak pahunchta hai.
Yeh port numbers ke through hota hai — jaise browser ke liye port 80, email ke liye port 25.
Yeh end-to-end communication establish karta hai.

**Example:**
Agar aap apne browser se ek website open karte ho, to transport layer ensure karta hai ki data browser tak hi aaye, kisi aur app tak nahi.
Yeh browser aur server ke HTTP process ke beech direct link banata hai.

---

## 🔷 **Transmission Layer Protocols**

### 1️⃣ **TCP (Transmission Control Protocol)**

#### ✅ **Byte Streaming**

**Explanation:**
TCP data ko byte-by-byte stream karta hai — continuous data stream ki tarah.
Receiver side par yeh byte stream ko fir se original data mein convert karta hai.
Yeh streaming real-time nahi hoti, but reliable hoti hai.

**Example:**
Jab aap WhatsApp pe message bhejte ho, TCP usko bytes mein tod ke bhejta hai.
Receiver side par woh message properly jod diya jata hai.

---

#### ✅ **Connection Oriented**

**Explanation:**
TCP mein data bhejne se pehle 3-way handshake karke connection establish hota hai.
Iska matlab reliable link dono devices ke beech banta hai.
Connection close hone par proper termination hoti hai.

**Example:**
Jab aap ek website kholte ho, pehle browser aur server ke beech connection banta hai.
Iske baad hi actual data transfer hota hai.

---

#### ✅ **Full Duplex**

**Explanation:**
TCP full duplex mode support karta hai — dono taraf se data ek saath ja sakta hai.
Isme sender aur receiver simultaneously baat kar sakte hain.
Yeh real-time 2-way communication ke liye useful hai.

**Example:**
Online voice call mein dono log ek saath bol sakte hain — TCP isko allow karta hai.
Yeh normal phone call jaisa feel deta hai.

---

#### ✅ **Piggybacking**

**Explanation:**
Acknowledge karne ke liye alag message bhejne ke bajaye, TCP reply ke sath hi ACK bhejta hai.
Isse bandwidth save hoti hai aur efficiency badhti hai.
Ye technique dono taraf hoti hai — jab data + ACK ek sath jaate hain.

**Example:**
Jab receiver message receive karta hai, usi reply ke packet mein ACK bhi bhejta hai.
Alag se ACK bhejne ki zarurat nahi padti.

---

#### ✅ **Error Control**

**Explanation:**
TCP har segment mein checksum add karta hai jo data error check karta hai.
Agar koi segment corrupt ho jaye, to sender usko dobara bhejta hai.
Yeh reliable delivery ke liye zaroori hai.

**Example:**
Agar WhatsApp ka message incomplete aaye, TCP us part ko fir se bhejta hai.
Isse user ko correct message milta hai.

---

#### ✅ **Flow Control**

**Explanation:**
TCP receiver ki speed ke hisaab se data bhejta hai using **Window Size**.
Yeh ensure karta hai ki receiver overload na ho.
Sliding Window Protocol use hota hai.

**Example:**
Agar receiver slow device ho, to TCP usko dheere-dheere data bhejta hai.
Bina flow control ke receiver crash ho sakta hai.

---

#### ✅ **Congestion Control**

**Explanation:**
Agar network congest ho (traffic zyada ho), to TCP apni sending speed kam karta hai.
Isse packet loss aur delay kam hota hai.
Algorithms jaise **Slow Start, Congestion Avoidance** use hoti hain.

**Example:**
Agar bahut saare log ek website access karein, to TCP gradually data bhejta hai.
Isse network crash hone se bacha rahta hai.

---

### 🧾 **TCP Header Format**

> TCP ka har segment ek header ke saath aata hai jisme control info hoti hai.

#### 🔹 **Source Port** – Jahan se data aaya.

#### 🔹 **Destination Port** – Jahan data jaana hai.

#### 🔹 **Sequence Number** – Har byte ka order maintain karta hai.

#### 🔹 **Acknowledgment Number** – Confirm karta hai ki konsa byte receive hua.

#### 🔹 **HLEN** – Header length (kitna bada TCP header hai).

#### 🔹 **Reserved** – Future use ke liye 6 bits hoti hain (0 set hoti hain).

#### 🔹 **Control Bits** – Jaise SYN, ACK, FIN for control signals.

#### 🔹 **Window Size** – Flow control ke liye use hota hai.

#### 🔹 **Checksum** – Error detection ke liye use hota hai.

#### 🔹 **Urgent Pointer** – Urgent data ke liye priority batata hai.

#### 🔹 **Options** – Extra features ke liye use hota hai (jaise timestamp).

**Example:**
TCP header me agar SYN=1 aur ACK=0 ho, iska matlab connection start ho raha hai.
Agar FIN=1 ho to connection close ho raha hai.

---

### 🔗 **A TCP Connection**

**Explanation:**
TCP connection establish karne ke liye **3-Way Handshake** hota hai:

1. SYN →
2. SYN-ACK ←
3. ACK →
   Connection establish hone ke baad data send hota hai.

**Example:**
Aap jab browser se Google open karte ho, to TCP pehle server se handshake karta hai.
Fir page ka data receive hota hai.

---

---

## 2️⃣ **UDP (User Datagram Protocol)**

#### ✅ **Why to Use**

**Explanation:**
UDP fast aur lightweight protocol hai — koi connection establish nahi karta.
Ye real-time apps ke liye use hota hai jahan speed important hai aur thoda data loss acceptable hai.
Ye unreliable but faster hota hai.

**Example:**
Online gaming, live streaming, ya Zoom calls mein UDP use hota hai.
Agar 1-2 packets miss bhi ho gaye to farak nahi padta.

---

### 🧾 **UDP Header Format**

UDP header chhota aur simple hota hai — sirf 4 fields hoti hain:

#### 🔹 **Source Port** – Jahan se data aaya.

#### 🔹 **Destination Port** – Jahan data jaana hai.

#### 🔹 **Length** – Poore packet ka length (header + data).

#### 🔹 **Checksum** – Basic error checking ke liye.

**Example:**
Jab aap online video dekhte ho aur video buffering kam hoti hai, to mostly UDP use ho raha hota hai.
Agar 1 frame miss ho bhi jaye, video rukta nahi hai.

---

## 🔷 **TCP vs UDP (Comparison)**

| Feature         | TCP                            | UDP                           |
| --------------- | ------------------------------ | ----------------------------- |
| **Type**        | Connection-oriented            | Connection-less               |
| **Reliability** | Reliable (ACK, Retransmission) | Unreliable (no ACK, no retry) |
| **Speed**       | Slower due to checks           | Faster due to no checks       |
| **Ordering**    | Maintains order                | No guarantee of order         |
| **Use-case**    | Email, Web, File Transfer      | Gaming, VoIP, Streaming       |

**Example:**
File download uses **TCP** so that har byte correct aaye.
Online game uses **UDP** kyunki speed important hai, even if some packets drop.

---

## 🔹 **TCP Window Management System**

**Explanation:**
TCP mein window size decide karta hai ki ek baar mein kitna data bheja ja sakta hai.
Receiver window size batata hai (Flow Control), sender uske hisaab se bhejta hai.
Sliding Window Protocol use hota hai jisme window move hoti hai jab ACK milta hai.

**Example:**
Agar receiver window 5 hai, sender ek baar mein 5 segments bhej sakta hai.
ACK milte hi window slide hoti hai aur naye segment bheje jaate hain.

---

## 🔹 **Flow Control (TCP)**

**Explanation:**
Flow control ensure karta hai ki sender zyada fast na bheje jisse receiver overload ho jaye.
TCP iska use karta hai window size ke through.
Receiver apna window size bhejkar control karta hai data rate.

**Example:**
Agar receiver slow device ho, to wo chhoti window advertise karega.
Sender us window ke hisaab se data bhejega.

---

## 🔹 **Retransmission (TCP)**

**Explanation:**
Agar TCP ko lagta hai koi packet lost ya corrupt ho gaya, to wo us packet ko dobara bhejta hai.
Retransmission **timeout** ya **duplicate ACKs** se trigger hoti hai.
Isse reliable data transfer ensure hota hai.

**Example:**
Agar ACK nahi aaya 1 second ke andar, TCP us packet ko fir se bhejega.
Ya agar teen baar same ACK aaye, to bhi retransmit karega.

---

## 🔹 **Multiplexer (Sender side)**

**Explanation:**
Multiplexing ka matlab hota hai multiple applications ka data ek hi TCP connection se bhejna.
Transport layer har app ko alag **port number** assign karta hai.
Isse data ka source identify hota hai.

**Example:**
Aap YouTube aur WhatsApp ek sath use kar rahe ho, dono ka data alag port se bheja jaata hai.
TCP multiplexing se confusion nahi hota.

---

## 🔹 **Demultiplexer (Receiver side)**

**Explanation:**
Receiver side par TCP demultiplexing karta hai — alag-alag port numbers se data ko correct app tak pahunchata hai.
Isse pata chalta hai ki data kis process (e.g. browser, mail) ke liye hai.

**Example:**
Agar port 80 ka data aaye, to TCP use browser ko bhejta hai.
Port 25 ka data email app ko bheja jaata hai.

---

---

## 🔷 **QoS (Quality of Service)**

**Explanation:**
QoS ka matlab hai data delivery ka **quality** maintain rakhna — jaise delay, bandwidth, loss control.
TCP/UDP me QoS important hoti hai real-time applications ke liye.
QoS ensure karta hai ki priority data jaldi aur safe pahunch jaye.

**Example:**
Zoom call mein voice clear ho aur delay na ho, ye QoS ki wajah se hota hai.
Email me QoS kam important hoti hai kyunki delay chalta hai.

---

### ✅ **To Improve QoS**

#### 🔹 **Over Provisioning**

Zyada bandwidth provide karna taaki congestion na ho.
Example: 10 users ke liye 20 Mbps internet plan rakhna.

#### 🔹 **Buffering**

Temporary storage use karna taaki delay ya variation handle ho sake.
Example: YouTube video load hone ke pehle buffer karta hai.

#### 🔹 **Scheduling**

Important packets ko pehle bhejna based on priority.
Example: Voice packet ko first preference dena.

#### 🔹 **Traffic Shaping**

Network traffic ko control karna (speed, flow limit karke).
Example: Ek user ka download limit karna during peak hours.

---

## 🔷 **TCP Congestion Control**

### 🔹 **Congestion Window (cwnd)**

**Explanation:**
TCP ek variable window use karta hai — **cwnd** — jo network congestion ke hisaab se badhta ya ghatta hai.
Ye sender ka limit hai ki kitna data bheja ja sakta hai bina ACK mile.
Yeh dynamic hota hai — adjust hota hai with congestion policy.

**Example:**
Start me cwnd = 1, fir ACK aane par 2, 4, 8 ho jaata hai (exponential growth).
Agar congestion mile to cwnd reduce ho jaata hai.

---

### 🔹 **Congestion Policies**

#### ✅ **1. Slow Start**

Starting me TCP apna cwnd = 1 set karta hai aur har ACK pe exponential growth karta hai.
Ye tab tak hota hai jab tak threshold na mil jaye.

**Example:**
1 → 2 → 4 → 8 → 16... jab tak congestion nahi hoti.

---

#### ✅ **2. Congestion Avoidance**

Jab cwnd threshold tak pahuchta hai, uske baad TCP linear growth karta hai.
Ab har ACK pe cwnd = cwnd + 1 hota hai (slow increment).

**Example:**
Threshold = 16 ke baad cwnd = 17, 18, 19... (not exponential)

---

#### ✅ **3. Congestion Detection Phase**

##### 🔸 **Case 1: Retransmission due to Timeout**

Timeout hone par TCP assume karta hai ki congestion ho gayi hai.
TCP cwnd = 1 set karta hai (again slow start).

**Example:**
Agar 2 sec tak ACK nahi aaya, TCP slow start se dobara start karega.

---

##### 🔸 **Case 2: Retransmission due to Duplicate Acknowledgment**

Agar 3 same ACK continuously aaye, to TCP **fast retransmit** karta hai.
Fir cwnd = cwnd / 2 karke **congestion avoidance** pe chala jaata hai.

**Example:**
ACK 20 teen baar aaya, to TCP samjhta hai packet 21 lost hai.
Wo us packet ko immediately fir se bhejta hai.

---

