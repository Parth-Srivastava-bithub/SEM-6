## 🔷 **Transport Layer**

* **Working**: Sender aur receiver ke beech reliable data transfer ka kaam karta hai.
* **At the Sender's Side**: Data ko segments mein todta hai aur headers ke sath bhejta hai.
* **At the Receiver's Side**: Segments ko jodta hai aur correct app ko data forward karta hai.
* **Functions**: Segmentation, flow control, error control, connection control, multiplexing.
* **Process-to-Process Delivery**: Data ko ek app se dusri specific app tak bhejta hai using port numbers.

---

## 🔷 **Transmission Layer Protocols**

### ✅ **TCP (Transmission Control Protocol)**

* **Byte Streaming**: Data ko continuous byte stream mein bhejta hai.
* **Connection Oriented**: Data bhejne se pehle 3-way handshake karta hai.
* **Full Duplex**: Dono taraf se simultaneously data bhej sakte hain.
* **Piggybacking**: ACK ko data ke sath combine karke bhejta hai for efficiency.
* **Error Control**: Checksum se error detect karta hai, galat packet dobara bhejta hai.
* **Flow Control**: Receiver ki capacity ke according sender ka speed control karta hai.
* **Congestion Control**: Network congest ho to sender data bhejna slow karta hai.

---

## ✅ **TCP Header Format**

* **Source Port**: Jis process ne data bheja uska port number.
* **Destination Port**: Jis process ko data bhejna hai uska port number.
* **Sequence Number**: Data byte ka order batata hai.
* **Acknowledgment**: Confirm karta hai ki kaunsa byte receive ho chuka hai.
* **HLEN**: Header ki length define karta hai.
* **Reserved**: Future use ke liye rakha gaya unused bits.
* **Control Bit**: Flags jaise SYN, ACK, FIN etc. ko define karta hai.
* **Window Size**: Flow control ke liye receiver ki capacity batata hai.
* **Checksum**: Error detect karne ke liye use hota hai.
* **Urgent Pointer**: Urgent data ko priority dene ke liye.
* **Options**: Extra features (e.g., timestamp) ke liye hota hai.

---

## ✅ **A TCP Connection**

* **TCP Connection**: 3-way handshake (SYN → SYN-ACK ← ACK) ke through connection banata hai.

---

### ✅ **UDP (User Datagram Protocol)**

* **Why to Use**: Fast & light protocol for real-time apps, no connection needed.
* **UDP Header**:

  * **Source Port**: Data bhejne wale ka port.
  * **Destination Port**: Data receive karne wale ka port.
  * **Length**: UDP header + data ki total length.
  * **Checksum**: Basic error detection ke liye.

---

## 🔷 **TCP vs UDP**

* **TCP**: Reliable, connection-based, slow but secure.
* **UDP**: Unreliable, connectionless, fast but may drop packets.

---

## 🔷 **TCP Window Management System**

* **Window Management**: Receiver ki advertised window ke hisaab se sender data bhejta hai.

---

## 🔷 **Flow Control (TCP)**

* **Flow Control**: Receiver overload na ho isliye sender ka speed control karta hai (via window size).

---

## 🔷 **Retransmission (TCP)**

* **Retransmission**: Lost/corrupted segment ko dobara bhejna (timeout ya duplicate ACK se).

---

## 🔷 **Multiplexer (Sender Side)**

* **Multiplexer**: Multiple apps ka data ek line se bhejna using port numbers.

---

## 🔷 **Demultiplexer (Receiver Side)**

* **Demultiplexer**: Received data ko correct app tak bhejna using destination port.

---

## 🔷 **QoS (Quality of Service)**

* **QoS**: Data delivery ki quality maintain karta hai (delay, jitter, loss kam karta hai).

---

### ✅ **To Improve QoS**

* **Over Provisioning**: Extra bandwidth dena taaki congestion na ho.
* **Buffering**: Data temporarily store karke smooth delivery ensure karna.
* **Scheduling**: High-priority data ko pehle bhejna.
* **Traffic Shaping**: Traffic ko manage karna to avoid congestion.

---

## 🔷 **TCP Congestion Control**

* **Congestion Window**: Sender ka limit ki kitna data bhej sakta hai at a time.
* **Congestion Policy**:

  * **Slow Start**: Start mein cwnd exponentially badhta hai.
  * **Congestion Avoidance**: Cwnd slowly (linearly) badhta hai after threshold.
  * **Congestion Detection Phase**:

    * **Case 1: Timeout** – TCP assumes loss & cwnd = 1 se restart karta hai.
    * **Case 2: Duplicate ACKs** – Fast retransmit karta hai & cwnd half ho jata hai.

---

