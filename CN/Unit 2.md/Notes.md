# **Unit 2 Notes**

### **Data Link Layer – The Bodyguard of Data 🚔**

---

### **1. 🛠 Services of Data Link Layer**

➡ Ensures smooth and safe delivery of data **node to node** (like security between apartments in a building).

---

### **2. 📦 Framing – “Packing the Data Parcel”**

**Why?** So the receiver knows where a message starts and ends.

🧩 **Parts of a Frame**:

* **Header** – Sender info, address, etc.
* **Payload** – Actual data
* **Trailer** – Error-check info

📏 **Types of Framing**:

* **Fixed Size** – Size is always same. Easy but wasteful.
* **Variable Size** – Size changes. Needs markers or counters.

  * *Byte Stuffing*: Add special characters to mark frames
  * *Bit Stuffing*: Add extra bits after certain patterns

🧠 **Mini Story**: Imagine mailing letters. Fixed-size = All envelopes same, even if data is small. Variable = Envelope size fits content, but you must mark it clearly.

---

### **3. 🚨 Error Detection and Correction – “CCTV for Data Crimes”**

#### 🧨 Types of Errors:

* **Single-bit error**: Only 1 bit flipped
* **Burst error**: 2+ bits flipped together

---

### **4. 🧮 Techniques**

#### ✅ **Simple Parity Check** –

Adds 1 bit to make total 1s even (Even parity) or odd (Odd parity)
*Limitation:* Can’t detect all errors, especially burst

#### 🧮 **Two-Dimensional Parity** –

Apply parity row-wise + column-wise
✔ Better at catching burst errors

#### 🧮 **Checksum** –

Split data into blocks, sum all, then send the **1’s complement**
Receiver adds all + checksum, result must be all 1s

#### 🔁 **Cyclic Redundancy Check (CRC)** –

Best! Treats data as binary polynomial, divides it by a generator
Sends remainder with data; receiver checks if division leaves 0
💡 High accuracy. Like a strict math teacher.

---

### **Quick Recall Story 🔁**

Think of the Data Link Layer as the **post office clerk**. He wraps (frames) your parcel, ensures no one messes with it (error detection), and if needed, **rebuilds it right** before passing it on. CRC is his best detective.

---

