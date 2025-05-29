# **Comprehensive Guide to Software Design Principles and Metrics**

## **1. Introduction to Software Design**

### **1.1 Definition and Importance**
Software design is the **engineering blueprint** phase that transforms requirements into a detailed specification for construction. It serves as the critical bridge between:
- **What** the system should do (requirements)
- **How** the system will do it (implementation)

**Key Characteristics of Good Design:**
- **Correctness:** Faithfully implements all requirements
- **Efficiency:** Optimizes resource usage (CPU, memory, I/O)
- **Maintainability:** Ease of modification (avg. 70% of software cost is maintenance)
- **Scalability:** Handles growth in users/data volume
- **Reusability:** Components usable across projects

### **1.2 Fundamental Design Concepts**
- **Abstraction:** Hiding complex details (e.g., using functions/classes)
- **Decomposition:** Breaking problems into manageable parts
- **Encapsulation:** Bundling data with methods that operate on it
- **Separation of Concerns:** Isolating different functionalities

## **2. Architectural Design**
### 🏗️ 2.1 Purpose and Objectives — *City Planning*

* **Components** = City ke parts (ghar, school, hospital)
* **Interactions** = Roads, bridges (kaise connect honge)
* **Quality** = City smooth chale (traffic = performance, police = security)

---

### 🏛️ 2.2 Common Architectural Patterns — *City ke Layout Designs*

#### **1. Layered Architecture = G+3 Building**

* Ground floor: **Data access (basement storage)**
* 1st floor: **Business logic (offices)**
* 2nd floor: **UI (reception)**
* Rule: Neeche waala bina upar waale se directly baat nahi karega.

#### **2. Microservices = Colony of Independent Houses**

* Har house = ek service (e.g., ek hospital, ek school)
* Alag power meter, water tank = **Independent deploy**
* Communicate karte hain phone se = **REST APIs**

#### **3. Event-Driven = City’s Emergency Alarm System**

* Fire = **Event trigger**
* Fire station = **Consumer**
* Alarm system = **Message broker**
* Har department ka apna kaam, bas signal milte hi activate ho jaate hain.

---

### 📘 2.3 Architectural Documentation — *City Map from Different Angles (4+1 Views)*

1. **Logical View** = City ka layout (ghar, road diagram)
2. **Process View** = Kaun kya kaam karega, kis speed se (concurrency)
3. **Development View** = Kis builder ne kya banaya (modules)
4. **Physical View** = Real location pe kaise deploy kiya (Google Maps view)
5. **Scenarios** = Real-life usage (agar fire lagi to kya process chalega)

---



## **3. Low-Level (Detailed) Design**

### **3.1 Modularization Principles**
**Effective Module Characteristics:**
- **High Cohesion:** Single, well-defined purpose
- **Low Coupling:** Minimal dependencies
- **Information Hiding:** Internal details hidden

**Module Size Guidelines:**
- 50-200 lines of code
- Fits in developer's working memory

### **3.2 Design Representation Techniques**

#### **Structure Charts**
- **Elements:**
  - Modules (rectangles)
  - Calls (arrows with parameters)
  - Data couples (dotted arrows)
