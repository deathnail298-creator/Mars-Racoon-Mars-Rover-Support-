# Phase 0 — Concept of Operations (ConOps)

## 1. Plain-English Overview

Mars Raccoon is a **logistics retrieval crawler** whose job is simple:

1. Operate within a predefined sample recovery zone  
2. Travel to individual tubes or tube clusters  
3. Retrieve them using a rugged, fault-tolerant mechanism  
4. Store them inside its internal protective vault  
5. Loiter safely, securing the collection  
6. Later be reached by another element of the Mars Sample Return system, which takes the tubes (or the entire vehicle)

It does not roam Mars freely.
It does not “explore.”
It executes **deliberate, bounded, conservative logistics operations**.

---

## 2. Operating Environment Assumptions

For Phase 0, Mars Raccoon assumes:

- Operation region is known in advance (sample depot / cache zone)
- Terrain has been partially mapped and characterized
- Tube locations are either:
  - preplanned caches, or  
  - individually taskable based on known coordinates
- Environmental realities:
  - dust
  - sloped regolith
  - temperature extremes
  - long idle periods
  - intermittent communications

Mars Raccoon is intentionally designed to **fit into this environment**, not fight it with fragile precision systems.

---

## 3. Deployment Context

### 3.1 Arrival on Mars

Mars Raccoon is delivered as part of a Mars mission architecture. It could be:

- Co-manifested with another MSR element, or
- Delivered as a small independent payload on a future lander

This document does not prescribe a specific delivery vehicle.  
It only requires that:

- Mars Raccoon reaches the surface
- It is placed within reasonable operational distance of target cache zones

### 3.2 Commissioning Phase

Once deployed:

1. Systems health check
2. Mobility test
3. Retrieval mechanism functionality check
4. Internal vault sealing & pressure integrity check (if applicable)
5. Communication integration into mission operations

No complex commissioning ceremony.
No dramatic firsts.
Just confirming the logistics system works.

---

## 4. Core Operational Loop

The Mars Raccoon operational life is defined by a repeating, controlled sequence.

### 4.1 Standby Mode

Default state is **idle and safe**.

- Low power consumption
- Minimal mechanical wear
- Awaiting tasking
- Protecting any already stored tubes

A raccoon doing nothing is not failure — it is success.  
Its job is to be dependable when needed, not to constantly prove it exists.

---

### 4.2 Task Assignment

Mars Raccoon receives recovery tasking:
- A tube location
- Or a small set of prioritized tube locations
- With navigation paths already at least partially validated by mission planners

Tasking assumptions:
- This is deliberate, not autonomous self-discovery
- Commands can be scheduled opportunistically based on mission tempo
- Navigation can emphasize safety over speed

---

### 4.3 Traversal Phase

Mars Raccoon moves to the target area:

- Very slow speed
- Conservative traction profile
- Wide stability envelope
- Navigation strategy focused on:
  - avoiding traps
  - minimizing power draw
  - not “getting clever”

Traversal is not about optimization.
It is about **predictable, boring, survival-first movement**.

If hazards appear or risk thresholds exceed conservative bounds, Mars Raccoon stops and defaults to safety.

---

### 4.4 Tube Acquisition Phase

Upon reaching a tube:

1. Positioning adjustment
2. Deploy retrieval system
3. Secure tube physically
4. Transfer into internal storage

Acquisition priorities:

- Do not damage the tube
- Do not expose tube to unnecessary shock
- Handle dust contamination conservatively
- Confirm retention

Tube is either successfully collected and stored, or the attempt is aborted safely.  
There is no mission logic that rewards “pushing luck.”

---

### 4.5 Storage Behavior

Once inside the Mars Raccoon vault:

- Tube is mechanically restrained
- Protected from abrasion
- Shielded from casual environmental insult
- Accounted for in internal inventory tracking logic

Mars Raccoon’s key obligation becomes:
> **Do not lose, damage, or mishandle what you’ve already secured.**

Tube safety supersedes the urge to go get “one more.”

---

### 4.6 Optional Return / Loiter Strategy

Depending on mission design, Mars Raccoon may:

- Return to a central rendezvous point, or
- Remain near the last collection site, or
- Move to a known safe loiter position

This is implementation-flexible.

Core rule:
Mars Raccoon should always end up somewhere **predictable and retrievable**.

---

## 5. Multiple-Tube Behavior

Mars Raccoon may collect:

- A single tube
- Several tubes
- Or operate as a rolling consolidation platform

Behavior remains the same:

- Retrieve
- Secure
- Protect
- Wait

If internal storage capacity fills, Mars Raccoon stops being ambitious.
It prioritizes safeguarding what it already holds until retrieval.

There is no “heroic last run” behavior.

---

## 6. Communications & Control Philosophy

### 6.1 Control Model

Control is expected to be:

- supervisory
- deliberate
- low-frequency
- batch command friendly

Mars Raccoon is **not** a high-tempo robot requiring continuous human piloting.  
Its job fits well into:
- scheduled operations windows
- cautious command cadence
- opportunistic retasking

---

### 6.2 Fault Behavior

If communications drop or uncertainties arise:

- Mars Raccoon prioritizes stasis and tube protection
- It does not attempt unauthorized exploration
- It does not attempt to improvise its own mission

Default safe state = **stopped, intact, guarding acquired tubes.**

---

## 7. End-of-Life and Retrieval Concept

Mars Raccoon’s story ends in one of two acceptable ways:

### 7.1 Planned Retrieval

A follow-on mission asset (lander, rover, or integrated MSR surface element) reaches Mars Raccoon and either:

- removes the tubes, or
- physically recovers the Mars Raccoon vehicle

This is the expected nominal success path.

---

### 7.2 Acceptable Non-Nominal End

If Mars Raccoon loses power or becomes immobile after successfully storing tubes:

- The tubes are **still in a consolidated, findable location**
- The vehicle is still a single, known coordinate
- Further mission elements can still attempt retrieval

This is vastly preferable to tubes being scattered across the terrain.

---

## 8. Operational Philosophy Summary

The ConOps can be summarized in one sentence:

> **Mars Raccoon turns “tubes scattered on Mars” into “tubes safely consolidated in one armored box waiting to be picked up,” using the most boring, conservative, survivable behavior possible.**

If it is:
- predictable,
- reliable,
- slow,
- durable,
- and politically quiet…

…it has done its job correctly.

---

## 9. Phase 0 ConOps Acceptance Criteria

This ConOps is considered valid if:

- Operations remain bounded and realistic
- Mars Raccoon never depends on speculative technology
- Safety and simplicity always override aggressiveness
- The presence of Mars Raccoon can only **reduce risk**, not introduce catastrophic new ones
- The ConOps reinforces the “single-purpose logistics asset” identity

All conditions are satisfied.

Mars Raccoon has a credible, disciplined Concept of Operations.
