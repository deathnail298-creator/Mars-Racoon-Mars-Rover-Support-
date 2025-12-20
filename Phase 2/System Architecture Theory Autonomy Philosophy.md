### Autonomy Scope — Bounded, Conservative, Non-Heroic

Mars Raccoon is not an AI robotics showcase. Its autonomy is intentionally scoped to be boring, conservative, and failure-tolerant.

The crawler does NOT attempt cinematic, perception-heavy heroics like:
- dynamic terrain reasoning at rover sophistication
- advanced visual AI under extreme dust/noise
- complex manipulation intelligence

Instead, autonomy follows three principles:

1) **Bias to Simplicity**
- Prefer predictable routes to patrol zones.
- Prefer “known tube drop zones” rather than open-world hunting.
- Prioritize behaviors that can succeed with degraded sensing.

2) **Recognition Discipline**
Tube recognition is expected to rely on:
- known tube geometry
- constrained search areas
- modest-level perception + geometric filtering
Not dependent on “vision miracles.” If it cannot confirm, it does not retrieve.

3) **Graceful Failure**
- If dust, shadowing, or burial degrade recognition, it defers rather than risks damage.
- Worst case: it fails to retrieve a tube. It does not endanger stored tubes or itself.

Autonomy exists to make Mars Raccoon *competent*, not “smart.” Competence is sufficient.
