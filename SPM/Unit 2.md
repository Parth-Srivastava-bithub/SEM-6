### **1.1 What is a WBS?**

A **Work Breakdown Structure (WBS)** splits a big project into smaller parts: functions → activities → tasks.
Helps assign responsibility, estimate time, and track progress.
Visual and clear — perfect for team coordination.

📦 Example:
**E-commerce site** → Frontend (UI + React), Backend (DB + API).

---

### **1.2 Types of WBS**

| **Type**              | **Description**                       | **Best For**                    |
| --------------------- | ------------------------------------- | ------------------------------- |
| **Deliverable-Based** | Breaks work by outputs (UI, API, DB). | Waterfall, Agile projects.      |
| **Phase-Based**       | Follows project phases (Design, Dev). | Traditional project lifecycles. |

👉 Choose based on what’s easier to manage — output or timeline.

---

### **1.3 Functions, Activities, Tasks**

| **Level** | **Meaning**               | **Example**                       |
| --------- | ------------------------- | --------------------------------- |
| Function  | Big area of work          | "Backend Development"             |
| Activity  | Logical group of tasks    | "API for User Login"              |
| Task      | Actionable, smallest unit | "Write JWT Token Validation Code" |

⚙️ It’s like zooming in — function → activity → task. Helps organize team work better!


---

### **2. Project Organization & WBS**

#### **2.1 How to Create an Effective WBS**

1. 🎯 **Identify major deliverables** – Big chunks like Frontend, Backend.
2. 🔍 **Break down into subtasks** – Smaller and actionable (e.g., "Design Login Page").
3. 👥 **Assign ownership** – Who's responsible for each task.
4. ✅ **Validate with stakeholders** – Make sure everyone agrees and it's feasible.

---

#### **2.2 WBS Examples**

**E-Commerce Site**

```
1.0 Website Dev  
├── 1.1 Frontend  
│   ├── 1.1.1 UI Design  
│   └── 1.1.2 React Code  
└── 1.2 Backend  
    ├── 1.2.1 DB Setup  
    └── 1.2.2 API Dev  
```

**Mobile App**

```
1.0 App Dev  
├── 1.1 iOS  
│   ├── 1.1.1 SwiftUI  
│   └── 1.1.2 App Store  
└── 1.2 Android  
    ├── 1.2.1 Kotlin  
    └── 1.2.2 Play Store  
```

---

#### **2.3 Common Mistakes to Avoid**

⚠️ Too Generic – “Do frontend” isn’t clear. Be specific.

⚠️ Missing Sequence – E.g., no DB → APIs fail.

⚠️ Uneven Layers – Some tasks go too deep, others too shallow.

---

### **3. Project Scheduling Techniques**

---

#### **3.1 Critical Path Method (CPM)**

| Activity | Predecessor | Duration (days) |
| -------- | ----------- | --------------- |
| A        | -           | 3               |
| B        | A           | 4               |
| C        | B           | 2               |
| D        | A           | 5               |
| E        | C, D        | 1               |

🧠 **Explanation:**

* Identify all tasks and their dependencies.
* Calculate duration and draw paths.
* **Critical Path = longest path** without delay margin (here A → D → E = 9 days).
* Any delay on this path delays the whole project.

---

#### **3.2 Gantt Chart vs PERT**

| Feature       | Gantt Chart                | PERT                                     |
| ------------- | -------------------------- | ---------------------------------------- |
| Visualization | Bar chart showing timeline | Network diagram (flowchart style)        |
| Best For      | Simple, linear projects    | Complex projects with dependencies/risks |
| Flexibility   | Hard to change once fixed  | Easier to update based on uncertainty    |

🧠 **Explanation:**

* **Gantt** is great for showing what’s happening *when*. Think of it like a calendar bar view.
* **PERT** focuses on dependencies and risk — more like a map of how things connect.
* Use Gantt for **clarity**, PERT for **accuracy under uncertainty**.

