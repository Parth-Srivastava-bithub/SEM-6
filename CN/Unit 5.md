**Topic: Protocols of the Application Layer in OSI Model**

---

### 1. **SMTP (Simple Mail Transfer Protocol)**

SMTP email bhejne ke liye use hota hai, especially sender se receiver ke mail server tak.
Ye protocol sirf text-based messages transfer karta hai aur mainly push model follow karta hai.
Iska use mail clients jaise Outlook ya Gmail ke background me hota hai.
**Example:** Jab aap kisi ko email bhejte ho, to SMTP us email ko mail server tak pahuchata hai.

---

### 2. **HTTP (HyperText Transfer Protocol)**

HTTP web browsers aur web servers ke beech communication ke liye use hota hai.
Ye request-response model par kaam karta hai jisme client request bhejta hai aur server response deta hai.
Ye mainly websites ko access karne aur HTML pages transfer karne me use hota hai.
**Example:** Jab aap [www.google.com](http://www.google.com) type karte ho, HTTP server se data fetch karta hai.

---

### 3. **FTP (File Transfer Protocol)**

FTP large files ko network par transfer karne ke liye use hota hai.
Ye client-server architecture follow karta hai aur authentication (username/password) bhi support karta hai.
Ye data transfer ke liye do channels use karta hai: control aur data channel.
**Example:** Jab aap kisi server se software download karte ho FTP client ke through, to FTP ka use hota hai.

---

### 4. **DNS (Domain Name System)**

DNS domain names (like google.com) ko IP addresses (like 142.250.64.78) me convert karta hai.
Isse users ko IP ya numbers yaad rakhne ki zarurat nahi hoti, sirf naam yaad rakhna hota hai.
Ye hierarchical system hota hai jo distributed servers pe based hota hai.
**Example:** Jab aap google.com type karte ho, DNS use hota hai uska IP address dhoondhne ke liye.

---

### 5. **SNMP (Simple Network Management Protocol)**

SNMP network devices jaise routers, switches, aur servers ko monitor aur manage karne ke liye use hota hai.
Iska use administrators karte hain to track performance aur troubleshoot problems.
Ye protocol network devices ke status ko read aur control kar sakta hai remotely.
**Example:** Jab ek admin apne network ka status monitor karta hai, SNMP use hota hai device information collect karne ke liye.

---

### 6. **TELNET (Telecommunication Network)**

TELNET kisi remote device ko access karne aur control karne ke liye use hota hai, jaise remote login.
Ye text-based communication allow karta hai via command-line interface.
Security kam hone ke wajah se aajkal iski jagah SSH zyada use hota hai.
**Example:** Jab koi network engineer remotely kisi server pe login karta hai command-line se, to wo TELNET use kar sakta hai.

---

### **1. SMTP (Simple Mail Transfer Protocol)**

* Email bhejne ke liye use hota hai (sending side par).
* Sirf text-based messages handle karta hai.
* Client se server aur server se server mail transfer karta hai.
* Push protocol hai – data ko actively bhejta hai.
* Port number 25 use karta hai.
  **Example:** Gmail ka backend SMTP use karta hai jab aap email bhejte ho.

---

### **2. HTTP (HyperText Transfer Protocol)**

* Web pages aur content transfer karne ke liye use hota hai.
* Client-server model pe based hota hai (browser → server).
* Stateless protocol hai – har request independent hoti hai.
* Web content jaise HTML, images transfer karta hai.
* Port 80 par kaam karta hai.
  **Example:** Jab aap browser me google.com open karte ho, HTTP use hota hai.

---

### **3. FTP (File Transfer Protocol)**

* Files ko network ke through transfer karne ke liye use hota hai.
* Client-server model follow karta hai.
* Do channels use karta hai – control aur data.
* Secure version FTPS ya SFTP ke naam se aata hai.
* Port 21 use karta hai (control channel).
  **Example:** Jab aap kisi website pe software download karte ho via FTP, to ye protocol kaam karta hai.

---

### **4. DNS (Domain Name System)**

* Domain names ko IP addresses me convert karta hai.
* Hierarchical aur distributed database system hai.
* Human-friendly names ko machine-readable format me badalta hai.
* Recursive aur iterative query ka use karta hai.
* Port 53 par kaam karta hai.
  **Example:** Jab aap youtube.com type karte ho, DNS uska IP address dhoondhta hai.

---

### **5. SNMP (Simple Network Management Protocol)**

* Network devices ko monitor aur manage karne ke liye use hota hai.
* Devices ka status, performance aur faults track karta hai.
* Agents aur manager architecture follow karta hai.
* Data ko MIB (Management Information Base) ke through read karta hai.
* Port 161 (for queries) and 162 (for traps) use karta hai.
  **Example:** Network admin router ka performance SNMP se monitor karta hai.

---

### **6. TELNET (Telecommunication Network)**

* Remote login aur command-line access provide karta hai.
* Plain text me data send karta hai (secure nahi hota).
* Command execution ke liye remote system access deta hai.
* Simple terminal-based connection hoti hai.
* Port 23 par kaam karta hai.
  **Example:** Admin remote server ko control karne ke liye TELNET use karta hai.

---

## 🌐 **World Wide Web (WWW)**

* WWW ek system hai jo globally web pages ko access karne ke liye use hota hai.
* Isme websites, web servers, aur web browsers ka use hota hai.
* Ye **HTTP** protocol aur **URLs** pe based hota hai.
* Multimedia content (text, images, video, etc.) share kiya ja sakta hai.
* Internet infrastructure par depend karta hai.
  **Example:** Jab aap [www.wikipedia.org](http://www.wikipedia.org) open karte ho, aap WWW ka hi part use kar rahe ho.

---

## 🔑 **Key Components of WWW**

* **Web Browser:** User interface jo websites ko access karta hai (e.g., Chrome).
* **Web Server:** Jahan website ka data store hota hai (e.g., Apache server).
* **HTTP/HTTPS:** Data transfer ke protocols.
* **URL (Uniform Resource Locator):** Web address jo resource ko identify karta hai.
* **DNS:** Domain name ko IP address me convert karta hai.
  **Example:** Jab aap YouTube browser me kholte ho, browser DNS se IP mangta hai aur server se data fetch karta hai.

---

## 🌐 **DNS (Domain Name System)**

* DNS domain names ko IP addresses me convert karta hai.
* Yeh Internet ki **"phonebook"** ki tarah kaam karta hai.
* Hierarchical aur distributed structure follow karta hai.
* Har domain ke liye authoritative DNS server hota hai.
* Fast access ke liye DNS caching ka use hota hai.
  **Example:** DNS google.com ko IP jaise 142.250.64.78 me convert karta hai.

---

## 🏷️ **Generic Domains**

* Ye globally recognized extensions hote hain (not country-specific).
* Common examples: `.com`, `.org`, `.net`, `.edu`, `.gov`
* Ye domain ka nature define karte hain (commercial, educational, etc.)
* ICANN in domains ko regulate karta hai.
* Subdomains bhi banaye ja sakte hain (e.g., mail.google.com).
  **Example:** [www.amazon.com](http://www.amazon.com) me `.com` ek generic domain hai.

---

## 🌍 **Country Domains (ccTLDs)**

* Specific countries ke liye assigned domain extensions hote hain.
* 2-letter code follow karte hain (ISO standard).
* Examples: `.in` (India), `.us` (USA), `.jp` (Japan), `.uk` (UK)
* Country-specific content serve karne me helpful hote hain.
* Inhe country ki authority manage karti hai.
  **Example:** [www.irctc.co.in](http://www.irctc.co.in) India ka domain extension use karta hai.

---

## 🔁 **Inverse Domains**

* IP addresses se domain names dhoondhne ke liye use hote hain.
* Ye reverse DNS lookup ke liye kaam aate hain.
* Mostly security aur logging purposes ke liye use hota hai.
* Format: IP ko reverse karke `.in-addr.arpa` domain me daala jata hai.
* DNS PTR record ka use karta hai.
  **Example:** 78.64.250.142 ka inverse domain ho sakta hai `142.250.64.78.in-addr.arpa`.

---

## 🔄 **Working of DNS**

* User URL type karta hai → DNS query generate hoti hai.
* Browser DNS resolver ko request bhejta hai.
* Resolver authoritative DNS server se IP address leta hai.
* IP address browser ko milta hai aur page load hota hai.
* Data caching performance ko fast banata hai.
  **Example:** Jab aap [www.facebook.com](http://www.facebook.com) kholte ho, DNS uska IP address dhoondta hai.

---

## 🔁 **Recursive Resolution**

* DNS client ek DNS server se complete answer expect karta hai.
* Agar server ke paas answer nahi hota, to wo aage query forward karta hai.
* Client ko sirf ek server se pura response milta hai.
* Commonly DNS resolvers (like ISP ke) recursion use karte hain.
* User ke liye fast aur simple query process hota hai.
  **Example:** Aapka ISP ka DNS server aapke liye recursion karta hai jab aap koi website open karte ho.

---

## 🔃 **Iterative Resolution**

* Server client ko agla DNS server ka reference deta hai (direct answer nahi deta).
* Client har step pe naye server se manually query karta hai.
* Zyada control deta hai, lekin client pe load badh jata hai.
* Root → TLD → Authoritative servers tak step-by-step jata hai.
* Commonly large networks me use hota hai.
  **Example:** Client khud root DNS ke baad TLD DNS aur fir authoritative DNS tak query bhejta hai.

---

### **1. HTTP (HyperText Transfer Protocol)**

* Web pages ko client (browser) aur server ke beech transfer karta hai.
* Request-response model pe based hota hai.
* Stateless protocol hai, matlab har request alag hoti hai.
* Port 80 use karta hai.
* Mostly websites access karne ke liye use hota hai.
  **Example:** Jab aap [www.google.com](http://www.google.com) kholte ho, HTTP use hota hai.

---

### **2. FTP (File Transfer Protocol)**

* Files ko network ke through upload/download karne ke liye use hota hai.
* Client-server architecture follow karta hai.
* Do channels use karta hai – control aur data.
* Port 21 control ke liye use hota hai.
* Username/password authentication provide karta hai.
  **Example:** Jab aap website me files upload karte ho FTP client ke through.

---

### **3. HTTPS (HTTP Secure)**

* HTTP ka secure version, jisme data encryption hota hai.
* SSL/TLS protocol use karta hai data ko secure karne ke liye.
* Port 443 use karta hai.
* Sensitive information jaise passwords, banking data ke liye use hota hai.
* Man-in-the-middle attacks se bachata hai.
  **Example:** Jab aap online banking website open karte ho, HTTPS use hota hai.

---

### **4. TELNET**

* Remote system ko command line interface se access karne ke liye use hota hai.
* Plain text me data transfer karta hai, isliye secure nahi hai.
* Port 23 use karta hai.
* Mostly legacy systems me use hota hai.
* Aajkal SSH se replace ho raha hai.
  **Example:** Network engineer remote server ko access karne TELNET use karta hai.

---

### **5. SSH (Secure Shell)**

* Remote login ke liye secure protocol hai.
* Data encryption karta hai, isliye secure hota hai.
* Port 22 use karta hai.
* Command-line interface provide karta hai remote systems ke liye.
* TELNET ka secure alternative hai.
  **Example:** Jab aap remotely server me commands run karte ho securely, to SSH use hota hai.

---

## **Network Management Protocols**

### **6. SNMP (Simple Network Management Protocol)**

* Network devices ko monitor aur control karne ke liye use hota hai.
* **Manager:** Network administrator ka tool jo devices ko monitor karta hai.
* **Agent:** Device me installed software jo information provide karta hai.
* **MIB (Management Information Base):** Database jisme network objects ki information stored hoti hai.
* Port 161 aur 162 use karta hai.
  **Example:** Admin SNMP manager se router ke performance ko monitor karta hai.

---

### **7. SMTP (Simple Mail Transfer Protocol)**

* Email bhejne ke liye use hota hai.
* Push model pe based hai.
* Port 25 par kaam karta hai.
* Sirf outgoing mail ke liye use hota hai.
* Email servers ke beech communication me madad karta hai.
  **Example:** Jab aap Gmail se email bhejte ho, SMTP ka use hota hai.

---

### **8. MIME (Multipurpose Internet Mail Extensions)**

* Email me multimedia content (images, audio, video) bhejne ke liye standard hai.
* Email ko text ke alawa bhi format karne me help karta hai.
* Email attachments ko support karta hai.
* SMTP ke sath use hota hai.
* Content-type specify karta hai (e.g., image/jpeg).
  **Example:** Jab aap email me photo attach karte ho, to MIME use hota hai.

---

### **9. POP3 (Post Office Protocol version 3)**

* Email receive karne ke liye client-server protocol hai.
* Emails ko server se download karke local device pe store karta hai.
* Port 110 use karta hai.
* Offline email access possible hota hai.
* Server se email delete kar deta hai download ke baad (by default).
  **Example:** Jab aap Outlook me email download karte ho POP3 use hota hai.

---

### **10. IMAP (Internet Message Access Protocol)**

* Email server par emails ko manage aur access karne ke liye use hota hai.
* Emails ko server pe hi rakhta hai, multiple devices se access possible.
* Port 143 use karta hai.
* Synchronization feature provide karta hai emails ka.
* Real-time email access allow karta hai.
  **Example:** Jab aap Gmail ko multiple devices se sync karte ho, IMAP use hota hai.

---

### **Difference between TFTP and FTP**

| Feature             | TFTP (Trivial FTP)                        | FTP (File Transfer Protocol)                    |
| ------------------- | ----------------------------------------- | ----------------------------------------------- |
| **Complexity**      | Simple protocol, very basic               | Complex with many features                      |
| **Port Number**     | Uses UDP port 69                          | Uses TCP port 21                                |
| **Connection Type** | Connectionless (UDP)                      | Connection-oriented (TCP)                       |
| **Authentication**  | No authentication required                | Username and password required                  |
| **Data Transfer**   | Mainly small files, no directory access   | Supports large files, directory navigation      |
| **Reliability**     | Less reliable, no error recovery          | Reliable with error checking and recovery       |
| **Use Case**        | Simple, fast transfers (e.g., boot files) | General file transfer, more secure and flexible |

**Example:** TFTP is used to transfer configuration files to routers, while FTP is used to upload/download files on websites.

---

### **Data Compression Types**

* **Lossless Compression**
  Data compress hone ke baad original data bina kisi loss ke wapas milta hai.
  Use hota hai jab data accuracy zaruri ho (jaise text, code).
  Example: ZIP files, PNG images.

* **Lossy Compression**
  Data compress hone ke baad kuch information permanently lost ho jati hai.
  Use hota hai jab thoda quality loss acceptable ho (jaise images, audio).
  Example: JPEG images, MP3 audio.

---

### **Cryptography Types**

* **Symmetrical Cryptography**
  Same key encryption aur decryption ke liye use hota hai.
  Fast hota hai lekin key sharing problem hoti hai.
  Example: AES, DES algorithms.

* **Asymmetrical Cryptography**
  Do alag keys use karta hai – public key encryption ke liye, private key decryption ke liye.
  Secure key exchange possible hota hai.
  Example: RSA algorithm.

* **Digital Signature**
  Message ke authenticity aur integrity ko verify karta hai.
  Sender apni private key se signature create karta hai, receiver public key se verify karta hai.
  Ensure karta hai ki message tampered nahi hua hai.

---

### **RSA Algorithm – Steps**

1. **Key Generation:**

   * Do prime numbers (p, q) choose karo.
   * N = p × q calculate karo.
   * Euler’s totient function φ(n) = (p-1)(q-1) calculate karo.

2. **Public Key:**

   * Choose e such that 1 < e < φ(n) and gcd(e, φ(n)) = 1 (e and φ(n) coprime).
   * Public key = (e, N).

3. **Private Key:**

   * Calculate d such that (d × e) mod φ(n) = 1.
   * Private key = (d, N).

4. **Encryption:**

   * Plaintext message M ko cipher C me convert karo:
     C = M^e mod N.

5. **Decryption:**

   * Cipher C ko original message M me convert karo:
     M = C^d mod N.

---

