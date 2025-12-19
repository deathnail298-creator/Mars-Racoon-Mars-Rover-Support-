# Phase 1 — Retrieval Mechanism Study

## 1. Purpose of This Document

This document tests a core assumption:

> **Mars Raccoon can pick up Mars sample tubes using a rugged, simple,
failure-tolerant retrieval system that does not require fragile precision robotics.**

If this assumption collapses, Mars Raccoon collapses with it.
So we treat this as a critical engineering reality check.

---

## 2. Retrieval Philosophy (Restated)

Mars Raccoon is not allowed to be clever.
Its retrieval system must:

- work with **wide tolerances**
- survive dust
- avoid precision dependence
- favor robustness over elegance
- protect the tube above all else

If design options drift toward “delicate robotic hand,” we are doing it wrong.

---

## 3. What the Retrieval System Actually Needs To Do

Not theoretical.
Plain English.

The retrieval mechanism must:

1️⃣ Approach tube with approximate positional accuracy  
2️⃣ Secure and stabilize tube physically  
3️⃣ Lift or feed the tube into internal storage path  
4️⃣ Place tube into storage cradle without scraping or shock damage  
5️⃣ Confirm retention  

Anything beyond this is unnecessary.

---

## 4. Tube Handling Constraints

### 4.1 Tube Physical Considerations
Retrieval must respect:

- tube structural integrity
- coatings and seals
- labelling / identification preservation
- contamination protection

Mars Raccoon must assume:

- tubes may be partially embedded
- tubes may be covered by dust
- tubes may not be “perfectly placed”

### 4.2 No-Damage Rule
Retrieval system must not:

- clamp too hard
- bend tubes
- scratch critical identification markings
- introduce internal contamination risks
- expose tubes to violent dynamic shock

The tube is more valuable than the robot.

---

## 5. Expected Difficult Retrieval Scenarios

Phase 1 assumes retrieval may involve:

- tubes partially buried by drifting regolith
- tubes lying at slight angles
- tubes sitting near small rocks
- tubes in loose sand
- tubes in moderately sloped terrain
- tubes with dust adhesion
- tubes not neatly aligned to the robot

If retrieval only works in ideal conditions, it does not work.

---

## 6. Candidate Retrieval Approaches

We do not pick final implementation in Phase 1.
We explore credible categories and test feasibility.

The approaches below are grouped by philosophical type:

---

### Approach A — **Guided Scoop / Funnel Capture System**

**Concept**
- Position vehicle with large geometric tolerance
- Use a wide scoop or funnel mouth
- Scoop guides tube into narrowing channel
- Tube is stabilized passively by geometry
- Only final inches require controlled handling

**Strengths**
- Extremely tolerant to misalignment
- Favors passive mechanics
- Dust-resistant
- Simple actuation
- Fail-safe tendencies

**Risks to Study**
- drag force on partially buried tubes
- potential scraping risk if geometry poorly designed
- need for force limits
- performance in rocky microterrain

This is strongly aligned with Mars Raccoon philosophy.

---

### Approach B — **Clamp + Stabilize Hybrid**

**Concept**
- Mechanism gently clamps tube
- Mechanical compliance absorbs misalignment
- Tube stabilized, lifted, handed off internally

**Strengths**
- Can handle angled tubes
- Allows controlled grip force
- Mechanically understandable
- Reasonable complexity

**Risks to Study**
- still requires some precision
- clamp force calibration critical
- susceptible to particulate wear

Acceptable only if clamp design can be made dumb, compliant, and durable.

---

### Approach C — **Passive Rolling Intake (Conveyor-Style)**

**Concept**
- Tube contacted by rolling elements
- Gradually fed into intake cradle
- Avoids “lift and place” entirely

**Strengths**
- smooth motion
- potentially very tube-gentle
- no singular precision grab moment

**Risks to Study**
- dust + moving rollers = reliability questions
- more mechanical components
- possible ingestion of debris

Promising only if mechanical simplicity remains intact.

---

### Approach D — **Miniature “Low-Precision Arm”**

**Concept**
- small robotic arm
- rough positioning
- compliant gripper

**Strengths**
- familiar architecture
- flexible
- adaptable

**Risks to Study**
- violates simplicity doctrine if not aggressively constrained
- precision creep risk
- autonomy/software burden
- fragility risk increases sharply

This is last-choice unless Phase 1 proves simpler methods cannot work.

---

## 7. Key Engineering Questions Phase 1 Must Answer

Phase 1 retrieval analysis must answer:

1️⃣ How much **position tolerance** is required and realistically achievable?  
2️⃣ What **maximum safe gripping / extraction force** protects tube integrity?  
3️⃣ How much **dust accumulation** can system tolerate before failure?  
4️⃣ Can retrieval logic work with **low autonomy and human supervision**?  
5️⃣ What happens when retrieval **fails mid-attempt**?  
6️⃣ How much **mechanical complexity** is required to keep reliability acceptable?  

If answering these honestly requires:
- precision robotics
- fragile sensors
- heroic controls
- or unrealistic cleanliness…

Then Mars Raccoon must rethink retrieval.

---

## 8. Phase 1 Test & Evaluation Methods

### 8.1 Required Earth Analog Testing
- tube analog test articles
- regolith analog environments
- partial burial retrieval attempts
- retrieval under dust-coated conditions
- misalignment trials

### 8.2 Mechanical Stress Modeling
- clamp / grip stress limits
- tube bending thresholds
- vibration and shock handoff simulations

### 8.3 Failure Mode Exploration
- what happens if mechanism jams?
- what if tube falls inside the intake path?
- what if retrieval pauses mid-lift?

Failures should default to safe states:
- tube not damaged
- tube not lost
- robot not catastrophically compromised

---

## 9. Retrieval Pass / Fail Criteria

### PASS IF:
- Retrieval can be done with conservative mechanics
- Alignment tolerance is broad
- Dust does not cripple the system
- System can abort safely
- Tubes remain safe even under partially failed retrieval attempts

### FAIL IF:
- Precision robotics or advanced AI become mandatory
- Retrieval only works in ideal lab conditions
- Tubes face meaningful structural risk during normal operation
- Complexity escalates beyond Mars Raccoon’s “rugged appliance” identity

---

## 10. Phase 1 Output Expectation

By the end of Phase 1, we must have:

- a clearly preferred retrieval architecture category
- quantified tolerance ranges
- realistic expected failure rates
- engineering confidence that Mars Raccoon can retrieve tubes reliably without being fragile

If retrieval cannot be made realistically robust, Mars Raccoon must not proceed dishonestly.

---

## 11. Status
Framework established.

Next document:
**02_Mobility_and_Navigation_Limits.md**
