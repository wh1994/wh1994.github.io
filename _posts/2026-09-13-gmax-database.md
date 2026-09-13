---
title: "A Harmonized Database of Small-Strain Shear Modulus Measurements on Sands and Gravels"
date: 2026-09-13
permalink: /posts/2026/09/gmax-database/
excerpt: "1,045 Gmax measurements on 95 sands and gravels, harmonized from two published databases — statistics, a benchmark of four empirical correlations, a recalibrated explicit equation, and a calibrated quantile surrogate model you can run in your browser."
tags:
  - Gmax
  - small-strain stiffness
  - sand
  - database
  - machine learning
toc: true
toc_sticky: true
---

> **Try it yourself:** the calibrated surrogate model and the classical correlations are available as an [interactive Gmax predictor](/apps/gmax/) that runs entirely in your browser.

## Abstract

A database of 1,045 small-strain shear modulus (G<sub>max</sub>) measurements on 95 clean sands and gravels is compiled by harmonizing two published datasets: the stiffness-curve database of Oztoprak & Bolton (2013) and the SAND-Small database of Lo et al. (2021). Missing index void ratios (e<sub>max</sub>, e<sub>min</sub>) of the Oztoprak & Bolton records are recovered by exact back-calculation from stored void-ratio–relative-density pairs or from the original literature, with every value validated against the stored data; the provenance of every quantity is recorded per record. Statistical analysis shows that stress level and packing state are uncorrelated across the database (no confounding), that log G<sub>max</sub> is governed primarily by mean effective stress (ρ = +0.73) and void ratio, and that grading acts on G<sub>max</sub> largely through void ratio. Four empirical correlations are benchmarked; when each sand is weighted equally, none achieves both low bias and low scatter, and the two grading-dependent models fail outside their calibration ranges. A recalibrated explicit equation with a C<sub>u</sub>-dependent stress exponent improves held-out accuracy by ~8%, but the dominant error source — sand-level offsets reflecting particle shape and mineralogy — cannot be resolved by any equation in (e<sub>0</sub>, p′, C<sub>u</sub>, D<sub>50</sub>). A gradient-boosting quantile surrogate that additionally uses e<sub>max</sub> and e<sub>min</sub> as shape proxies reduces held-out error by 16% and, after conformal calibration on held-out sands, returns prediction intervals with exact 50% and 90% coverage, so every prediction carries an honest statement of its reliability. The database is published in a standardized, extensible CSV format.

---

## 1. The database

### 1.1 Sources

| Code | Source | Records | Content |
|---|---|---|---|
| OB2013 | Oztoprak & Bolton (2013), Géotechnique 63(1), via the CC0 digitization of Charles, Oztoprak & Gourvenec (2022), Univ. of Southampton, DOI 10.5258/SOTON/D2101 | 240 | G<sub>0</sub> plus full G/G<sub>0</sub>–strain degradation curves (2,861 points), resonant column and torsional shear, 23 studies |
| LO2021 | Lo, Wei, Chian & Ku (2021), J. Geotech. Geoenviron. Eng. 147(5) ("SAND-Small") | 805 | G<sub>max</sub> from bender element (123) and resonant column (682) tests, 10 studies |

Together: **1,045 measurements, 95 distinct materials, 32 source studies**, spanning p′ = 15–590 kPa (median 150), e<sub>0</sub> = 0.20–1.50, D<sub>r</sub> = 8–112%, D<sub>50</sub> = 0.10–70 mm, C<sub>u</sub> = 1.0–133, G<sub>max</sub> = 36–1,165 MPa. All materials are clean (fines-free) sands and gravels. Per-sand coverage is shown in Figure 1.

![Figure 1 — per-sand coverage](/images/posts/gmax-database/fig_gmax_coverage_dotplot.png)
*Figure 1. Database coverage, one row per material sorted by grain size: D<sub>50</sub> (black, top axis) and C<sub>u</sub> (orange, bottom axis), stress range, relative density range, void ratio range, and number of tests.*

### 1.2 Harmonization and recovery of index void ratios

The two sources report different variable sets. Harmonization decisions, all recorded per record in a provenance column:

