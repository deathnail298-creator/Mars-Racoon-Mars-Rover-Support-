# Phase 2 — System Architecture (Theory-Only)

> **License Note:**  
> This document is governed by **TEL-1.0 — Theory Exploration License**.  
> It is **conceptual only**. Nothing here authorizes execution, fabrication, testing, or deployment.  
> Any real-world execution requires a separate paid **Execution License (Phase 3)**.

---

## 1. Purpose and Scope

This document defines the **theoretical system architecture** for Mars Raccoon:

- how the system is structured at a high level  
- what major subsystems exist  
- how they relate to one another  
- what design principles constrain them  

This is **not** a build plan.  
It is a **structured concept description** designed to:

- guide future engineering if execution is licensed  
- support risk analysis  
- prevent architecture drift  
- keep the system aligned with Phase 0 & Phase 1 doctrine

---

## 2. Role Recap (Architecture Driver)

Mars Raccoon performs one mission:

> **Retrieve tubes, protect tubes, and wait.**

Architecturally, that means:

- it is a **logistics asset**, not a science rover  
- it consolidates tubes from a local cache region into a protected vault  
- it becomes a stationary “sample depot” if mobility is lost  
- it interfaces with future retrieval assets (helicopter / rover / lander / ascent system)

The architecture must support that role without drifting into:

- science payload bus  
- demo autonomy platform  
- multi-role exploration robot  

---

## 3. Top-Level System View

At the highest level, Mars Raccoon can be represented as **eight cooperating subsystems**:

1. **Chassis & Structure**  
2. **Mobility System**  
3. **Retrieval System**  
4. **Storage Vault System**  
5. **Power System**  
6. **Thermal Management System**  
7. **Avionics & Control System**  
8. **Communications & Integration Interfaces**

Conceptually:

- **Chassis** provides mechanical backbone and mounting  
- **Mobility** moves the box in a constrained zone  
- **Retrieval** brings tubes from ground to vault intake  
- **Vault** stores and protects tubes  
- **Power** keeps everything alive on a slow, austere duty cycle  
- **Thermal** maintains survivable regime for hardware and stored tubes  
- **Avionics & Control** implement the “slow, supervised, deterministic” behavior  
- **Comms & Integration** connect Mars Raccoon to MSR operations and downstream assets

---

## 4. High-Level Architecture Diagram (Conceptual)

Text-mode conceptual diagram (notional, non-geometric):

- **Mobility System** and **Retrieval System** mounted to  
- **Chassis & Structure**, which surrounds the  
- **Storage Vault**, which is thermally coupled to the  
- **Thermal Management System**, all powered by the  
- **Power System**, coordinated by  
- **Avionics & Control**, and communicating through  
- **Comms & Integration Interfaces**.

Dependencies:

- Retrieval depends on Mobility (to reach tubes) and Vault (to store them)  
- Vault depends on Chassis (protection) and Thermal (environment)  
- Mobility, Retrieval, Vault all depend on Power and Control  
- Comms depends on Power and Avionics  
- The mission value depends primarily on **Vault + Retrieval**, with Mobility as a facilitator

Architecture rule:

> If Mobility fails, Vault must still be functional and protective.  
> If Avionics fail, Vault must still be protective.

---

## 5. Operational Modes (System-Level Behavior)

The architecture must support at least these high-level modes:

1. **Idle / Guard Mode**  
   - Low-power state  
   - Minimal telemetry  
   - Vault closed and protective  
   - No motion unless commanded

2. **Transit Mode (Local Movement)**  
   - Slow, controlled movement within cache region  
   - Navigation under supervisory control  
   - Mobility prioritized for stability over speed

3. **Retrieval Mode**  
   - Retrieval system active  
   - Small geometric maneuvers to align intake  
   - Tube handoff into vault intake path  
   - High monitoring of force and misalignment

4. **Consolidation / Reposition Mode**  
   - Optional movement after partial loading  
   - Used to reposition into a more accessible spot for downstream retrieval

5. **Safe-Hold / Degraded Mode**  
   - Triggered by anomalies (mobility, power, comms, retrieval issues)  
   - System ceases non-essential actions  
   - Prioritizes vault integrity and predictable posture

