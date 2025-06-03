
## 📘 **LINK LAYER - Hinglish Notes with Examples**

---

### 1. **Framing (Data ko structure mein todna)**

#### 🔹 **Character Count**

* **Explanation:** Frame ke starting mein ek number hota hai jo total characters batata hai.
* **Example:**

  ```
  [5, A, B, C, D] → 5 characters total.
  ```

  Agar koi byte galat ho gaya (jaise B corrupt ho gaya), to receiver framing samajh nahi paayega.

---

#### 🔹 **Byte Stuffing**

* **Explanation:** Special character (e.g., FLAG = `F`) ko use karte hain frame ke start/end batane ke liye. Agar data mein `F` aa gaya to usse ESC (escape character) ke sath bhejte hain.
* **Example:**

  * Data: `A F B`
  * Stuffed: `F A ESC F B F`
  * FLAG = F, ESC = Escape character.

---

#### 🔹 **Bit Stuffing**

* **Explanation:** Jab 5 continuous 1s aate hain to ek 0 insert karte hain taaki receiver samajh sake ye data hai, frame end nahi.
* **Example:**

  * Original: `01111110`
  * Stuffed: `011111010` (5 1s ke baad ek 0 daal diya)

---

#### 🔹 **Physical Layer Coding Violation**

* **Explanation:** Kuch special voltage ya signals ka use karte hain framing ke liye.
* **Example:** Normal data voltages hote hain +5V, -5V. Framing ke liye +10V use karte hain (jo data mein nahi hota).

---

### 2. **Error Detection and Correction**

---

#### 🔹 **Parity Bit**

* **Explanation:** Even ya Odd parity use karte hain. Ek bit add hoti hai taaki total 1s even/odd ho jaye.
* **Example:**

  * Data: `1000001` (2 ones) → Even parity = `0` → Transmit: `10000010`

---

#### 🔹 **Checksum**

* **Explanation:** Data ko chunks mein divide karte hain, unka sum nikal kar 1’s complement bhejte hain.
* **Example:**

  * Data blocks: `1101 0010`, `1010 1011`
  * Sum: `10111101`
  * 1’s complement: `01000010` → Checksum

---

#### 🔹 **Cyclic Redundancy Check (CRC)**

* **Explanation:** Polynomial division ke through check bits nikalte hain.
* **Example:**

  * Data: `11010011101100`
  * Generator: `1011` (CRC polynomial)
  * CRC bits milke full message banega.

---

### 3. **Flow Control**

Data sender fast ho sakta hai aur receiver slow, to data loss na ho isliye **flow control protocols** ka use hota hai.

---

#### 🔹 **Elementary Protocols (Stop-and-Wait)**

* **Explanation:** Sender ek frame bhejta hai, fir wait karta hai ACK (acknowledgment) ka.
* **Example:**

  ```
  Sender → [Frame 1] → Receiver
  Sender ← [ACK 1] ← Receiver
  ```

---

#### 🔹 **Sliding Window Protocols**

* **Explanation:** Multiple frames ek sath bhej sakte hain (window size ke hisaab se), aur ACK ke base pe window slide hoti hai.

##### 🔸 Types:

1. **Go-Back-N**

   * Error aane pe purane frames wapas bhejte hain.
   * Example: Window size = 4, Sender ne frame 0-3 bheje. Frame 2 corrupt ho gaya → Frame 2, 3 wapas bhejne padenge.

2. **Selective Repeat**

   * Sirf error waala frame dubara bhejte hain.
   * Example: Frame 2 corrupt → Sirf Frame 2 wapas bhejna.

---

## 📘 **MEDIUM ACCESS CONTROL & LAN**

---

### 1. **Channel Allocation**

Jab multiple devices ek medium share karte hain, to channel allocate karna padta hai.

---

#### 🔹 **Static Allocation**

* Example: TDMA (Time Division Multiple Access) – har device ko fixed time slot milta hai.

#### 🔹 **Dynamic Allocation**

* Example: CSMA (Carrier Sense Multiple Access) – sab devices channel sunte hain, agar free hai to send karte hain.

---

### 2. **Multiple Access Protocols**

#### 🔹 **ALOHA (Pure & Slotted)**

1. **Pure ALOHA**

   * Kabhi bhi send kar sakte ho. Agar collision hua to resend.
   * Efficiency ≈ 18%

2. **Slotted ALOHA**

   * Fixed time slots mein hi send kar sakte ho.
   * Efficiency ≈ 36%

---

#### 🔹 **CSMA/CD (Collision Detection)**

* Sender pehle channel sunta hai. Agar channel free ho, to send karta hai.
* Collision hone par send band kar deta hai, aur backoff karke fir try karta hai.
* Used in **Ethernet**

---

#### 🔹 **CSMA/CA (Collision Avoidance)**

* Collision hone se pehle avoid karte hain.
* Wireless LANs (Wi-Fi) mein use hota hai.
* ACK system + random backoff.

---

### 3. **LAN Standards**

* **Ethernet (IEEE 802.3)** – Wired LAN
* **Wi-Fi (IEEE 802.11)** – Wireless LAN
* **Token Ring (IEEE 802.5)** – Ring topology mein token pass karke data bhejna

---

### 4. **Link Layer Devices**

#### 🔹 **Switch**

* Frame ko destination MAC address ke basis pe forward karta hai.
* High speed, multiple ports.

#### 🔹 **Bridge**

* Do LANs ko connect karta hai.
* Learning Bridge: MAC table bana ke decide karta hai data ko kis port se bhejna hai.
* **Spanning Tree Algorithm (STA):** Loops avoid karta hai bridge network mein.

---

### ✅ **Summary Table**

| Concept                  | Method                  | Example                          |
| ------------------------ | ----------------------- | -------------------------------- |
| Framing                  | Byte Stuffing           | FLAG = F, ESC = escape           |
| Error Detection          | Parity Bit              | Even parity: `1000001 + 0`       |
| Flow Control             | Stop-and-Wait           | Frame → ACK → Next Frame         |
| Access Protocols         | CSMA/CD, ALOHA          | Ethernet, Slotted ALOHA          |
| Sliding Window Protocols | Go-Back-N, Selective RP | Frame 2 error → resend 2,3 (GBN) |
| LAN Devices              | Switch, Bridge          | MAC-based forwarding             |

---