- **Example:**
  ```
  [Order Processing]
   ↓           ↓
[Payment]   [Inventory]
   ↓           ↓
[DB Access] [Warehouse API]

#### **Pseudocode Standards**
- **Best Practices:**
  - Language-independent
  - Structured (IF-THEN-ELSE, WHILE-DO)
  - Detailed but not implementation-specific
- **Example (Search Algorithm):**
  ```plaintext
  PROCEDURE BinarySearch(list, target)
      low ← 1
      high ← length(list)
      WHILE low ≤ high DO
          mid ← (low + high) DIV 2
          IF list[mid] = target THEN
              RETURN mid
          ELSE IF list[mid] < target THEN
              low ← mid + 1
          ELSE
              high ← mid - 1
          ENDIF
      ENDWHILE
      RETURN -1
  END PROCEDURE
  ```

#### **Flowchart Design**
- **Advanced Symbols:**
  - Predefined process (rectangle with double lines)
  - Document (rectangle with wavy base)
  - Database (cylinder)
- **Optimization Techniques:**
  - Avoid spaghetti diagrams
  - Limit to 10-15 symbols per chart
  - Use swimlanes for parallel processes

### **3.3 Coupling and Cohesion Metrics**

#### **Coupling Types (Ordered from Best to Worst)**
1. **Data Coupling:** Through parameters only
2. **Stamp Coupling:** Passing composite objects
3. **Control Coupling:** Passing control flags
4. **Common Coupling:** Global variables
5. **Content Coupling:** Direct modification of internals

#### **Cohesion Levels (Ordered from Best to Worst)**
1. **Functional:** Single well-defined task
2. **Sequential:** Output from one part is input to next
3. **Communicational:** Operations on same data
4. **Procedural:** Ordered execution steps
5. **Temporal:** Operations executed together in time

**Quantitative Measures:**
- **Coupling Between Objects (CBO):** Count of classes a class is coupled to
- **Lack of Cohesion in Methods (LCOM):** Measures method similarity

## **4. Design Strategies**

### **4.1 Function-Oriented Design**
- **Characteristics:**
  - Top-down decomposition
  - Emphasis on functional decomposition
  - Data structures secondary
- **Example (C Program Structure):**
  ```c
  void main() {
      input();
      process();
      output();
  }
  ```

### **4.2 Object-Oriented Design**
- **SOLID Principles:**
  1. **Single Responsibility:** One reason to change
  2. **Open/Closed:** Open for extension, closed for modification
  3. **Liskov Substitution:** Subtypes behave as supertypes
  4. **Interface Segregation:** Client-specific interfaces
  5. **Dependency Inversion:** Depend on abstractions
- **Design Patterns:**
  - Creational (Factory, Singleton)
  - Structural (Adapter, Composite)
  - Behavioral (Observer, Strategy)



---

### 🍽️ SOLID Principles = Ek Acche Restaurant ke 5 Rules

---

### 1. **Single Responsibility** – *Har banda sirf ek kaam kare*

👨‍🍳 Chef sirf cooking karega, waiter sirf serving.
➡️ Ek reason se hi kaam badlega. Chef ko serving nahi aani chahiye.

---

### 2. **Open/Closed** – *Menu update ho sakta hai, purani dishes ko chhede bina*

➡️ Nayi dishes add karo, lekin existing dishes ka recipe mat todho.

---

### 3. **Liskov Substitution** – *Chef ka assistant bhi cooking sambhal le bina gadbad kiye*

➡️ Subclass (assistant) ko bhi parent (chef) ki tarah kaam aana chahiye.

---

### 4. **Interface Segregation** – *Waiter ko cooking tools ka interface mat do*

➡️ Har role ko sirf apne kaam ka button do. Jyada options confuse karenge.

---

### 5. **Dependency Inversion** – *Chef ko fridge ka brand nahi chahiye, bas abstract “cold storage” chahiye*

➡️ High-level modules ko low-level pe depend nahi karna chahiye, dono abstraction pe depend karein.

---


### **4.3 Top-Down vs Bottom-Up**

**Comparison Table:**
| **Characteristic**   | **Top-Down**                  | **Bottom-Up**                |
|----------------------|-------------------------------|------------------------------|
| **Approach**         | Starts with system level      | Starts with components       |
| **Advantages**       | Early architecture validation | Reusable components          |
| **Disadvantages**    | Potential redesign of modules | Late system integration      |
| **Best For**         | New systems                   | Component libraries          |

## **5. Software Measurement and Metrics**

### **5.1 Halstead's Software Science**

**Complete Metric Suite:**
1. **Program Vocabulary:** n = n1 + n2
2. **Program Length:** N = N1 + N2
3. **Volume:** V = N × log₂n
4. **Difficulty:** D = (n1/2) × (N2/n2)
5. **Effort:** E = D × V
6. **Time:** T = E/18 seconds

**Example Calculation:**
For code with:
- 50 unique operators (n1)
- 30 unique operands (n2)
- 400 total operators (N1)
- 200 total operands (N2)

Volume V = (400+200) × log₂(50+30) ≈ 600 × 6.32 ≈ 3792

### **5.2 Function Point Analysis**

**Detailed Calculation Process:**

1. **Count Measurement Parameters:**
   - External Inputs (EI)
   - External Outputs (EO)
   - External Inquiries (EQ)
   - Internal Logical Files (ILF)
   - External Interface Files (EIF)

2. **Determine Complexity Weights:**
   | **Type** | **Low** | **Avg** | **High** |
   |----------|--------|--------|--------|
   | EI       | 3      | 4      | 6      |
   | EO       | 4      | 5      | 7      |

3. **Calculate Unadjusted FP:**
   ```
   UFP = Σ(Count × Weight)
   ```

4. **Determine Value Adjustment Factor (VAF):**
   - Rate 14 general system characteristics (0-5 scale)
   - VAF = 0.65 + (0.01 × ΣScores)

5. **Final FP Count:**
   ```
   FP = UFP × VAF
   ```

### **5.3 Cyclomatic Complexity**

**Advanced Applications:**
- **Basis Path Testing:** Generates V(G) test cases
- **Risk Assessment:**
  - V(G) > 50: High defect probability
  - V(G) > 100: Consider redesign

**Alternative Calculation Methods:**
1. **Graph Formula:** V(G) = e - n + 2p
2. **Decision Points:** V(G) = P + 1 (P = predicate nodes)
3. **Code Inspection:** Count control structures + 1

**Example (Java Method):**
```java
public String evaluate(int score) {
    if (score > 90) return "A";      // 1
    else if (score > 80) return "B"; // 2
    else if (score > 70) return "C"; // 3
    else return "F";                 // 4
}
```
V(G) = Number of decisions (3) + 1 = 4

## **6. Practical Applications**

### **6.1 Design Quality Assessment**
- **Maintainability Index:**
  ```
  MI = 171 - 5.2×ln(V) - 0.23×V(G) - 16.2×ln(LOC)
  ```
  Where:
  - V = Halstead Volume
  - V(G) = Cyclomatic Complexity
  - LOC = Lines of Code

### **6.2 Industry Benchmarks**
| **Metric**           | **Excellent** | **Acceptable** | **Poor** |
|----------------------|--------------|---------------|---------|
| Cyclomatic Complexity | 1-10         | 11-20         | >20     |
| Function Points/PM   | >20          | 10-20         | <10     |
| CBO                 | <5           | 5-10          | >10     |

## **7. Tools for Design and Metrics**

### **7.1 Design Tools**
- **UML Modeling:** Enterprise Architect, Visual Paradigm
- **Flowcharting:** Lucidchart, Draw.io
- **Pseudocode Editors:** Pseudogen, Code2Flow

### **7.2 Metrics Tools**
- **Complexity Analysis:** SonarQube, NDepend
- **Function Points:** COSMIC FP, IFPUG Certified Tools
- **Halstead Metrics:** Understand, SourceMonitor

This comprehensive approach to software design ensures systems are:
✔ Architecturally sound  
✔ Implemented efficiently  
✔ Maintainable long-term  
✔ Measurable for quality  
