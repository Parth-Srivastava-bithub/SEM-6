### ✅ **Application Layer**

User aur network ke beech interaction aur services provide karne wali OSI model ki top layer hai.

---

### ✅ **Functions of Application Layer**

User interface dena, data formatting karna aur network services (jaise email, file transfer) provide karna.

---

### ✅ **Protocols of the Application Layer in OSI Model**

* **SMTP** – Emails ko send karne ke liye use hota hai via mail servers.
* **HTTP** – Web pages ko browser aur server ke beech transfer karta hai.
* **FTP** – Network par files upload/download karne ke liye use hota hai.
* **DNS** – Domain name ko IP address me convert karta hai.
* **SNMP** – Network devices ka status monitor aur manage karta hai.
* **TELNET** – Remote system ko text-based access provide karta hai.

---

### ✅ **World Wide Web**

Internet ka part jo web pages aur content ko globally access karta hai.

---

### ✅ **Key Components of WWW**

Web browser, web server, HTTP, URL aur DNS WWW ke main components hain.

* **DNS** – Domain name ko IP me convert karta hai.
* **Generic Domains** – Global use wale domains jaise .com, .org.
* **Country Domains** – Specific countries ke domains jaise .in, .us.
* **Inverse Domains** – IP address se domain name find karne ke liye hote hain.
* **Working of DNS** – URL type karne ke baad DNS IP address provide karta hai.
* **Recursive Resolution** – DNS server client ke liye full answer dhoondta hai.
* **Iterative Resolution** – DNS server client ko agle server ka address deta hai.

---

### ✅ **HTTP**

Web browser aur server ke beech web data exchange karta hai over port 80.

---

### ✅ **FTP**

Network par files ka transfer karta hai using client-server model over port 21.

---

### ✅ **HTTPS**

HTTP ka secure version hai jisme SSL/TLS se data encrypt hota hai (port 443).

---

### ✅ **Remote Login Protocol**

Remote system ko command-line access dene wale protocols jaise TELNET aur SSH.

---

### ✅ **TELNET**

Remote login ke liye plain text connection provide karta hai (non-secure).

---

### ✅ **SSH**

Remote login ke liye encrypted aur secure connection provide karta hai.

---

### ✅ **Network Management**

Network devices ka monitoring, configuration aur control ka process hai.

---

#### **SNMP (Simple Network Management Protocol)**

Network devices ko remotely monitor aur manage karne ke liye protocol hai.

* **Manager** – Network device data collect karne wala centralized system.
* **Agent** – Device pe installed software jo manager ko info bhejta hai.
* **MIB** – Database jisme network objects ki details hoti hain.

---

### ✅ **SMTP**

Emails ko send karne ke liye server-based protocol hai.

---

### ✅ **MIME**

Email me multimedia content (image, video, etc.) bhejne ke liye format provide karta hai.

---

### ✅ **POP3**

Emails ko download kar leta hai aur server se delete kar deta hai (offline access).

---

### ✅ **IMAP**

Emails ko server par hi store aur sync karta hai across multiple devices.

---

### ✅ **How TFTP is Different from FTP (Table Format)**

| Feature        | TFTP                        | FTP                          |
| -------------- | --------------------------- | ---------------------------- |
| Protocol       | UDP (Port 69)               | TCP (Port 21)                |
| Authentication | Nahi hoti                   | Username/password required   |
| Usage          | Small config files transfer | Large file transfer          |
| Reliability    | Less reliable               | Reliable with error checking |
| Directory      | Directory access nahi       | Directory listing possible   |

---

### ✅ **Data Compression**

* **Lossless** – Data compress hone ke baad original form me recover hota hai.
* **Lossy** – Compress hone ke baad data ka kuch part permanently lost ho jata hai.

---

### ✅ **Cryptography**

* **Symmetrical** – Same key se encryption aur decryption hota hai.
* **Asymmetrical** – Public key se encrypt aur private key se decrypt hota hai.
* **Digital Signature** – Message ki authenticity verify karta hai using sender's private key.

---

### ✅ **RSA Algorithm – Steps**

1. Do prime numbers choose karo (p, q)
2. N = p × q aur φ(n) = (p-1)(q-1) nikaalo
3. Public key (e, N) choose karo
4. Private key (d, N) calculate karo
5. Encrypt: C = M^e mod N, Decrypt: M = C^d mod N

---

