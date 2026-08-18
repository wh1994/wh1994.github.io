---
title: "Statistical Analysis of the Integrated Sand Triaxial Database"
date: 2026-08-19
permalink: /posts/2026/08/sand-database-statistics/
excerpt: "What 287 drained monotonic triaxial tests say about peak strength, dilatancy, and a near-universal mobilization curve — a statistical tour of the sand triaxial test database."
tags:
  - sand
  - triaxial test
  - database
  - statistics
  - constitutive modelling
toc: true
toc_sticky: true
---

> **About this article.** This is a statistical analysis of the
> [Sand Triaxial Test Database](/posts/2026/08/sand-triaxial-database/),
> openly available under CC-BY-4.0 on 4TU.ResearchData:
> [doi.org/10.4121/086847a6-ba39-4d66-973b-6b93028c7ad8](https://doi.org/10.4121/086847a6-ba39-4d66-973b-6b93028c7ad8).

## 1. The database

The integrated dataset compiles **32 granular materials** (30 natural sands, one
sandstone rockfill, one family of glass-bead mixtures; the database's 49 material
files grouped into distinct materials, with multi-laboratory campaigns, sieve
fractions, and mixture series counted once) from published experimental
programmes into a uniform machine-readable format: **287 drained monotonic triaxial
compression tests, 62,669 digitized measurement records**. All stresses are
effective and compression is positive. The sand subset comprises 239 tests spanning:

| Quantity | Range (sands) |
|---|---|
| Confining stress σ′_r0 | 20 – 1000 kPa (median 150) |
| Relative density D_r0 | −5 – 110 % (median 70) |
| Median grain size d50 | 0.10 – 2.1 mm |
| Coefficient of uniformity Cu | 1.5 – >400 |
| Critical-state friction angle φ_c | 29.0° – 38.0° |
| Peak friction angle φ_peak (per test) | 23.2° – 48.1° (median 38.8°) |

Most curves extend to 20 % axial strain. The statistics below use the isotropically
consolidated, normally consolidated sand tests (213 tests; 186 with known density).

![Database coverage](/images/posts/sand-database-statistics/fig1_coverage.png)

**Figure 1 — Coverage.** One dot per test in the density–stress plane. The plane is
well populated for σ′_r0 = 25–400 kPa and D_r = 15–100 %; the rockfill occupies the
high-stress fringe (1.5–3.5 MPa).

![Distributions](/images/posts/sand-database-statistics/fig2_distributions.png)

**Figure 2 — Distributions.** Density is skewed toward dense states; confining
stress clusters at the conventional 50/100/200/400 kPa levels. Index properties
show the database is dominated by clean, uniform silica sands, with a few
well-graded exceptions.

## 2. Peak strength

A two-variable regression over 210 sand tests gives

> **φ_peak = 38.14° + 8.71°·(D_r0/100) − 1.13°·ln(σ′_r0/kPa)**  (R² = 0.59, RMSE = 2.13°)

![Peak strength](/images/posts/sand-database-statistics/fig3_peak_strength.png)

**Figure 3 — Peak friction angle vs. density and stress level.**

Insights:

- Both coefficients carry the sign and magnitude expected from Bolton's (1986)
  strength–dilatancy framework: strength grows with density and decays with the
  logarithm of stress level.
- The residual scatter (±2°) is comparable to the accuracy Bolton reported for his
  correlation — most of what the regression misses is genuine sand-to-sand
  variability (mineralogy, angularity, grading), not noise.
- Ranked drivers of φ_peak (Spearman): density ρ = 0.74, maximum dilation
  ρ = −0.72, initial void ratio ρ = −0.54, stress level ρ = −0.28.

## 3. Dilatancy

![Dilatancy](/images/posts/sand-database-statistics/fig4_dilatancy.png)

**Figure 4 — Maximum dilation vs. density and stress level.** Dilation increases
with density (ρ = −0.65) and is suppressed by stress (ρ = 0.27). Dense sands at low
stress dilate up to ~14 %; loose sands contract throughout.

The strong anti-correlation between peak strength and contraction is sharp enough
to serve as a **physics-based data-quality screen**: a test claiming high peak
friction *and* strong net contraction is internally inconsistent. Applied to the
whole database, this screen isolated exactly one material — all six Stockton Beach
sand tests carried an inverted volumetric-strain sign inherited from the source
figure (which plots dilation as positive). The error was confirmed against the
source publication, corrected at the source file, and documented in the material's
notes. No other material shows the signature.

## 4. Empirical cross-sand quantile bands

![Empirical bands](/images/posts/sand-database-statistics/fig5_empirical_bands.png)

**Figure 5 — Normalized stress–strain bands.** Pooling all sands after normalizing
q by confining stress shows the canonical progression: loose sands harden
monotonically to q/σ′_r0 ≈ 2.5; dense sands peak near 3.5 at 4–6 % strain and
soften toward a common large-strain level near 2.7 (the critical-state signature).
The 25–75 % band (roughly ±0.4 in normalized stress) is the irreducible cross-sand
spread that any prediction conditioned only on density and stress must carry as
uncertainty.

## 5. A near-universal mobilization curve

![Normalized collapse](/images/posts/sand-database-statistics/fig6_normalized_collapse.png)

**Figure 6 — Mobilized strength vs. √stress-normalized shear strain.** Plotting
q/q_max against (ε_a − ε_r)/√σ′_r0 (with ε_r = (ε_v − ε_a)/2) removes both the
strength scale and the stiffness scale — the √σ′ scaling mirrors the classical
G ∝ √p′ pressure dependence. What remains is nearly universal:

- ~80 % of strength is mobilized by x ≈ 0.3–0.4 %/√kPa in **every** density class;
- the peak is reached at x ≈ 0.7–1.0;
- the cross-sand interquartile spread roughly **halves** relative to Figure 5
  (mean IQR/median: loose 0.178 → 0.105, medium 0.202 → 0.097, dense
  0.207 → 0.143);
- the residual spread concentrates in the post-peak branch of dense sands —
  softening rates remain the most sand-specific feature.

![Volumetric response normalized](/images/posts/sand-database-statistics/fig7_epsv_normalized.png)

**Figure 7 — Volumetric response vs. √stress-normalized axial strain** (dilation
plotted upward). The same strain scaling organizes the volumetric behaviour: the
interquartile band narrows by 15–22 % in every density class relative to plain
axial strain (loose 2.05 → 1.66 %, medium 3.07 → 2.64 %, dense 2.61 → 2.04 % mean
width). The strain at which contraction turns to dilation, like the strain to
peak, scales with √σ′_r0.

## 6. Direct insights

1. **Classical sand mechanics holds across 30 different sands**: a two-variable
   Bolton-type law explains 59 % of peak-strength variance with 2.1° RMSE, and the
   density–dilatancy–strength correlations are strong and correctly signed.
2. **Density is the dominant state variable** for strength and dilatancy; stress
   level is secondary; what neither explains is mostly intrinsic friction —
   φ_c spans 29–38° across the database, so at identical (D_r, σ′) two sands can
   differ by several degrees in φ_peak without any dilatancy difference.
3. **Normalization reveals structure**: mobilized strength against
   √stress-normalized shear strain collapses all sands onto a nearly universal
   mobilization curve, halving the apparent cross-sand variability — evidence that
   much of the spread in raw stress–strain space is scale, not shape. The same
   scaling tightens the volumetric bands by ~20 %.
4. **What stays irreducible** is the post-peak softening of dense sands and the
   magnitude of dilation — the natural targets for material-specific descriptors
   (d50, Cu, φ_c, particle shape) in any predictive model.