- **Stress.** OB2013 stores mean effective stress p′ (converted MPa→kPa); LO2021 stores the isotropic consolidation stress σ′₃, taken as p′ (`p_mean_provenance = "assumed equal to sigma3 (isotropic)"`).
- **Index void ratios.** LO2021 reports e<sub>max</sub>/e<sub>min</sub> directly (789 records). OB2013 does not — but it stores (e<sub>0</sub>, D<sub>r</sub>) per test, and since

$$
D_r = \frac{e_{\max}-e_0}{e_{\max}-e_{\min}},
$$

The points of one sand fall on the exact straight line

$$
e_0 = e_{\max} + D_r\,(e_{\min}-e_{\max}).
$$

For every sand tested at ≥2 densities the pair was recovered **exactly** (fit residuals < 2×10⁻⁶; 122 records). For single-density sands the values were taken from the original papers and accepted only if they reproduce the stored D<sub>r</sub> within ±0.015 (61 records). 73 records (mostly gravels in paywalled sources) remain without limits.

The recovery uncovered several data-forensics results worth recording:

1. **Two sands can share D<sub>50</sub> and C<sub>u</sub>.** The Tika et al. (2003) group at D<sub>50</sub> = 0.20 mm/C<sub>u</sub> = 1.1 produced a physically impossible joint fit (e<sub>max</sub> = −0.18); the paper's Tables 1–2 revealed it is two different sands (S1: 0.982/0.617 and S4: 1.044/0.719), assigned per test via the D<sub>r</sub> check.
2. **Stored D<sub>r</sub> values are internally consistent but can contradict the source paper.** Ban-nosu Sand B back-calculates exactly to 0.82/0.68 while Iwasaki et al. (1978) print 1.01/0.68; the database keeps the internally consistent pair with a note.
3. **Material identifications.** "Yamashita & Toki 1995a/b" are Ishikari sand (1.416/0.837) and Toyoura sand (0.970/0.618); "Fioravante et al. 1998" is the Quiou carbonate sand study of Fioravante et al. (1994) — its back-calculated 1.281/0.831 (shared with the Lo Presti et al. 1997 coarse group) matches Quiou, explaining the anomalously high void ratios.
4. Cross-lab validation: two independent studies of Ticino-lab Quiou sand and six independent Toyoura programs recover mutually consistent limits.

Anomalies in the sources (D<sub>r</sub> up to 112%, e<sub>0</sub> < e<sub>min</sub> on 38 records) are flagged (`quality_flags`), not altered.

---

## 2. Statistical overview

![Figure 2 — statistics](/images/posts/gmax-database/fig_gmax_stats.png)
*Figure 2. (a) D<sub>r</sub> distribution (median 75%); (b) stress levels (64% of tests within 10% of 50/100/200/400 kPa); (c) Pearson correlation matrix; (d) G<sub>max</sub> vs p′ colored by D<sub>r</sub>, with pooled power-law fit.*

Key observations:

- **No confounding between state and stress**: log p′ is uncorrelated with both D<sub>r</sub> (−0.02) and e<sub>0</sub> (−0.02) — the database supports unbiased estimation of both effects.
- **log G<sub>max</sub> is driven by log p′ (+0.73), then e<sub>0</sub> (−0.35) and D<sub>r</sub> (+0.26).** The pooled power-law fit (shown below; ρ = 0.73 in log–log) recovers the classic ≈0.5 stress exponent.
- **Grading acts through void ratio**: e<sub>0</sub> correlates with log C<sub>u</sub> (−0.61) and log D<sub>50</sub> (−0.51) — better-graded and coarser materials pack denser — while the direct correlations of grading with G<sub>max</sub> are weak once stress is accounted for.
- Detrending the stress effect leaves a void-ratio slope of −0.46 per unit e<sub>0</sub> on log G<sub>max</sub> (ρ = −0.50): denser is stiffer, in Hardin-type fashion.

The pooled power-law fit is

$$
G_{\max} = 109\left(\frac{p^{\prime}}{100\,\mathrm{kPa}}\right)^{0.46}\,\mathrm{MPa}.
$$

A structural caution that shapes everything downstream: the Wichtmann & Triantafyllidis quartz series contributes 623 of 1,045 tests (25 artificially graded sands from one laboratory). **Test-weighted statistics therefore mostly measure agreement with one source.** All model evaluation below reports *per-sand balanced* metrics (every material counts equally) alongside conventional per-test values.

---