---

#### **3.3 Agile Scheduling**

| Agile Element   | Purpose                                |
| --------------- | -------------------------------------- |
| Sprint Planning | Define goals for next 1–2 weeks        |
| Daily Standups  | Quick status check & blockers          |
| Sprint Review   | Show completed work to stakeholders    |
| Retrospective   | Discuss what to improve in next sprint |
| Tools           | Jira, Trello, Azure DevOps             |

🧠 **Explanation:**

* Agile breaks big work into **short, time-boxed sprints**.
* You review progress daily, fix problems fast, and **adapt continuously**.
* Lightweight, flexible, and **customer-focused** — perfect for changing needs.

---

### 4. Earned Value Management (EVM)

| Metric | Formula                  | Interpretation                                       |
| ------ | ------------------------ | ---------------------------------------------------- |
| PV     | Planned % complete × BAC | What we *planned* to spend so far                    |
| EV     | Actual % complete × BAC  | Value of work *actually done*                        |
| AC     | Actual costs incurred    | What we have *actually spent*                        |
| SPI    | EV / PV                  | Schedule performance index — over or behind schedule |
| CPI    | EV / AC                  | Cost performance index — under or over budget        |

**Explanation:**
EVM lets you track if your project is on track **schedule-wise (SPI)** and **budget-wise (CPI)**.
SPI < 1 means you’re behind schedule, CPI < 1 means over budget. It combines scope, time, and cost in one system — gold for project control.

---

### 4.2 EVM Example

| Parameter | Value     | Explanation                        |
| --------- | --------- | ---------------------------------- |
| BAC       | \$100,000 | Total project budget               |
| PV        | \$60,000  | Planned value (should be 60% done) |
| EV        | \$50,000  | Earned value (actually 50% done)   |
| AC        | \$55,000  | Actual cost spent                  |
| SPI       | 0.83      | Behind schedule (50k/60k)          |
| CPI       | 0.91      | Over budget (50k/55k)              |

---

### 5. Software Quality Assurance (SQA)

| Type             | Formality  | Preparation | Participants       | Best For                   |
| ---------------- | ---------- | ----------- | ------------------ | -------------------------- |
| Inspection       | High       | Extensive   | Trained moderators | Critical systems           |
| Walkthrough      | Medium     | Some        | Author + peers     | Early design review        |
| Code Review      | High       | Some        | Developers         | Implementation phase       |
| Pair Programming | Continuous | None        | Two developers     | Agile teams, fast feedback |

**Explanation:**
SQA ensures software quality through structured checks at different stages.
Inspections are super formal and deep, perfect for safety-critical software.
Walkthroughs are casual reviews during early design. Code reviews catch bugs during coding, and pair programming delivers instant feedback during development.

---

### 5.2 Defect Tracking Process

| Step           | Description                      | Tools                         |
| -------------- | -------------------------------- | ----------------------------- |
| Identification | Detect the bug or issue          | Jira, Bugzilla, GitHub Issues |
| Classification | Set priority: High/Medium/Low    |                               |
| Assignment     | Assign responsible developer     |                               |
| Resolution     | Fix and verify the bug           |                               |
| Closure        | Document fix and close the issue |                               |

**Explanation:**
A bug’s journey from discovery to resolution follows these steps to keep everything clear and tracked.
Defect tracking tools help teams communicate and prioritize bugs effectively, preventing chaos in large projects.

---

### 6. Risk Management

| Technique          | Description                                                   |
| ------------------ | ------------------------------------------------------------- |
| Brainstorming      | Team discusses all possible risks.                            |
| Checklist Analysis | Uses known risk lists to spot issues.                         |
| SWOT Analysis      | Identifies strengths, weaknesses, threats, and opportunities. |
| Expert Judgment    | Experienced pros assess risks.                                |

**Explanation:**
You find risks early by brainstorming, checklists, SWOT, or experts to avoid nasty surprises later.

