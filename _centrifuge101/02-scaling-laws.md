---
title: "Scaling Laws & Similitude"
excerpt: "The theory behind centrifuge modelling — the classical scaling laws, plus the practical similitude rules from the TC104 catalogue: grain-size limits, container effects, and time-scale conflicts."
collection: centrifuge101
order: 2
---

The foundation of centrifuge modelling is **similitude**: if a 1/*N*-scale model is accelerated to *N* × g, the stress at any homologous point equals the prototype stress (σ\* = ρ\* g\* l\* = 1). From this follow the classical scaling laws:

| Quantity | Model / Prototype |
|---|---|
| Length | 1/*N* |
| Acceleration | *N* |
| Stress, strain | 1 |
| Force | 1/*N*² |
| Bending stiffness (EI) | 1/*N*⁴ |
| Time (diffusion/consolidation) | 1/*N*² |
| Time (dynamic) | 1/*N* |
| Time (creep) | ≈ 1 |
| Frequency | *N* |
| Darcy permeability *k* (same soil & fluid) | *N* |
| Hydraulic gradient | 1 |
| Capillary rise | 1/*N* |

Much of what follows is distilled from the TC104 (formerly TC2) **catalogue of scaling laws** — Garnier et al. (2007) — which collects the community's accumulated experimental evidence on when these laws hold and when they need care.

## The time-scale conflict — and its two cures

Dynamic time scales with 1/*N* but consolidation time with 1/*N*². For problems where inertia and pore-pressure dissipation are coupled — earthquake liquefaction being the classic case — the two clocks disagree by a factor of *N*. The catalogue records two remedies:

1. **Increase the pore-fluid viscosity** by a factor of *N* (silicone oil or methylcellulose solutions), slowing diffusion to match dynamic time; or
2. **Reduce the particle size** so that permeability drops by the required factor — at the price of introducing new grain-size questions.

Related rate effects deserve attention even in "static" tests: the undrained shear strength of clay rises by roughly **5–15% per log cycle of strain rate**, and whether a penetration event is drained or undrained can be judged from the normalised velocity *V* = *vd*/*c*<sub>v</sub> — fully drained below *V* ≈ 0.01, fully undrained above *V* ≈ 30.

## How small can a model be? Grain-size limits

Soil grains are *not* scaled, so a structure in the model must remain large relative to the grains for the soil to behave as a continuum. The catalogue's experimentally established thresholds (B = structure dimension, d₅₀ = mean grain size):

| Problem | Minimum ratio |
|---|---|
| Shallow footing (bearing capacity) | B/d₅₀ > 35 |
| Laterally loaded pile | B/d₅₀ > 45–60 |
| Anchor plate (pull-out) | B/d₅₀ > 48 |
| Pile shaft / frictional interface | B/d₅₀ > 50–100 |
| Tunnel face stability | B/d₅₀ > 175 |
| Pipeline uplift | H/d₅₀ > 550 |

For interface problems the **normalised roughness** R<sub>n</sub> = R<sub>max</sub>/d₅₀ should match between model and prototype — interfaces behave as perfectly rough above R<sub>n</sub> ≈ 0.1–1 and perfectly smooth below R<sub>n</sub> ≈ 0.01.

## Container and boundary effects

The model lives in a box, and the box is part of the experiment:

* **Stress gradient**: "gravity" varies with radius, so the vertical stress profile is slightly non-linear — calculable, and kept to a few per cent by good model design.
* **Silo effect**: wall friction can significantly reduce vertical stress at depth; the error depends chiefly on the sample's height-to-diameter ratio.
* **K₀ preservation**: container wall deflection should stay below H/2000 to maintain at-rest conditions.
* **In-flight CPT**: keep the cone at least 10 diameters from the nearest wall (S/B > 10) in a container at least 30 cone-diameters across (D/B > 30).
* **Dynamic testing**: the ideal container deforms like a flexible shear beam — hence laminar and equivalent-shear-beam boxes for earthquake work.
* **Sample uniformity**: with good pluviation technique, dry unit weight can be controlled within ±0.5% across a container.

## Modelling of models

The community's classic self-check: test the same prototype at different scales and g-levels (e.g. a 1/50 model at 50g and a 1/100 model at 100g) and confirm the responses coincide at prototype scale. Much of the evidence behind the thresholds above comes from exactly this technique — and it remains the standard way to validate scaling assumptions on any new problem class.

## The definitive reference

> Garnier, J., Gaudin, C., Springman, S. M., Culligan, P. J., Goodings, D., König, D., Kutter, B., Phillips, R., Randolph, M. F. & Thorel, L. (2007). Catalogue of scaling laws and similitude questions in geotechnical centrifuge modelling. *International Journal of Physical Modelling in Geotechnics*, 7(3), 1–23.

The catalogue is organised as a living inventory — topics span statics, grain-size effects, in-flight testing, fluid flow, unsaturated conditions, dynamics, contaminant transport, and heat transfer, each with solved results, open questions, and references — and is maintained by [ISSMGE TC104](https://tc104-issmge.com/scaling-laws/), with updates timed to the ICPMG conference cycle.

*Planned addition: a worked example of scaling a monopile centrifuge test from my own programmes.*