6. **End-State Depot Mode**  
   - Mobility and retrieval no longer used  
   - Raccoon functions purely as a stable sample depot  
   - Vault remains the only critical subsystem

System architecture must ensure the above modes can exist without architectural contradictions.

---

## 6. Subsystem Overview (Theory)

### 6.1 Chassis & Structure

**Role:**
- Provide mechanical backbone  
- Protect vault  
- Support mobility and retrieval loads  
- Survive shocks and long-term degradation

**Key architectural properties:**
- Low center of gravity  
- Stiff paths around vault, not through it  
- Designed to tolerate partial damage while preserving vault volume  
- Interfaces for lifting / handling by downstream retrieval systems

---

### 6.2 Mobility System

**Role:**
- Move Mars Raccoon within a defined local operating zone

**Candidate architectures (conceptual):**
- Tracked or semi-tracked system  
- Heavy-traction wheeled bogie system  
- Hybrid tracked-wheeled layout

**Architectural requirements:**
- Conservative speed  
- High traction margin  
- Wide stability envelope  
- Predictable, low-agility behavior  
- Tolerant to partial entrapment (fail-to-stable)

Mobility is architecturally **subordinate** to Vault and Retrieval:  
If necessary, the system can be considered successful even if mobility later fails.

---

### 6.3 Retrieval System

**Role:**
- Transfer tubes from surface to the vault intake  
- Operate with wide misalignment and dust tolerance  
- Never prioritize “mission success” over tube safety

**Candidate conceptual structure:**
- Funnel / scoop style intake with guiding geometry  
- Compliant capture elements  
- Force-limited extraction mechanism  
- Simple motion degrees-of-freedom (few axes, low precision, high robustness)

Architectural constraints (from Phase 1):

- No high-precision robotic arms as the primary mechanism  
- Passive geometry does as much work as possible  
- Aborts are always safer than forcing a grab  
- System recognizes “walk away” conditions based on burial and resistance

---

### 6.4 Storage Vault System

**Role:**
- Provide protected internal volume for tubes  
- Maintain retention under shock, vibration, and partial chassis damage  
- Prevent tube-on-tube impact and abrasion  
- Stay protective even if the rest of the system dies

**Conceptual features:**
- Individual or grouped slots/cradles for tubes  
- Shock-damping interfaces  
- Positive retention geometry (mechanical, not powered)  
- Limited, controlled ingress path from retrieval interface  
- Optional internal indexing/organization for future access

Architectural rule:

> The vault does not depend on power to remain protective.  
> Mechanical retention is the default.

---

### 6.5 Power System

**Role:**
- Supply electrical power for all active subsystems  
- Enable long idle survival and occasional activity

**Conceptual baseline:**
- Solar-based input (heritage Mars-style panel)  
- Energy storage (battery) sized for:
  - long idle periods  
  - intermittent retrieval and mobility operations  

RTG-based variants may be considered at theory level but are treated as:
- higher-cost, higher-complexity alternatives  
- subject to program-level resource and political constraints

Architectural constraints:

- Idle draw must be minimal  
- Vault must not depend on power for retention  
- Safe-hold and dormancy states must be supported

---

### 6.6 Thermal Management System

**Role:**
- Maintain survivable temperature ranges for:
  - electronics  
  - mechanical components  
  - stored tubes (within acceptable bounds)

**Conceptual tools:**
- Passive insulation  
- Radiative surfaces  
- Internal thermal mass  
- Possibly shared thermal strategy with power system

Architecture must assume:
- thermal behavior couples strongly to power availability  
- extremes must be handled passively as much as possible

---

### 6.7 Avionics & Control System

**Role:**
- Implement supervised, deterministic behavior  
- Manage modes (Idle, Transit, Retrieval, Safe-Hold, etc.)  
- Process commands from ground  
- Execute low-rate autonomy or hazard checks

Architectural constraints:

- Simple, interpretable logic over complex autonomy  
- Safe defaults under uncertainty or partial failure  
- Clear separation between:
  - command interpretation  
  - low-level control  
  - safety interlocks

System design must make behavior predictable under telemetry review.