---

### Risk Response Strategies

| Strategy | When to Use        | Example                   |
| -------- | ------------------ | ------------------------- |
| Avoid    | High impact risk   | Change project scope      |
| Transfer | Can be insured     | Buy insurance or warranty |
| Mitigate | Reduce risk chance | Add extra code reviews    |
| Accept   | Low impact risk    | Minor UI bugs             |

**Explanation:**
Depending on risk severity, you either avoid, shift, reduce, or just accept it — no point sweating minor stuff.

---

### 7. Agile Project Management

| Agile Method | Key Features                                                                                        |
| ------------ | --------------------------------------------------------------------------------------------------- |
| Scrum        | Roles: Product Owner, Scrum Master, Team. Artifacts: Backlogs. Ceremonies: Daily standups, reviews. |
| Kanban       | Visual boards with To Do → Done columns. Limits on work in progress. Focus on smooth flow.          |

**Explanation:**
Scrum breaks work into sprints with roles and meetings to keep things tight; Kanban visualizes tasks and limits overload for steady delivery.

---

**Scrum Framework:**
You got your Product Owner who decides what’s needed, Scrum Master who keeps the team on track, and the Team who builds stuff. They work off Product Backlog (all features wanted) and Sprint Backlog (what’s being done now). Ceremonies like Daily Standup keep everyone synced, and Sprint Review checks progress.

**Kanban Method:**
It’s like a visual to-do list with columns: To Do, In Progress, Done. Limits on how many tasks are “In Progress” keep the team focused and avoid overload. Kanban is about smooth, continuous delivery without fixed sprints.


---

### 8.1 Popular Project Management Tools

| Tool       | Best For        | Key Feature        |
| ---------- | --------------- | ------------------ |
| Jira       | Agile teams     | Custom workflows   |
| Trello     | Simple projects | Kanban boards      |
| MS Project | Traditional PM  | Gantt charts       |
| Asana      | Task management | Team collaboration |

**Explanation:**
Jira rules for Agile with powerful workflow customizations, Trello is casual and visual with Kanban, MS Project is classic for detailed scheduling using Gantt charts, and Asana shines for smooth task tracking and team chats.

---

### 9. Case Studies

| Case Study            | Key Points                                                          |
| --------------------- | ------------------------------------------------------------------- |
| Spotify Agile Model   | Squads & Tribes for autonomy, continuous deployment, feature teams  |
| Healthcare.gov Launch | Failed due to poor requirements, missing integration & load testing |

**Explanation:**
Spotify nailed Agile by splitting teams into small, independent squads for fast delivery and constant updates. Healthcare.gov flopped hard due to sloppy planning, no thorough integration, and ignoring real-world traffic testing — a classic disaster.

---

### 10.1 Key Formulas to Remember

| Formula                   | Description                                  |
| ------------------------- | -------------------------------------------- |
| **EV = % complete × BAC** | Earned Value (work done value)               |
| **SV = EV - PV**          | Schedule Variance (ahead or behind schedule) |
| **CV = EV - AC**          | Cost Variance (under or over budget)         |

**Explanation:**
Earned Value tells you how much work you’ve actually done against your budget. Schedule Variance shows if you’re early or late, and Cost Variance reveals if you’re spending more or less than planned.

---

### 10.2 Common Exam Questions

| Question                                    | Focus Area               |
| ------------------------------------------- | ------------------------ |
| Difference between PERT and CPM?            | Scheduling techniques    |
| How to calculate SPI and CPI?               | Earned Value Management  |
| What are the four risk response strategies? | Risk Management          |
| Compare Gantt charts and network diagrams.  | Project scheduling tools |

---

### 10.3 Study Tips

* Practice building Work Breakdown Structures (WBS) for various projects to master project decomposition.
* Drill EVM formulas and calculation examples until they’re second nature.
* Clearly understand Agile vs. Waterfall — their phases, pros/cons, and when to use each.

---