## 3. Performance of existing correlations

Four correlations spanning three generations were evaluated exactly as coded in engineering practice (G₀ and stresses in kPa, $p_a$ = 100 kPa):

**Hardin & Richart (1963), angular-grain form:**

$$
G_0 = 3270\,\frac{(2.97-e_0)^2}{1+e_0}\,\sqrt{p'}
$$

**Oztoprak & Bolton (2013), mean curve:**

$$
G_0 = 5760\,\frac{p_a}{(1+e_0)^3}\left(\frac{p'}{p_a}\right)^{0.49}
$$

**Wang (2022):**

$$
G_0 = 64{,}300\; C_u^{-0.21}\; e_0^{\,-1.08-(0.09\,D_{50})^{0.51}} \left(\frac{p'}{p_a}\right)^{0.47\,D_{50}^{0.06}}
$$

**Wichtmann & Triantafyllidis (2009):**

$$
\begin{aligned}
G_0 &= \left(1563 + 3.13\,C_u^{2.98}\right)\frac{(a-e_0)^2}{1+e_0}\; (p^{\prime})^{n}\,p_a^{1-n}, \\
a &= 1.94\,\exp\!\left(-0.066\,C_u\right), \\
n &= 0.40\,C_u^{0.18}.
\end{aligned}
$$

![Figure 3 — benchmark](/images/posts/gmax-database/fig_g0_benchmark.png)
*Figure 3. Predicted vs measured G<sub>max</sub> for the four correlations (dashed lines: factor 2).*

**Results (all 1,045 records; "balanced" = per-sand equal weight):**

| Correlation | Bias (test-wtd) | RMSE<sub>log</sub> (test-wtd) | Bias (balanced) | RMS<sub>log</sub> (balanced) |
|---|---|---|---|---|
| Hardin & Richart 1963 | ×1.01 | 0.120 | ×0.90 | 0.195 |
| Oztoprak & Bolton 2013 | ×1.23 | 0.123 | ×1.11 | 0.201 |
| Wang 2022 | ×0.98 | 0.201 | ×1.01 | 0.400 |
| Wichtmann & Triantafyllidis 2009 | ×0.99 | 0.249 | ×1.13 | 0.596 |

Findings:

- **The 62-year-old Hardin–Richart equation remains the most robust general-purpose choice** — near-zero test-weighted bias, tightest scatter, stable out to gravels — using only e<sub>0</sub> and p′. On a per-sand basis it under-predicts the typical sand by 10%.
- **Oztoprak & Bolton over-predicts by a consistent ~23% (test-weighted)** on this database — notable because 240 records are its own source data; the offset is dominated by the BE/RC clean-sand measurements of LO2021.
- **The grading-dependent models are sharp inside and unreliable outside their calibration domains.** Wang (2022) achieves the lowest clean-sand scatter (0.107) but its e⁻ˣ void-ratio function collapses for the loose calcareous Cabo Rojo sand (e<sub>0</sub> up to 1.5) and its balanced RMS doubles on the full set. W&T (2009) is excellent on its own quartz series but errs by up to a factor of 10 at C<sub>u</sub> > 40, where its (a−e)² term degenerates.

---

## 4. An improved explicit equation — and its ceiling

Nested Hardin-type candidates (2–5 parameters, C<sub>u</sub>/D<sub>50</sub> multipliers, C<sub>u</sub>-dependent stress exponents, a recalibrated W&T form) were fitted in log space with per-sand weights and selected by **sand-grouped 5-fold cross-validation** — whole sands held out, so the score measures transfer to unseen materials — using the per-sand balanced RMS. The winner (4 parameters):

$$
G_{\max} = 40.8\;\frac{(2.97-e_0)^2}{1+e_0}\; C_u^{-0.073} \left(\frac{p'}{p_a}\right)^{0.26\,+\,0.34\log_{10}C_u} \;\;\text{[MPa]}
$$

The C<sub>u</sub>-dependent stress exponent (0.31 for uniform sands → ~0.9 for well-graded gravels) is the only grading feature that survived held-out-sand validation; richer forms (free Hardin constant, D<sub>50</sub> terms) did not. Residual diagnostics (Figure 4) are trend-free in p′, e<sub>0</sub> and C<sub>u</sub>.

![Figure 4 — proposed equation](/images/posts/gmax-database/fig_g0_newmodel.png)
*Figure 4. Proposed equation: predictions and residual diagnostics.*

Balanced performance: bias ×1.00, RMS<sub>log</sub> 0.175 (fit), 0.180 (cross-validated) — an ~8% improvement over Hardin–Richart with unbiasedness by construction. **But this is close to the ceiling for any equation in (e₀, p′, C<sub>u</sub>, D₅₀):** the residuals are dominated by *sand-level offsets* — a given sand sits systematically stiff or soft, by up to a factor of 2, because of particle shape, angularity and mineralogy that these four variables do not encode. More parameters redistribute this error; they cannot remove it. Two consequences follow: (i) point predictions need a variable that carries the shape signal, and (ii) honest use requires quantified uncertainty. Both lead to the surrogate model.

---

## 5. Calibrated quantile surrogate model

### 5.1 Architecture

- **Learner:** scikit-learn `HistGradientBoostingRegressor` with pinball (quantile) loss; five independent models per tier at quantiles 5, 25, 50, 75, 95%; target log₁₀G<sub>max</sub> [MPa]. Hyperparameters kept deliberately conservative for a ~1,000-row dataset (max 15 leaf nodes, min 25 samples/leaf, L2 = 1, 400 iterations, learning rate 0.06).
- **Two tiers:**
  - *basic* — features (e₀, log p′, log C<sub>u</sub>, log D₅₀); applicable to any record (1,029 tests, 88 sands);
  - *plus* — adds **D<sub>r</sub> and (e<sub>max</sub>−e<sub>min</sub>)** (981 tests, 78 sands). The index limits are the key: they are laboratory measurements that implicitly encode particle shape and angularity — exactly the sand-level information the explicit equations lack.
- **Physics guards:** monotonicity constraints force G<sub>max</sub> to increase with p′ and decrease with e₀, preventing unphysical extrapolation wiggles.
- **Weighting:** per-sand equal weights in every fit, for the reason established in §2.

### 5.2 Judgements made, and why

1. **Sand-grouped cross-validation, never random splits.** Random splits leak: the model would see sibling tests of every sand and report flattering scores. All reported numbers come from 5-fold CV with whole sands held out.
2. **Raw quantiles are badly over-confident and cannot be used as published.** Held-out coverage of the nominal 50%/90% bands was only 0.28/0.67. Diagnosis: pooled quantile regression captures *within-sand* variability, but the residual is dominated by *between-sand* offsets — within one held-out sand, either all points fall inside the band or all fall outside.
3. **Conformal calibration targeted at per-sand balanced coverage.** Band half-widths are widened until held-out coverage, averaged over sands, hits the nominal level exactly (solved by bisection), separately for clean sands (D₅₀ ≤ 2 mm, C<sub>u</sub> ≤ 8) and coarse/well-graded materials — the two populations have genuinely different uncertainty.
4. **Additive widening in log space beats multiplicative.** Because the dominant error is a roughly constant sand-level offset in log units, adding a constant to the half-width reaches the same coverage with much narrower bands than multiplying (90% band: total factor ×2.4 vs ×5.1). The calibration mode is chosen automatically per band by which yields the narrower band at equal coverage; additive won everywhere.
5. **Quantile crossing** is removed by sorting the five quantile predictions per point before calibration.
6. **Extrapolation is declared, not hidden:** every prediction returns an `in_range` flag checking all inputs against the training domain.

### 5.3 Performance

![Figure 5 — surrogate](/images/posts/gmax-database/fig_gmax_surrogate.png)
*Figure 5. (a) Held-out median predictions with 90% intervals; (b) interval calibration before/after conformal correction; (c) predicted uncertainty vs C<sub>u</sub>; (d) example predictions with 50%/90% bands.*

Held-out (sand-grouped CV), per-sand balanced:

| Model | RMS<sub>log</sub> | Bias | 90% band, clean sands | 90% coverage |
|---|---|---|---|---|
| Explicit proposed equation | 0.180 | ×1.00 | — | — |
| Surrogate *basic* | 0.180 | ×1.03 | total factor ×2.7 | 0.90 |
| Surrogate *plus* | **0.151** | ×1.01 | **total factor ×2.4** | 0.90 |

- The *plus* tier improves point accuracy by **16%** over any explicit equation — confirmation that e<sub>max</sub>/e<sub>min</sub> carry usable shape information.
- After calibration, both the 50% and 90% intervals achieve their nominal coverage **exactly**, in both material groups (clean 0.89–0.91, coarse 0.92–0.93).
- The bands communicate reliability honestly: ×/÷ ≈ 1.55 (90%) for a clean sand, widening to ×/÷ ≈ 2.9 for gravels and well-graded materials, where data are sparse and inter-study scatter is real (Fig. 5c).
- Example: Toyoura sand at e₀ = 0.70, p′ = 100 kPa → median 118 MPa, 50% interval [102, 141], 90% interval [88, 167] MPa.

### 5.4 Practical use

The trained bundle (`gmax_quantile_model.joblib`) stores both tiers, their calibration factors and training ranges. `predict_q(e0, p0_kPa, Cu, D50_mm, emax=None, emin=None)` selects the tier from the available inputs and returns the five calibrated quantiles (MPa), the tier used, and an `in_range` flag. For end users, the **[interactive Gmax predictor](/apps/gmax/)** hosted on this site presents the empirical correlations and the surrogate side by side, with the prediction intervals and an interactive G<sub>max</sub>–p′ chart; the boosted trees are exported to JSON and evaluated in the browser (verified against scikit-learn to 10⁻⁹), so the app is a dependency-free single page. You can use it directly below:

<iframe src="/apps/gmax/" title="Interactive Gmax predictor" style="width:100%;height:900px;border:1px solid #e2e2de;border-radius:6px;" loading="lazy"></iframe>

<p style="font-size:0.9em;"><a href="/apps/gmax/" target="_blank" rel="noopener">Open the predictor in its own tab &rarr;</a></p>

---

## 6. Data availability and extensibility

The database is prepared for publication on 4TU.ResearchData (`Gmax/publication/`, v1.0, CC-BY-4.0): a master CSV (one row per measurement, 26 columns with stable keys `G####`/`S###`/`R##`, per-record provenance for e<sub>max</sub>/e<sub>min</sub>, D<sub>r</sub> and p′, and quality flags), degradation curves in long format, a citation table, a machine-readable data dictionary with controlled vocabularies, and a README with append-only extensibility rules. A validation script enforces key integrity, vocabularies, physical ranges and D<sub>r</sub>-consistency after every addition.

## 7. Limitations

- Applicability: p′ = 15–590 kPa, e₀ = 0.20–1.50, C<sub>u</sub> = 1–133, D₅₀ = 0.10–70 mm; clean, uncemented, unaged laboratory specimens; vertically propagated shear waves.
- The coarse/well-graded region rests on few materials, mostly at a single density; its wide uncertainty bands are a property of the available evidence, not of the model.
- 73 records lack e<sub>max</sub>/e<sub>min</sub> (paywalled gravel sources) and fall back to the *basic* tier.
- Test-method effects (BE vs RC) and inter-laboratory bias are absorbed into the uncertainty bands rather than modeled explicitly — a natural next step as the database grows.

## References

- Charles, J.A., Oztoprak, S. & Gourvenec, S.M. (2022). Dataset in support of "Recovering shear stiffness degradation curves from classification data with a neural network approach". Univ. of Southampton. DOI 10.5258/SOTON/D2101.

- Hardin, B.O. & Richart, F.E. (1963). Elastic wave velocities in granular soils. J. Soil Mech. Found. Div. ASCE 89(1), 33–65.

- Lo, M.K., Wei, X., Chian, S.C. & Ku, T. (2021). Bayesian network prediction of stiffness and shear strength of sand. J. Geotech. Geoenviron. Eng. 147(5), 04021020.

- Oztoprak, S. & Bolton, M.D. (2013). Stiffness of sands through a laboratory test database. Géotechnique 63(1), 54–70.

- Wang, Y. (2022). Development of constitutive models for linear and nonlinear shear modulus and material damping ratio of uncemented soils. PhD-report, Univ. of Texas.

- Wichtmann, T. & Triantafyllidis, T. (2009). Influence of the grain-size distribution curve of quartz sand on the small strain shear modulus G<sub>max</sub>. J. Geotech. Geoenviron. Eng. 135(10), 1404–1418.

*(Full list of the 32 data-source studies: `publication/GMAX_references.csv`.)*
