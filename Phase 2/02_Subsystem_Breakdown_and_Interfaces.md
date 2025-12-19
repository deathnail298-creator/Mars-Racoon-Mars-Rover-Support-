# Phase 2 — Subsystem Breakdown & Interfaces (Theory-Only)

> **License Note**  
> Governed by **TEL-1.0 — Theory Exploration License**.  
> This document is conceptual only.  
> Nothing here authorizes fabrication, testing, prototyping, simulation, manufacturing, or operational use.  
> Any execution requires a paid **Phase 3 Execution License**.

---

## 1. Purpose of This Document

This document defines Mars Raccoon at the **subsystem level**, focusing on:

- what each subsystem does  
- what boundaries it owns  
- what it must not depend on  
- how subsystems interact conceptually  
- what interfaces must exist between them  

This prevents uncontrolled growth, unrealistic dependence chains, and architectural drift.

This document is about **discipline, not engineering indulgence**.

---

## 2. Subsystem List

Mars Raccoon consists of the following conceptual subsystems:

1️⃣ Chassis & Structure  
2️⃣ Mobility System  
3️⃣ Retrieval System  
4️⃣ Storage Vault System  
5️⃣ Power System  
6️⃣ Thermal Management System  
7️⃣ Avionics & Control  
8️⃣ Communications & Integration Interfaces

Each subsystem below is defined cleanly with:

- Role
- Boundaries
- Critical Requirements
- Interface Expectations
- Non-Negotiable Constraints

---

## 3️⃣ Subsystem Definitions

---

## 3.1 Chassis & Structure

### **Role**
Mechanical backbone of the system.  
Protects vault. Supports loads. Survives Mars.

---

### **Subsystem Boundary**
Chassis owns:

- primary structural frame
- impact / vibration load paths
- vault protective housing
- integration mount points for:
  - mobility
  - retrieval
  - solar / antennas
- lifting / handling interfaces

---

### **Critical Requirements**
- Must maintain vault structural protection even under partial failure
- Must avoid transmitting shock directly through stored tubes
- Must support low center-of-gravity configuration
- Must enable stable stance geometry
- Must allow downstream retrieval asset access

---

### **Interfaces**
- Mechanical interface → **Mobility**
- Mechanical interface → **Retrieval**
- Protective enclosure & structural coupling → **Vault**
- Physical mounting & stowage points → **Power & Comms**
- Load-bypass structural paths around vault

---

### **Non-Negotiable Constraints**
- Vault protection dominates chassis decisions
- Structural complexity must remain reasonable
- Must tolerate partial deformation without catastrophic vault compromise

---

## 3.2 Mobility System

### **Role**
Move Mars Raccoon within a limited local operations region.  
Movement is supportive, not heroic.

---

### **Subsystem Boundary**
Mobility subsystem owns:

- locomotion hardware (tracks/wheels/bogies)
- suspension and compliance behavior
- traction capability
- mechanical stability envelope
- drive actuation & gearing

---

### **Critical Requirements**
- Conservative, stable traversal
- Prefer traction margin over efficiency
- Motion → rare, deliberate, slow
- Supports “stuck but stable” fail outcome
- Prevents high-tip-risk behavior

---

### **Interfaces**
- Structural mounting → **Chassis**
- Power input → **Power System**
- Commanding → **Avionics**
- Health state feedback → **Comms**

---

### **Non-Negotiable Constraints**
- Shall not depend on high refresh autonomy
- Shall not assume rover-like capability
- Movement failure must not endanger vault
- If mobility dies, system must still retain mission value

---

## 3.3 Retrieval System

### **Role**
Transfer tubes from surface to the vault intake **safely**, with high misalignment tolerance and strong dust robustness.

---

### **Subsystem Boundary**
Retrieval owns:

- intake geometry (funnel/scoop style)
- physical capture mechanics
- compliant contact elements
- force-limiting extraction system
- tube transition mechanism into vault intake

---

### **Critical Requirements**
- Passive geometry does most of the precision work
- Minimal axis-count, minimal finesse required
- Abort is always safer than forcing
- Must explicitly handle:
  - dust
  - imperfect alignment
  - shallow burial
- Must respect “walk away” constraints

---

### **Interfaces**
- Mechanical mounting → **Chassis**
- Intake path → **Vault Interface Structure**
- Motion actuation & sensing → **Power**
- Control strategy enforcement → **Avionics**
- State/inventory impact → **Comms**

---

### **Non-Negotiable Constraints**
- No primary dependence on precision robotics
- May fail to retrieve but must not damage tubes
- Must support graceful abort states
- Must never escalate risk simply to “succeed”

---

## 3.4 Storage Vault System

### **Role**
Protect tubes.
Retain tubes.
Remain safe even if everything else fails.

---

### **Subsystem Boundary**
Vault owns:

- internal retention geometry
- tube shock isolation structures
- internal organization (slots/trays/cradles)
- vault door / intake gate
- dust and intrusion barrier at entry interface

---

### **Critical Requirements**
- Retention does not depend on power
- Vault remains secure if avionics die
- Vault remains secure if power dies
- Vault remains secure if mobility fails
- Vault remains secure if robot falls silent

Vault must remain **boringly reliable**.

---

### **Interfaces**
- Structural hard coupling → **Chassis**
- Intake handoff → **Retrieval System**
- Thermal buffering → **Thermal System**
- Inventory state reporting → **Avionics → Comms**

---

### **Non-Negotiable Constraints**
- Vault integrity takes precedence over:
  - mobility optimization  
  - retrieval aggressiveness  
  - power convenience  
- Failure must bias toward retention, not loss

---

## 3.5 Power System

### **Role**
Provide scarce, precious power over long mission timescales.
Support idle-first, burst-rare mission profile.

---

### **Subsystem Boundary**
Power subsystem owns:

- solar collection (conceptual baseline)
- energy storage
- power distribution logic
- safe power-down & recovery behavior

---

### **Critical Requirements**
- Extremely low idle draw
- Must support long dormancy
- Recharge must support patience, not urgency
- Power failure must NOT compromise vault

---

### **Interfaces**
- Electrical supply → all active subsystems
- Power budgeting logic → **Avionics**
- Thermal link influences → **Thermal System**
- Health reporting → **Comms**

---

### **Non-Negotiable Constraints**
- Vault safety shall not depend on powered retention
- Power starvation must degrade safely
- RTG attractive but not baseline assumed
