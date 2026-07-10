---
title: "Scaling Laws & Similitude"
excerpt: "The theory behind centrifuge modelling: how length, stress, time, and force scale between a 1/N model at N·g and the full-scale prototype."
collection: centrifuge101
order: 2
---

The foundation of centrifuge modelling is **similitude**: if a 1/*N*-scale model is accelerated to *N* × g, the stress at any homologous point equals the prototype stress. From this follow the classical scaling laws:

| Quantity | Model / Prototype |
|---|---|
| Length | 1/*N* |
| Acceleration | *N* |
| Stress, strain | 1 |
| Force | 1/*N*² |
| Bending stiffness (EI) | 1/*N*⁴ |
| Time (diffusion/consolidation) | 1/*N*² |
| Time (dynamic) | 1/*N* |
| Frequency | *N* |

A few consequences worth appreciating:

* **Consolidation is fast.** Diffusion time scales with 1/*N*², so a year of prototype consolidation takes about an hour at 100g — one of the great practical advantages of the technique.
* **Time-scale conflict.** Dynamic time scales with 1/*N* but diffusion time with 1/*N*². For problems where both matter (e.g. earthquake liquefaction), the conflict is usually resolved by increasing the pore fluid viscosity by a factor of *N*.
* **Grain-size effects.** The soil grains are *not* scaled, so the ratio of structure dimension to grain size must stay large enough for the soil to behave as a continuum — a key consideration when modelling piles, cones, and interfaces.
* **Stress gradient error.** In the centrifuge, "gravity" varies with radius, so the stress profile in the model is slightly non-linear; models are designed so this error stays small (typically a few per cent).

**The definitive reference** for scaling relationships is the TC104 catalogue:

> Garnier, J., Gaudin, C., Springman, S. M., Culligan, P. J., Goodings, D., König, D., Kutter, B., Phillips, R., Randolph, M. F. & Thorel, L. (2007). Catalogue of scaling laws and similitude questions in geotechnical centrifuge modelling. *International Journal of Physical Modelling in Geotechnics*, 7(3), 1–23.

See also the [TC104 scaling laws page](https://tc104-issmge.com/scaling-laws/), which links the full catalogue.

*Planned additions: a worked example of scaling a monopile test, and a discussion of modelling-of-models as a validation technique.*
