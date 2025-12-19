# Phase 1 — Power and Uptime Model

## 1. Purpose of This Document

This document tests a critical assumption:

> **Mars Raccoon can survive long durations, support occasional mobility and retrieval operations, and remain operationally useful within realistic Mars power constraints.**

If the power story collapses into fantasy, Mars Raccoon collapses with it.

So this is a rigor and honesty exercise, not optimism.

---

## 2. Power Philosophy (Restated)

Mars Raccoon is built on one truth:

> **Movement is rare. Waiting is normal.**

The platform is designed for:

- long idle survival
- short operational bursts
- predictable energy budgeting
- conservative endurance margins

This power model should look more like **field equipment** than spacecraft showmanship.

---

## 3. Mission Profile Power Reality

Mars Raccoon’s expected duty cycle:

- **≥90% of its life:** idle / standby / guarding tubes  
- **Occasional periods:** traversal to tube  
- **Rare periods:** retrieval operation + internal handling  
- **Possibly once or twice:** relocation / rendezvous reposition

This means:

- baseline survival power dominates design
- burst operation must be affordable without panic
- system cannot rely on daily high power availability

If the concept only works assuming generous continuous power, it fails.

---

## 4. Candidate Power Architectures to Evaluate

Phase 1 does not pick final hardware.
It evaluates feasibility and realism.

---

### Option A — **Solar-Based with Energy Storage**

**Concept**
- robust solar array
- paired with battery system
- designed for extremely low idle draw
- slow recharge, patient operations

**Strengths**
- proven Mars technology
- politically and programmatically comfortable
- lightweight and understood
- supports long static durations

**Risks / Phase 1 Questions**
- dust accumulation impact
- power starvation after storms
- long winter / low light periods
- slow recharge cycles vs operational needs

This is the default architecture unless proven insufficient.

---

### Option B — **RTG-Based (Radioisotope Power)**

**Concept**
- constant trickle power
- thermal stability benefits
- extreme longevity

**Strengths**
- high reliability
- excellent survivability
- continuous slow charging

**Risks / Phase 1 Questions**
- cost class escalation
- availability constraints
- political / resource allocation issues
- weight and integration complexity

This is extremely attractive technically…
…but may fail politically or economically.

---

### Option C — **Hybrid Solar + Supplemental Solutions**

**Concept**
- solar primary
- plus:
  - improved dust tolerance strategies
  - operational positioning optimization
  - extremely low energy baseline
- focuses on architectural resilience instead of exotic systems

**Strengths**
- avoids full RTG commitment
- manageable cost class
- engineering approachable

**Risks**
- still constrained by dust and light availability
- must prove robustness under marginal cases

A likely realistic compromise path if pure solar risk proves borderline.

---

## 5. Power Demand Categories

Phase 1 must quantify and reality-check:

### 5.1 Idle Survival Power
Includes:
- baseline electronics survival
- thermal management (if required)
- health checks
- low-frequency comms readiness

Idle must be **ultra-low**.
If idle is expensive, Mars Raccoon is dead.

---

### 5.2 Communication & Operations Power
Includes:
- periodic check-ins
- command reception
- logging tasks
- supervisory operations

This should be:
- low duty cycle
- energy-budget predictable
- operationally compatible with NASA cadence

---

### 5.3 Mobility Power
Includes:
- slow traversal
- steering / stabilization
- mechanical actuation losses

Mobility:
- must be energy rare, not energy constant
- must have conservative energy uncertainty margins
- must never operate on razor-thin reserves

---

### 5.4 Retrieval Power
Includes:
- retrieval mechanism actuation
- vault interface activity

Should be:
- lower energy than mobility
- short-duration bursts
- mechanically efficient by design

---

## 6. Thermal Reality

Power and thermal are inseparable.

Phase 1 must evaluate:
- whether energy budget supports thermal survival
- whether tubes require specific internal temperature buffering
- whether the vault acts as thermal mass advantage
- whether RTG heat (if present) creates pros/cons

If the thermal survival story depends on exotic systems,
power feasibility collapses indirectly.

---

## 7. Expected Stress Conditions

Phase 1 assumes Mars will not behave nicely.

We must test survivability under:
- prolonged dust accumulation on solar
- interrupted operational cycles
- temperature dips below optimistic predictions
- long-duration idle periods
- degraded battery capacity with aging

If Mars Raccoon only survives best case,
it doesn’t survive.

---

## 8. Key Engineering Questions Phase 1 Must Answer

1️⃣ What is realistic idle power consumption?  
2️⃣ How large must storage capacity be for comfortable margins?  
3️⃣ How long can Mars Raccoon survive in full idle with poor recharge?  
4️⃣ How many traversals per Martian season are realistic?  
5️⃣ How big are mobility + retrieval energy spikes?  
6️⃣ Can power constraints coexist with failure-safe doctrine?  

These must be answered honestly, without “Mars will probably be nice.”

---

## 9. Power Failure Behavior

Power failure isn’t allowed to become catastrophic.

**Acceptable:**
- vehicle goes dormant
- vault remains closed and protective
- tubes remain safe
- vehicle can potentially be recovered physically

**Unacceptable:**
- vault loses retention because of power loss
- power drop causes mechanical release
- tubes become exposed
- platform loses positional awareness entirely

Power failure must degrade gracefully.

---

## 10. Test & Validation Strategy

### 10.1 Analytical Modeling
- power budget modeling
- energy-use envelope simulations
- long-duration scenario modeling

### 10.2 Environmental / Mission Scenario Modeling
- dust storm survivability
- degraded solar case
- low-temp / low light winter scenarios
- worst-case idle endurance evaluation

### 10.3 Hardware Feasibility Assumptions
- use technology with Mars heritage where possible
- do not rely on experimental or unproven energy systems unless justified

---

## 11. Power & Uptime Pass / Fail Criteria

### PASS IF:
- idle lifespan is long and realistic
- operational bursts are affordable
- dust and winter realities do not cripple survival
- architecture allows predictable budgeting
- failure modes remain safe

### FAIL IF:
- survival demands unrealistic energy optimism
- power collapses under routine Mars conditions
- only RTG makes concept viable but creates unacceptable programmatic friction
- failure behavior endangers stored tubes

---

## 12. Phase 1 Output Expectation

By end of Phase 1 we must have:

- credible baseline power architecture
- defined idle endurance expectations
- traversal + retrieval power budget confidence
- failure survivability logic validated
- belief that Mars Raccoon can stay alive long enough to matter

If power cannot be established realistically,
Mars Raccoon must not proceed dishonestly.

---

## 13. Status
Framework established.

Next document:
**05_Failure_Mode_Testing.md**
