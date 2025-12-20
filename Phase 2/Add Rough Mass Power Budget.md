### Conceptual Size / Power Class (Non-Execution, Architectural Bounds)

This is not a design commitment; it is an architectural discipline boundary. The Mars Raccoon is intentionally scoped as a **low-mass, low-power, boring utility crawler** that coexists with higher-value MSR assets instead of competing with them.

**Mass Class (Conceptual Band Only)**
- Expected system mass: **20–50 kg**
- Absolutely not in the 100+ kg rover class
- Lives comfortably in the “secondary lander payload” ecosystem
- Sized to be politically survivable, logistically affordable, and launch-rational

**Power + Energy Philosophy**
- Designed as a **low-duty-cycle asset**: mostly sleeping, occasionally moving
- Nominal storage class: **~100–300 Wh**
- Operational bursts rather than continuous traverse
- Assumes **solar trickle recharge**, not hero power regimes
- Explicit intent: **does not compete with flagship energy budgets**

**Behavioral Envelope**
- It is slow, patient, persistent infrastructure
- It does not race, sprint, or perform cinematic rescues
- It wins by *existing for a long time and quietly doing its job*

This establishes architectural sanity: this is a tens-of-kilograms crawler that sips power, not a rover-class science vehicle requiring heroic power and mass allocations.
