# Phase 1 — Mobility and Navigation Limits

## 1. Purpose of This Document

This document tests another core assumption:

> **Mars Raccoon can move reliably, safely, and boringly within its intended operating zone using conservative mobility and navigation.**

If movement requires heroics, precision acrobatics, or fragile autonomy,  
Mars Raccoon fails its identity and likely its feasibility.

So mobility realism must be proven, not assumed.

---

## 2. Mobility Philosophy (Restated)

Mars Raccoon mobility is explicitly:

- slow
- conservative
- torque heavy, not speed optimized
- stability biased
- safety-first

The platform should behave more like a **crawl vehicle** than a rover:

> “If it looks exciting, something is wrong.”

---

## 3. Operating Reality Assumptions

Phase 1 assumes Mars Raccoon will operate primarily in:

- known sample cache zones
- terrain already mapped reasonably well by primary mission assets
- environments selected intentionally by mission planners (not random Mars wilderness)

It is not required to:
- traverse kilometers
- explore unknown zones
- handle cliffside hero terrain

It is required to:
- move within localized zones
- reach scattered tubes inside those zones
- avoid getting stuck like an idiot

---

## 4. What Mobility Must Actually Achieve

Plain-English requirements:

1️⃣ Move from standby location to a tube region  
2️⃣ Traverse modest slopes, soft regolith, and mild irregular terrain  
3️⃣ Avoid entrapment conditions  
4️⃣ Maintain stability and traction  
5️⃣ Arrive without exhausting power margins  
6️⃣ Be capable of returning or repositioning predictably  

Nothing more is expected.
Nothing more should be designed.

---

## 5. Mobility Constraints

### 5.1 Environmental Constraints
Mars Raccoon mobility must respect:

- loose regolith
- fine dust
- embedded rocks
- shallow depressions
- low temperatures affecting materials
- varying terrain hardness

### 5.2 Stability Constraints
Vehicle design must prioritize:

- low center of gravity
- wide contact footprint
- predictable handling
- resistance to tip and roll

If a terrain interaction leads to frequent near-roll events,  
the system is fundamentally wrong.

---

## 6. Expected Problem Scenarios

Phase 1 assumes mobility may face:

- soft sink-prone soil
- longitudinal ruts
- mild slopes + loose material combined
- ridge crossing
- small embedded rocks
- partial wheel burial
- traction loss

If Mars Raccoon only works on perfect, clean flats, it does not work.

---

## 7. Navigation Reality Check

Navigation is not a computer science victory parade.
It needs to be:

- bounded
- predictable
- supervisor friendly
- tolerant to uncertainty

Phase 1 must prove:

- navigation does not require high-frequency AI autonomy
- deliberate tasking with conservative path planning is enough
- hazard detection can be simple and still safe
- comms cadence supports planned movements

If navigation requires realtime continuous piloting, the concept breaks politically and operationally.

---

## 8. Candidate Mobility Architectures to Study

We are not choosing a final design here.
We are testing feasibility categories.

---

### Architecture A — **Tracked / Crawler Mobility**

**Strengths**
- maximum traction
- great soft soil behavior
- stable platform
- conservative and well-understood

**Risks**
- dust + track mechanics
- mechanical wear complexity
- potential energy efficiency concerns

Highly aligned with “boring survivable machine” identity.

---

### Architecture B — **Wheeled Heavy-Traction Vehicle**

**Strengths**
- proven Mars heritage
- simpler mechanics
- potentially efficient
- easier to maintain conceptually

**Risks**
- entrapment if poorly designed
- requires meaningful traction margin
- wheel-sink scenarios must be proven survivable

Acceptable only if design stays extremely conservative.

---

### Architecture C — **Hybrid Bogie or Semi-Tracked System**

**Strengths**
- stability benefits
- terrain smoothing capability
- enhanced obstacle handling
- potentially ideal middle ground

**Risks**
- mechanical complexity
- potential maintenance demands

Worth study only if reliability doesn’t degrade.

---

## 9. Key Engineering Questions Phase 1 Must Answer

Phase 1 needs hard answers to:

1️⃣ What is the realistic max slope tolerance in loose soil?  
2️⃣ What torque and traction reserves are truly necessary?  
3️⃣ How easy is it to get stuck compared to nominal movement?  
4️⃣ How severe is dust wear on chosen mobility system?  
5️⃣ Can movement be done without demanding aggressive precision control?  
6️⃣ What are realistic energy costs per traversal?  

If the honest answers point toward:

- razor-thin margins
- constant risk of entrapment
- or “this only works in perfect terrain”

Mars Raccoon mobility fails its mission identity.

---

## 10. Test & Evaluation Framework

### 10.1 Physical Analog Testing
- regolith simulant bed traversal
- slope + loose soil trials
- track / wheel sink and recovery behavior
- low-speed controlled maneuver tests

### 10.2 Simulation / Modeling
- traction modeling
- center of gravity stability envelope analysis
- entrapment probability scenarios
- torque/power requirement curves

### 10.3 Failure Mode Studies
- what happens if only one side loses traction?
- what if the platform partially sinks?
- what if drivetrain partially fails?

Mobility failures should resolve to:

- stuck but stable
- recoverable stop
- safe idle

Not:

- tipped over
- violently destabilized
- self-destructive thrashing

---

## 11. Power Reality for Mobility

Mobility cannot assume power abundance.
Phase 1 must confirm:

- movement is energy-rare but feasible
- idle robustness dominates power budget
- travel does not meaningfully endanger survival

If “one decent drive equals huge mission risk,” mobility is wrong.

---

## 12. Navigation Control Model Testing

Phase 1 evaluates whether:

- path planning can be low frequency
- supervision cadence matches NASA comfort
- hazard detection can be simple and still safe
- safe-stop defaults are realistic

If navigation requires:
- continuous piloting
- tight AI autonomy dependence
- risky obstacle threading

Then Mars Raccoon becomes an operations burden instead of a relief.

---

## 13. Mobility & Navigation Pass/Fail Criteria

### PASS IF:
- slow and conservative movement is viable
- stability envelope is wide
- entrapment risk is low and manageable
- dust does not cripple mobility
- navigation can be supervisory and boring
- power requirements remain reasonable

### FAIL IF:
- movement requires precision heroics
- terrain interaction is inherently risky
- platform regularly risks tipping / sinking
- navigation is software-fragile or ops-painful
- energy margins are unrealistic

---

## 14. Phase 1 Output Expectation

By the end of Phase 1 we must have:

- a preferred mobility category
- defined operational terrain envelope
- quantified slope & traction limits
- realistic power cost estimates
- failure behavior confidence
- confidence that Mars Raccoon can move **reliably and boringly**

If mobility can’t be made conservative and dependable,  
Mars Raccoon does not proceed dishonestly.

---

## 15. Status
Framework established.

Next document:
**03_Storage_Vault_and_Tube_Protection.md**
