---
title: "Undrained Shear Strength of Clay from the CPT"
excerpt: "The cone factor approach, how to calibrate N_kt, alternative methods, and the pitfalls — deriving s_u from piezocone data."
collection: cpt101
parent: interpretation
order: 1
---

*Part of the [CPT interpretation series](/cpt-101/02-interpretation/).*

The undrained shear strength s<sub>u</sub> is the single most-requested clay parameter from a CPT sounding, and the classical route to it is disarmingly simple:

$$ s_u = \frac{q_t - \sigma_{v0}}{N_{kt}} $$

where q<sub>t</sub> is the corrected cone resistance, σ<sub>v0</sub> the total overburden stress (their difference is the *net* cone resistance q<sub>net</sub>), and N<sub>kt</sub> an empirical cone factor. Everything interesting hides in N<sub>kt</sub>.

## Choosing and calibrating N<sub>kt</sub>

* Typical values fall between **10 and 20**, with 12–15 a common starting range for onshore and offshore clays.
* N<sub>kt</sub> is *not* a constant of nature: it depends on the reference test used to define s<sub>u</sub> (triaxial compression, simple shear, vane), on clay plasticity, rigidity index, and sensitivity. An N<sub>kt</sub> calibrated against CAUC triaxial data will differ systematically from one calibrated against average or DSS strength.
* Best practice is **site-specific calibration**: pair CPTU soundings with high-quality laboratory tests on adjacent samples (or vane tests), derive N<sub>kt</sub> per unit, and only then interpret the full sounding coverage. Absent site data, adopt values from well-documented analogue clays and state the reference strength explicitly.

## Alternative and complementary methods

* **Excess pore pressure method:** s<sub>u</sub> = Δu₂/N<sub>Δu</sub> with N<sub>Δu</sub> ≈ 4–10; useful in soft clays where Δu is large and q<sub>net</sub> is small (and less sensitive to load-cell accuracy at low resistances).
* **Effective cone resistance:** s<sub>u</sub> = (q<sub>t</sub> − u₂)/N<sub>ke</sub> — a further option, though N<sub>ke</sub> is more variable.
* **Remoulded strength:** the sleeve friction f<sub>s</sub> approximates s<sub>u,rem</sub> in many clays, giving sensitivity S<sub>t</sub> ≈ q<sub>net</sub>/(N<sub>kt</sub>·f<sub>s</sub>).

## Pitfalls

1. **Skipping the q<sub>t</sub> correction.** In clays, u₂ is large and the unequal-area correction matters — uncorrected q<sub>c</sub> can underestimate strength substantially, especially with small cone-area ratios.
2. **Shallow depths.** Near the surface, q<sub>net</sub> is a small difference between two comparable numbers; scatter is inevitable.
3. **Partial drainage.** In silty or layered profiles, penetration may not be undrained — check the normalised velocity V = vd/c<sub>v</sub> before applying undrained interpretation (fully undrained typically requires V > 30).
4. **One N<sub>kt</sub> for everything.** Different units in the same profile can require different cone factors; sensitivity and OCR trends within a unit can too.

## Key references

* Lunne, T., Robertson, P. K. & Powell, J. J. M. — *Cone Penetration Testing in Geotechnical Practice* (the standard reference).
* Low, H. E. et al. (2010). Estimation of intact and remoulded undrained shear strengths from penetration tests in soft clays. *Géotechnique*, 60(11) — the benchmark calibration study across many clays.

*This article will grow with worked examples from offshore clay sites and notes on full-flow penetrometers (T-bar, ball), whose resistance factors are less sensitive to soil stiffness than the cone's.*