---

### 6.8 Communications & Integration Interfaces

**Role:**
- Exchange commands and telemetry with mission infrastructure  
- Integrate into the Mars Sample Return operations cadence  
- Support localization or identification for downstream retrieval systems

Conceptual requirements:

- Use standards consistent with MSR-era comms expectations  
- Support low-duty-cycle operations  
- Provide enough state info for:
  - knowing where the raccoon is  
  - knowing vault load state  
  - knowing health / mode

---

## 7. Architectural Design Principles (Non-Negotiable)

The system architecture is constrained by the following principles:

1. **Tube Safety First**  
   - Every architectural decision is measured by its impact on tube safety.

2. **Simplicity Over Cleverness**  
   - Complexity increases failure risk and review discomfort.  
   - Passive solutions beat active ones when technically adequate.

3. **Fail-to-Depot**  
   - Architecture prefers failure states where the raccoon becomes a static depot with intact tubes.

4. **Mission Support, Not Mission Center**  
   - Architecture must not encroach on rover / helicopter / ascent roles.  
   - Logistics role is baked into subsystem choices.

5. **Deterministic Behavior**  
   - The fewer surprises, the better.  
   - Behavior under stress should be explainable and predictable.

6. **Power Austerity**  
   - Architecture assumes power scarcity.  
   - Movement is rare; waiting is normal.

7. **Theory-Only Boundary**  
   - All architecture here is **non-executable** under TEL-1.0.  
   - It describes how a system *could* be built under license, not how it *must* be built now.

---

## 8. Constraints Imported from Phase 1

The architecture must respect these Phase 1 constraints:

- **Retrieval Constraint:**  
  Retrieval is feasible but bounded. System must allow “no-go” calls on buried or unsafe tubes without penalty.

- **Mobility Constraint:**  
  Movement envelope is local, conservative, and terrain-limited; architecture cannot assume rover-like exploration.

- **Vault Constraint:**  
  Vault integrity is a hard requirement; any architecture that places vault at major structural risk is rejected.

- **Power Constraint:**  
  Solar-based architecture must be viable; RTG variant is not assumed baseline.

- **Failure Behavior Constraint:**  
  Safe states must be architected in, not bolted on.

- **Ops Constraint:**  
  System must fit into NASA-style supervised operations with low-frequency command cycles.

---

## 9. Notional Physical Configuration (Conceptual Only)

A plausible, non-binding conceptual layout:

- **Lower module:**  
  - Mobility system  
  - Chassis frame  
  - Battery and power distribution

- **Central module:**  
  - Storage vault (structural core)  
  - Thermal mass and insulation  
  - Structural stiffeners that route loads around vault

- **Upper / forward module:**  
  - Retrieval system (scoop / intake)  
  - Intake tunnel into vault interface  
  - Sensor package for local perception and alignment

- **Exterior surfaces:**  
  - Solar array (deployable or fixed, depending on heritage reuse)  
  - Antenna / comms hardware

Again: this is conceptual, not prescriptive.

---

## 10. Dependency & Priority Map

From an architectural priority standpoint:

1. **Vault** — primary mission value  
2. **Retrieval** — secondary, high-impact capability  
3. **Power & Thermal** — enablers of time and survival  
4. **Mobility** — facilitator, but mission value can persist even if lost  
5. **Avionics & Comms** — required for active operations, but vault must still be safe without them  

Architecture design rule:

> If a conflict arises, **Vault safety wins**, even if it constrains Retrieval, Mobility, or Power optimization.

---

## 11. Theory-Only Disclaimer

All content in this document is:

- conceptual  
- non-executable  
- provided for reasoning, analysis, and design discussion only  

No reader has:

- permission to build  
- permission to test  
- permission to deploy  
- permission to sell or offer services based on execution  

without a separate, explicit **Phase 3 Execution License**.

---

## 12. Status

- System architecture concept: **defined** (theory-only)  
- Ready for:  
  - Subsystem breakdown and interface detailing  
  - Conceptual prototype pathway definition  
  - Risk and constraint documentation

Next document:  
`02_Subsystem_Breakdown_and_Interfaces.md`
