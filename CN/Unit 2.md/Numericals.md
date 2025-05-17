## 🧠 **1. Simple Parity Check (Even Parity)**

> 🧒 “We want the number of 1s to be even. If it’s not, we add 1 to make it even.”

### ✅ Example:

**Data** = `1010001`
Count of 1s = 3 → Odd
➡ Add **1** as parity bit ➡ `10100011`
Now: Total 1s = 4 → Even ✅

📍At receiver side:
If number of 1s is not even → ❌ Error

---

## 🧠 **2. Two-Dimensional Parity Check**

> 🧒 “Like checking both rows and columns in tic-tac-toe to find where the cheating happened!”

### ✅ Example:

**Original Data (3x3)**

```
Row1: 1 0 1  
Row2: 0 1 1  
Row3: 1 1 0  
```

👉 Add **Row Parity**:

```
Row1: 1 0 1 → 2 ones → Even → Add 0  
Row2: 0 1 1 → 2 ones → Add 0  
Row3: 1 1 0 → 2 ones → Add 0  
```

👉 Add **Column Parity**:
Count 1s in each column (top-down):

```
Col1: 1+0+1 = 2 → Add 0  
Col2: 0+1+1 = 2 → Add 0  
Col3: 1+1+0 = 2 → Add 0  
```

➡ Final with parity:

```
1 0 1 | 0  
0 1 1 | 0  
1 1 0 | 0  
--------  
0 0 0
```

🔍 Error occurs? Check which row & column parity fails = pinpoint exact error bit.

---

## 🧠 **3. Checksum**

> 🧒 “Add all your gifts, then send their total to your friend. They’ll re-add and check if it matches.”

### ✅ Example (8-bit blocks):

```
Block 1: 01100110 (102)  
Block 2: 01101100 (108)  
Block 3: 01010101 (85)
```

Sum:

```
Step 1: 01100110 + 01101100 = 11010010  
Step 2: 11010010 + 01010101 = 00100111 (carry wrapped around)
```

Now, take 1’s complement (flip bits):

```
00100111 → 11011000 = ✅ Checksum
```

🔁 Send data + checksum = receiver re-adds all
→ If result = all 1s → ✅ No error
→ Else ❌

---

## 🧠 **4. CRC (Cyclic Redundancy Check)**

> 🧒 “Divide big number by another number and send the remainder. Receiver divides and checks if remainder is same!”

### ✅ Example:

**Data**: `1101`
**Divisor (Generator Polynomial)**: `1011`
➡ Append 3 zeros to data: `1101000` (because divisor is 4-bits)

Use binary division (like long division but with XOR):

```
1101 ÷ 1011 =  
→ First XOR: 1101 XOR 1011 = 0110  
→ Bring down next bit, repeat...

Final Remainder (CRC): `100`

➡ Send: `1101 + 100` = `1101100`

Receiver divides `1101100` by `1011`  
→ If remainder = `0` → ✅ All good  
→ Else ❌ Error

---
