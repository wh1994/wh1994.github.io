---
title: "Undrained Shear Strength of Clay and Its Interpretation from CPTU"
excerpt: "What controls the undrained strength of natural clay — anisotropy, stress history, sensitivity, sample quality — and how to interpret strength and OCR from CPTU, built on the Karlsrud block-sample correlations."
collection: cpt101
parent: interpretation
order: 1
toc: true
toc_sticky: true
---

*Part of the [CPT interpretation series](/cpt-101/02-interpretation/).*


## Introduction

Undrained shear strength, $s_u$, is one of the most important parameters in the design and assessment of foundations, embankments, excavations, slopes, offshore structures, and other systems involving saturated clay. At the same time, $s_u$ is often misunderstood as a single intrinsic property of the soil. In reality, the measured undrained strength depends on stress history, stress path, anisotropy, soil structure, sensitivity, strain rate, and sample quality. These dependencies become particularly important when continuous in-situ measurements such as cone penetration testing with pore-pressure measurement (CPTU) are used to infer clay strength.

This article discusses the undrained shear strength of natural clay and how it can be interpreted from CPTU measurements. The technical discussion is based mainly on two valuable papers by Karlsrud and co-workers:

- **Karlsrud, Lunne & Brattlien (1996), _Improved CPTU interpretations based on block samples_**
- **Karlsrud, Lunne, Kort & Strandvik (2005), _CPTU Correlations for Clays_**

These papers are particularly useful because the CPTU correlations were calibrated against laboratory tests on high-quality Sherbrooke block samples rather than relying mainly on conventional piston samples. The 1996 paper established the importance of sample quality and geological history in CPTU interpretation, while the 2005 paper substantially enlarged the database and developed more explicit correlations between CPTU response, overconsolidation ratio (OCR), clay sensitivity, plasticity, and undrained triaxial compression strength.

### Overview of the clay databases

The two studies should be viewed as an evolving database rather than two completely independent datasets. The 1996 study established the first block-sample-based correlations using six clay sites, while the 2005 study expanded the database to 17 sites and 58 block-sample test levels.

| Item | Karlsrud et al. (1996) | Karlsrud et al. (2005) |
|---|---:|---:|
| Main purpose | Improve CPTU interpretation using high-quality block samples | Expand the block-sample database and develop updated $s_u$- and OCR-correlations |
| Number of sites | 6 | 17 |
| Geographic coverage | Norway + Bothkennar, UK | 16 Norwegian sites + Bothkennar, UK |
| Approximate depth range | 3.1–22.4 m | 3.1–22.4 m |
| Water content, $w$ | about 25–72% | about 25–72% |
| Liquid limit, $w_L$ | about 28–90% | not tabulated systematically |
| Plasticity index, $I_p$ | about 7–53% | authors summarize the database as about 10–50%; the site table extends approximately from 4 to 53% |
| Clay fraction, $<2\,\mu\text{m}$ | about 17–49% | approximately 17–65% in the tabulated sites |
| Sensitivity, $S_t$ | typically 2–77, with an isolated value around 240 | roughly 3–200 in the authors' summary; individual site data extend to about 240 |
| OCR range | about 1.2–6.5 | about 1.2–6.3 |
| Reference $s_u$ | CAUC triaxial compression strength | CAUC triaxial compression strength, $s_{uc}$ |
| Reported $s_{uc}$ range | not summarized as a single range | about 15–150 kPa |
| Reference preconsolidation stress | Oedometer tests | Mainly CRS oedometer tests |
| Sampling | 250 mm Sherbrooke block samples | 250 mm Sherbrooke block samples |
| Key message | Sample quality and geological history strongly influence the apparent CPTU correlations | Pore-pressure response gives the most consistent estimate of $s_{uc}$; OCR, sensitivity and plasticity should be accounted for |

The database is dominated by soft to medium-stiff natural marine clays. This is important when applying the correlations outside the original geological context. The correlations should not automatically be regarded as universal relationships for all fine-grained soils.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig00-database-coverage.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig00-database-coverage.png" style="max-width:640px;width:100%;height:auto;" alt="Four-panel chart showing the ranges of plasticity index, sensitivity, OCR and CAUC strength covered by the 1996 and 2005 block-sample databases"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 1.</b> Coverage of the block-sample databases: ranges of <i>I</i><sub>p</sub>, <i>S</i><sub>t</sub>, OCR and <i>s</i><sub>uc</sub>, with the 1996 study as the initial subset and the 2005 study as the expanded dataset. Redrawn after Karlsrud et al. (1996, 2005).</figcaption>
</figure>

The underlying philosophy of the two studies can be summarized as:

$$
\boxed{
\text{Reliable CPTU interpretation}
\;\Longrightarrow\;
\text{reliable laboratory reference data}
}
$$

This point is fundamental. If the laboratory sample has been disturbed, the measured preconsolidation stress, peak strength and stress-strain response may no longer represent the in-situ clay. A CPTU correlation calibrated against such data may therefore appear statistically reasonable while being mechanically misleading.

---

## 1. Clay strength

### 1.1 Undrained shear strength is not a unique material constant

For saturated clay loaded rapidly enough that drainage is negligible, the response is commonly described using an undrained shear strength $s_u$. In practice, however, there is no unique value of $s_u$ independent of the loading mode.

Karlsrud et al. (1996, 2005) use the peak strength from anisotropically consolidated undrained triaxial compression tests as the principal reference strength for CPTU correlation. This strength is denoted here as $s_{uc}$. Other relevant strengths include: $s_{uDSS}$ (from direct simple shear tests) and $s_{ue}$ (from triaxial extension tests).

For a natural anisotropic clay,

$$
\boxed{
s_{uc}\neq s_{uDSS}\neq s_{ue}
}
$$

because each test follows a different stress path and mobilizes the soil fabric differently.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/fig-shear-mode.png"><img src="/images/cpt101/su-of-clay/fig-shear-mode.png" style="max-width:640px;width:100%;height:auto;" alt="Four-panel figure comparing triaxial compression, triaxial extension and direct simple shear tests on Drammen clay at OCR 1, 4 and 40: stress-strain curves above and pore-pressure development below"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 2.</b> Influence of shear mode on the undrained response of Drammen clay: anisotropically consolidated triaxial compression/extension (left) and direct simple shear (right) at OCR = 1, 4 and 40, with stress–strain behaviour above and pore-pressure development below. Both the mobilised strength and the pore-pressure response depend strongly on the shear mode. Redrawn after Andersen et al. (1988).</figcaption>
</figure>

This point matters when interpreting CPTU data. A value derived from a cone factor should always be associated with the laboratory strength against which that cone factor was calibrated. In the Karlsrud database, this is primarily the **peak CAUC triaxial compression strength**.

Thus, a CPTU-derived value should not automatically be interpreted as an isotropic design strength applicable to every failure mechanism.

---

### 1.2 Strength anisotropy

Natural clays develop fabric during deposition, one-dimensional consolidation, ageing and subsequent geological processes. This fabric produces directional dependence of the undrained response.

The block-sample results presented by Karlsrud et al. (1996, 2005) show the general ordering

$$
s_{uc}>s_{uDSS}>s_{ue}
$$

for many of the investigated clays.

The measured ratios show significant scatter, but the 2005 database suggests approximately:

$$
\frac{s_{uDSS}}{s_{uc}}
\sim 0.6-0.9
$$

for many low-sensitivity clays, while

$$
\frac{s_{ue}}{s_{uc}}
$$

is commonly much smaller and often lies roughly in the range of 0.35–0.5.

These values should not be treated as universal conversion factors. The important observation is that **the anisotropy itself varies between clay deposits**.

The data further suggest that:

- highly sensitive clays tend to show stronger anisotropy;
- anisotropy generally decreases as $I_p$ increases;
- no clear systematic dependence of the anisotropy ratios on OCR was observed in the database.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig04-anisotropy-ip.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig04-anisotropy-ip.png" style="max-width:640px;width:100%;height:auto;" alt="Scatter plot of the anisotropic strength ratios DSS-to-compression and extension-to-compression against plasticity index, distinguishing low- and high-sensitivity clays"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 3.</b> Anisotropic strength ratios <i>s</i><sub>uDSS</sub>/<i>s</i><sub>uc</sub> and <i>s</i><sub>ue</sub>/<i>s</i><sub>uc</sub> versus plasticity index <i>I</i><sub>p</sub>, distinguishing low- and high-sensitivity clays. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

For engineering design, this leads to an important distinction:

$$
\boxed{
s_{uc,\mathrm{CPTU}}
\neq
s_{u,\mathrm{design}}
\text{ for every loading condition}
}
$$

A foundation or slope failure mechanism may contain zones closer to triaxial compression, direct simple shear and triaxial extension. A single compression strength therefore cannot represent the entire mechanism unless anisotropy is explicitly or implicitly accounted for.

---

### 1.3 Stress history and overconsolidation ratio

The stress history of a clay is conventionally represented by the overconsolidation ratio

$$
\boxed{
OCR=\frac{p'_c}{\sigma'_{v0}}
}
$$

where

- $p'_c$ is the preconsolidation or yield stress;
- $\sigma'_{v0}$ is the current in-situ vertical effective stress.

A young normally consolidated clay has approximately

$$
OCR\approx1,
$$

whereas

$$
OCR>1
$$

indicates that the current effective stress is lower than the apparent preconsolidation stress.

The mechanical influence of overconsolidation is illustrated directly by undrained triaxial compression tests on the same clay at different OCR. With the post-swelling effective stress held constant, increasing OCR raises the mobilized undrained strength and progressively changes the pore-pressure response from strongly contractive at $OCR=1$ towards dilative behaviour, with negative excess pore pressure at $OCR=8$.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/fig-triax-ocr.png"><img src="/images/cpt101/su-of-clay/fig-triax-ocr.png" style="max-width:640px;width:100%;height:auto;" alt="Two-panel figure of CIUC triaxial tests on reconstituted clay at OCR 1, 2, 4 and 8: deviator stress versus axial strain on the left and excess pore-pressure ratio versus axial strain on the right, showing higher strength and increasingly dilative response at higher OCR"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 4.</b> Effect of OCR in undrained triaxial compression: CIUC tests on reconstituted clay, all consolidated to <i>p</i>′<sub>OC</sub> and swelled to the same effective stress <i>p</i>′<sub>0</sub> = 100 kPa, so OCR = <i>p</i>′<sub>OC</sub>/<i>p</i>′<sub>0</sub>. Higher OCR increases the undrained strength and shifts the pore-pressure response from contractive to dilative. Redrawn after Gu et al. (2016).</figcaption>
</figure>

It is tempting to interpret OCR simply as evidence that the soil was once loaded to a higher vertical stress and subsequently unloaded. Natural clay is more complicated. Apparent preconsolidation may also develop through ageing, secondary compression, chemical bonding, weathering and other geological processes.

In the 2005 database, OCR ranged approximately from 1.2 to 6.3. The highest OCR values at some sites were associated with removal of overburden, while at other sites apparent overconsolidation was attributed to secondary creep and/or chemical weathering.

This distinction is important because two deposits having the same OCR do not necessarily have the same fabric, structure or strength.

---

### 1.4 Relationship between $s_u$ and OCR

A widely used framework for expressing stress-history effects on clay strength is the SHANSEP-type relationship

$$
\boxed{
\frac{s_{uc}}{\sigma'_{v0}}
=
\alpha OCR^m
}
$$

where

- $\alpha$ is the normalized undrained compression strength at $OCR=1$;
- $m$ controls the increase in normalized strength with OCR.

The block-sample data in Karlsrud et al. (2005) were compared with relationships approximately represented by

$$
\frac{s_{uc}}{\sigma'_{v0}}
\approx0.28OCR^{0.6}
$$

and

$$
\frac{s_{uc}}{\sigma'_{v0}}
\approx0.32OCR^{0.9}.
$$

These two curves should not be interpreted as universal upper and lower laws. The more important observation is the considerable spread of the natural-clay data between them.

The database therefore demonstrates that

$$
\boxed{
OCR\text{ alone does not uniquely determine }s_u
}
$$

for natural clay.

The likely reason is that stress history cannot fully describe the in-situ structure of a natural deposit. Ageing, cementation, leaching, bonding and depositional fabric can all influence the current strength. These effects are partly destroyed when a clay is reconstituted or artificially overconsolidated in the laboratory.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig03-suc-ocr.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig03-suc-ocr.png" style="max-width:640px;width:100%;height:auto;" alt="Normalized CAUC strength plotted against OCR for the block-sample database, with two SHANSEP-type trend curves bounding the scatter"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 5.</b> Normalized CAUC strength <i>s</i><sub>uc</sub>/<i>σ</i>′<sub>v0</sub> versus OCR for the block-sample database, together with the two representative SHANSEP-type trends. Note the considerable spread of the natural-clay data between the curves. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

This is one of the most useful conceptual results in the two papers. OCR is an important state parameter, but it should not be regarded as a complete description of clay strength.

---

### 1.5 Why sample quality matters

Both papers emphasize that the development of CPTU correlations depends critically on the quality of the laboratory reference data.

Conventional piston sampling can alter:

- void ratio;
- effective stress state;
- preconsolidation stress;
- peak undrained strength;
- strain at peak strength;
- post-peak strain softening;
- stiffness.

The 1996 study illustrates this directly by comparing Sherbrooke block samples with conventional 54 mm piston samples. The block specimens showed a much clearer preconsolidation stress and a pronounced peak in CAUC testing at small strain. The disturbed piston sample, in contrast, displayed a strongly altered stress-strain response.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig01-cauc-sample-quality.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig01-cauc-sample-quality.png" style="max-width:640px;width:100%;height:auto;" alt="CAUC stress-strain curves for Lierstranda clay from a block sample, a 75 mm piston sample and a 54 mm piston sample, showing progressive loss of the peak with increasing disturbance"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 6.</b> Effect of sample quality on the CAUC stress–strain response, Lierstranda clay at 12.3 m depth. The block sample shows a pronounced peak at small strain; the piston samples show progressively altered responses. Redrawn after Karlsrud et al. (2005), after Lunne et al. (2002).</figcaption>
</figure>

Importantly, disturbance does not always simply reduce the measured peak strength. Changes in reconsolidation strain and void ratio can alter dilatancy and the effective stress path sufficiently that a disturbed specimen can sometimes produce an apparently high peak strength for the wrong physical reason.

The block samples therefore provide a much more reliable reference for establishing both:

$$
p'_c
$$

and

$$
s_{uc}.
$$

The 2005 study consequently used CAUC tests on very good to excellent block samples as the reference strength and oedometer tests as the reference for preconsolidation stress.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig02-oedometer-crs.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig02-oedometer-crs.png" style="max-width:640px;width:100%;height:auto;" alt="CRS oedometer test result on a block sample of Lierstranda clay, showing a well-defined preconsolidation stress"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 7.</b> CRS oedometer result on a block sample of Lierstranda clay (12.3 m depth), showing the well-defined preconsolidation stress used as the reference for OCR. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

This is the basis on which the CPTU correlations discussed below should be understood.

---

## 2. OCR from CPTU

### 2.1 CPTU quantities relevant to stress history

A CPTU sounding typically provides:

- cone resistance, $q_c$;
- pore pressure measured behind the cone shoulder, $u_2$;
- sleeve friction, $f_s$.

The measured cone resistance is corrected for unequal end-area effects as

$$
\boxed{
q_t=q_c+(1-a)u_2
}
$$

where $a$ is the cone area ratio.

The following quantities are particularly useful in clay:

$$
q_t-\sigma_{v0}
$$

which is the net cone resistance,

$$
\Delta u=u_2-u_0
$$

which is the penetration-induced excess pore pressure, and

$$
\sigma'_{v0}
$$

which is the initial vertical effective stress.

Two important normalized CPTU parameters are then

$$
\boxed{
Q_t=
\frac{q_t-\sigma_{v0}}
{\sigma'_{v0}}
}
$$

and

$$
\boxed{
B_q=
\frac{u_2-u_0}
{q_t-\sigma_{v0}}
}
$$

where $u_0$ is the in-situ hydrostatic pore pressure.

In the 1996 paper the normalized resistance was written as $Q$; the later paper uses $Q_t$. The underlying definition is essentially the same.

---

### 2.2 Why OCR affects CPTU response

Cone penetration induces very large strains around the cone. The measured response therefore depends on the strength, stiffness and pore-pressure generation characteristics of the clay.

An overconsolidated clay generally has a different:

- normalized strength;
- stiffness;
- contractive/dilative tendency;
- pore-pressure response;
- stress-strain behaviour

from a normally consolidated clay.

Consequently, $Q_t$, $B_q$ and normalized excess pore pressure contain information about stress history.

The important point is that these are **correlations with stress history**, not direct measurements of preconsolidation stress.

---

### 2.3 The early observation: geological history matters

The 1996 database showed that CPTU parameters did not collapse onto a unique OCR relationship. The data appeared to form different bands depending on how the apparent preconsolidation had developed.

Some level-ground clay deposits were interpreted as having developed apparent preconsolidation mainly through ageing or delayed consolidation. Other deposits had been genuinely unloaded through erosion or removal of overburden.

The resulting CPTU responses were different even when the conventional OCR parameter was similar.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-1996-figures/fig-q-ocr.png"><img src="/images/cpt101/su-of-clay/karlsrud-1996-figures/fig-q-ocr.png" style="max-width:640px;width:100%;height:auto;" alt="Normalised cone resistance Q plotted against OCR for the six 1996 block-sample sites, showing separate bands rather than a single trend"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 8.</b> Normalised cone resistance <i>Q</i> versus OCR for the 1996 block-sample sites. The data form bands depending on how the apparent preconsolidation developed, rather than collapsing onto a unique relationship. Redrawn after Karlsrud et al. (1996).</figcaption>
</figure>

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-1996-figures/fig-bq-ocr.png"><img src="/images/cpt101/su-of-clay/karlsrud-1996-figures/fig-bq-ocr.png" style="max-width:640px;width:100%;height:auto;" alt="Pore pressure ratio Bq plotted against OCR for the six 1996 block-sample sites"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 9.</b> Pore pressure ratio <i>B</i><sub>q</sub> versus OCR for the 1996 block-sample sites, showing the same site-dependent grouping. Redrawn after Karlsrud et al. (1996).</figcaption>
</figure>

The 1996 paper therefore made an important observation:

$$
\boxed{
\text{A universal CPTU--OCR correlation should not be expected for every geological setting.}
}
$$

This remains relevant even when applying the more explicit correlations proposed in 2005.

---

### 2.4 $Q_t$ as the preferred OCR indicator

The expanded 2005 database compared OCR with:

$$
B_q,
$$

$$
\frac{u_2-u_0}{\sigma'_{v0}},
$$

and

$$
Q_t.
$$

Among these parameters, the normalized cone resistance $Q_t$ gave the best overall correlation with measured OCR.

The proposed average correlations are:

#### Low-sensitivity clay, $S_t<15$

$$
\boxed{
OCR=
\left(
\frac{Q_t}{3}
\right)^{1.20}
}
$$

#### High-sensitivity clay, $S_t>15$

$$
\boxed{
OCR=
\left(
\frac{Q_t}{2}
\right)^{1.11}
}
$$

These expressions provide a practical way of generating a continuous first estimate of OCR from CPTU data.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig17-qt-ocr.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig17-qt-ocr.png" style="max-width:640px;width:100%;height:auto;" alt="Normalised cone resistance Qt plotted against OCR for the 2005 block-sample database, with separate trend curves for low- and high-sensitivity clays"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 10.</b> Normalised cone resistance <i>Q</i><sub>t</sub> versus OCR for the 2005 database, with separate trends for <i>S</i><sub>t</sub> &lt; 15 and <i>S</i><sub>t</sub> &gt; 15. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

---

### 2.5 Pore-pressure-based OCR indicators

The 2005 study also proposed relationships between OCR and $B_q$.

For low-sensitivity clay,

$$
\boxed{
B_q
=
0.88-0.51\log OCR
}
$$

and for high-sensitivity clay,

$$
\boxed{
B_q
=
1.15-0.67\log OCR.
}
$$

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig15-bq-ocr.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig15-bq-ocr.png" style="max-width:640px;width:100%;height:auto;" alt="Pore pressure ratio Bq plotted against OCR for the 2005 database, with linear-in-log-OCR trends for low- and high-sensitivity clays"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 11.</b> Pore pressure ratio <i>B</i><sub>q</sub> versus OCR with the proposed trends for low- and high-sensitivity clays. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

Similarly, the normalized excess pore pressure follows approximately:

#### $S_t<15$

$$
\boxed{
\frac{u_2-u_0}{\sigma'_{v0}}
=
2.4+8\log OCR
}
$$

#### $S_t>15$

$$
\boxed{
\frac{u_2-u_0}{\sigma'_{v0}}
=
2.5+6\log OCR
}
$$

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig16-du-ocr.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig16-du-ocr.png" style="max-width:640px;width:100%;height:auto;" alt="Normalised excess pore pressure plotted against OCR for the 2005 database, with trends for low- and high-sensitivity clays"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 12.</b> Normalised excess pore pressure (<i>u</i><sub>2</sub> − <i>u</i><sub>0</sub>)/<i>σ</i>′<sub>v0</sub> versus OCR with the proposed trends. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

These relationships can be used as checks on the $Q_t$-based estimate.

However, the scatter is significant. Even the preferred $Q_t$-OCR relationship is appreciably less precise than the CPTU correlations for undrained strength.

Therefore,

$$
\boxed{
\text{OCR from CPTU should be interpreted as an estimate rather than an exact measurement.}
}
$$

For important projects, high-quality oedometer data are still required to calibrate the absolute OCR level.

---

## 3. Undrained shear strength from CPTU

### 3.1 Three cone factors

The two papers discuss three principal cone factors for interpreting $s_{uc}$.

#### Net cone resistance factor

$$
\boxed{
N_{kt}
=
\frac{q_t-\sigma_{v0}}
{s_{uc}}
}
$$

which gives

$$
\boxed{
s_{uc}
=
\frac{q_t-\sigma_{v0}}
{N_{kt}}.
}
$$

#### Excess pore-pressure factor

$$
\boxed{
N_{\Delta u}
=
\frac{u_2-u_0}
{s_{uc}}
}
$$

which gives

$$
\boxed{
s_{uc}
=
\frac{u_2-u_0}
{N_{\Delta u}}.
}
$$

#### Effective cone-resistance factor

$$
\boxed{
N_{ke}
=
\frac{q_t-u_2}
{s_{uc}}
}
$$

which gives

$$
\boxed{
s_{uc}
=
\frac{q_t-u_2}
{N_{ke}}.
}
$$

The central question is therefore not whether CPTU can be correlated with strength, but **which measured response provides the most robust correlation and how the cone factor varies with the clay state**.

The 1996 study already demonstrated this variability by plotting the three cone factors against the pore pressure ratio $B_q$ for the block-sample sites. None of the factors is a constant; each varies systematically with the pore-pressure response of the clay.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-1996-figures/fig-ndu-bq.png"><img src="/images/cpt101/su-of-clay/karlsrud-1996-figures/fig-ndu-bq.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor N delta u plotted against pore pressure ratio Bq for the 1996 block-sample sites"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 13.</b> Cone factor <i>N</i><sub>Δu</sub> versus pore pressure ratio <i>B</i><sub>q</sub> from the 1996 block-sample study, with <i>s</i><sub>u</sub> from CAUC tests. Redrawn after Karlsrud et al. (1996).</figcaption>
</figure>

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-1996-figures/fig-nkt-bq.png"><img src="/images/cpt101/su-of-clay/karlsrud-1996-figures/fig-nkt-bq.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor Nkt plotted against pore pressure ratio Bq for the 1996 block-sample sites"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 14.</b> Cone factor <i>N</i><sub>kt</sub> versus pore pressure ratio <i>B</i><sub>q</sub> from the 1996 block-sample study. Redrawn after Karlsrud et al. (1996).</figcaption>
</figure>

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-1996-figures/fig-nke-bq.png"><img src="/images/cpt101/su-of-clay/karlsrud-1996-figures/fig-nke-bq.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor Nke plotted against pore pressure ratio Bq for the 1996 block-sample sites"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 15.</b> Cone factor <i>N</i><sub>ke</sub> versus pore pressure ratio <i>B</i><sub>q</sub> from the 1996 block-sample study. Redrawn after Karlsrud et al. (1996).</figcaption>
</figure>

---

### 3.2 The pore-pressure response gives the best strength correlation

The most important conclusion of the 2005 study is that the penetration-induced excess pore pressure provides the most consistent relationship with block-sample CAUC strength.

The proposed correlations for $N_{\Delta u}$ are:

#### Low-sensitivity clay, $S_t<15$

$$
\boxed{
N_{\Delta u}
=
6.9
-
4.0\log OCR
+
0.07I_p
}
$$

with $I_p$ expressed in percent.

Therefore,

$$
\boxed{
s_{uc}
=
\frac{u_2-u_0}
{6.9-4.0\log OCR+0.07I_p}
}
$$

#### High-sensitivity clay, $S_t>15$

$$
\boxed{
N_{\Delta u}
=
9.8
-
4.5\log OCR
}
$$

and

$$
\boxed{
s_{uc}
=
\frac{u_2-u_0}
{9.8-4.5\log OCR}.
}
$$

The observed scatter in calculated strength was approximately $\pm 10$–$15\%$ for these correlations.

The equations show explicitly that $N_{\Delta u}$ is not a universal constant. It depends on stress history and sensitivity, and for lower-sensitivity clays it also depends on plasticity.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig05-ndu-ocr.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig05-ndu-ocr.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor N delta u plotted against OCR for the 2005 database, with separate trends for low- and high-sensitivity clays"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 16.</b> Cone factor <i>N</i><sub>Δu</sub> versus OCR with the proposed correlations for low- and high-sensitivity clays. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig06-ndu-st.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig06-ndu-st.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor N delta u plotted against sensitivity, grouped by OCR class, with a step change around sensitivity 15"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 17.</b> Cone factor <i>N</i><sub>Δu</sub> versus sensitivity <i>S</i><sub>t</sub>, grouped by OCR class. The division at <i>S</i><sub>t</sub> = 15 separates the low- and high-sensitivity correlations. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig07-ndu-ip.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig07-ndu-ip.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor N delta u plotted against plasticity index, grouped by OCR class and sensitivity"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 18.</b> Cone factor <i>N</i><sub>Δu</sub> versus plasticity index <i>I</i><sub>p</sub>, grouped by OCR class and sensitivity. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

---

### 3.3 Why $u_2$ performs better than $q_t$

The improved performance of the pore-pressure-based correlation is supported by the comparison of different cone penetrometers at the Onsøy site.

The measured cone resistance $q_t$ showed a larger spread between different cone systems than the measured pore pressure $u_2$. In addition to instrumentation effects, $q_t$ may depend more strongly on details of the soil response such as:

- pre-peak stiffness;
- peak strength;
- post-peak softening;
- local deformation mechanism;
- anisotropy.

The pore-pressure response appears, for the clays in the database, to provide a more stable indicator of the strength mobilized around the cone.

This leads to an important practical conclusion:

$$
\boxed{
s_{uc}\text{ from }N_{\Delta u}
\text{ should generally receive more weight than }
s_{uc}\text{ from }N_{kt}.
}
$$

**The advantage only holds if the CPTU pore-pressure system is properly saturated and functioning reliably.**

In reality, this condition is far from guaranteed. The measured pore pressure can depend strongly on the device and on the soil itself: filter location and saturation, the saturation fluid, temperature effects, and desaturation or gas in stiff, dilative or partially drained soils can all distort the measured $u_2$. As a consequence, the pore-pressure response does not always give a good prediction of soil strength, and the $N_{\Delta u}$ approach is not routinely used in practice. The net-cone-resistance interpretation through $N_{kt}$ remains the default in most projects, with the pore-pressure-based estimate serving as a valuable complement where the quality of the $u_2$ measurement can be demonstrated.

---

### 3.4 Strength from net cone resistance

For the conventional net cone resistance approach, Karlsrud et al. (2005) proposed:

#### Low-sensitivity clay, $S_t<15$

$$
\boxed{
N_{kt}
=
7.8
+
2.5\log OCR
+
0.082I_p
}
$$

#### High-sensitivity clay, $S_t>15$

$$
\boxed{
N_{kt}
=
8.5
+
2.5\log OCR.
}
$$

The compression strength is then

$$
\boxed{
s_{uc}
=
\frac{q_t-\sigma_{v0}}
{N_{kt}}.
}
$$

The scatter is larger than for $N_{\Delta u}$. The 2005 paper reports uncertainties of approximately:

$$
\pm30\%
$$

for the low-sensitivity clays and roughly

$$
\pm15\%
$$

for the high-sensitivity clays in the database.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig08-nkt-ocr.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig08-nkt-ocr.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor Nkt plotted against OCR for the 2005 database, with separate trends for low- and high-sensitivity clays"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 19.</b> Cone factor <i>N</i><sub>kt</sub> versus OCR with the proposed correlations. Note the larger scatter compared with <i>N</i><sub>Δu</sub> (Figure 16). Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig09-nkt-st.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig09-nkt-st.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor Nkt plotted against sensitivity, grouped by OCR class"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 20.</b> Cone factor <i>N</i><sub>kt</sub> versus sensitivity <i>S</i><sub>t</sub>, grouped by OCR class. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig10-nkt-ip.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig10-nkt-ip.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor Nkt plotted against plasticity index, grouped by OCR class and sensitivity"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 21.</b> Cone factor <i>N</i><sub>kt</sub> versus plasticity index <i>I</i><sub>p</sub>, grouped by OCR class and sensitivity. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

The Oslo harbour data also suggested a possible depth dependency in $N_{kt}$. In an essentially normally consolidated deposit, the strength derived from $N_{\Delta u}$ increased approximately linearly with depth, whereas the $N_{kt}$-based profile showed a systematic relative shift with depth.

The authors did not establish whether this was a general phenomenon. It should therefore be viewed as an observation requiring further study rather than a universal correction.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig11-bjorvika-profiles.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig11-bjorvika-profiles.png" style="max-width:640px;width:100%;height:auto;" alt="Undrained strength profiles versus elevation from 35 CPTUs at Bjørvika, Oslo harbour, comparing interpretations based on N delta u and Nkt"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 22.</b> Interpreted strength profiles (min / average / max) from 35 CPTUs at Bjørvika, Oslo harbour. The <i>N</i><sub>Δu</sub>-based strength increases approximately linearly with depth, whereas the <i>N</i><sub>kt</sub>-based profile shows a systematic relative shift. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

To quantify the systematic difference between the two profiles in Figure 22, Karlsrud et al. (2005) introduced a depth correction factor $I_z$, applied to the strength derived from $N_{kt}$ to try to match the strength derived from $N_{\Delta u}$. It is defined by the expression

$$
\boxed{
\left(s_{uc}\right)_{N_{kt}}
=
I_z
\left(s_{uc}\right)_{N_{\Delta u}}
}
$$

so that $I_z$ is the ratio between the $N_{kt}$-based and the $N_{\Delta u}$-based strength estimates at a given depth. At Bjørvika, $I_z$ is larger than unity at shallow depth, where the $N_{kt}$-based strength is comparatively high, and decreases with depth as the $N_{kt}$-based profile falls off relative to the $N_{\Delta u}$-based one. The fitted variation with depth is shown in Figure 23.

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig12-depth-factor.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig12-depth-factor.png" style="max-width:640px;width:100%;height:auto;" alt="Empirical depth factor for the Nkt interpretation plotted against depth, with the curve fit and the measured Bjørvika data"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 23.</b> Tentative depth factor <i>I</i><sub>z</sub> for the <i>N</i><sub>kt</sub> interpretation, fitted to the Bjørvika data. This remains an observation requiring further study rather than a universal correction. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

---

### 3.5 Effective cone-resistance factor $N_{ke}$

The third interpretation combines corrected cone resistance and measured pore pressure:

$$
N_{ke}
=
\frac{q_t-u_2}
{s_{uc}}.
$$

Karlsrud et al. (2005) found that $N_{ke}$ correlated reasonably with $B_q$, giving:

#### $S_t<15$

$$
\boxed{
N_{ke}
=
11.5-9.05B_q
}
$$

#### $S_t>15$

$$
\boxed{
N_{ke}
=
12.5-11.0B_q
}
$$

with

$$
\boxed{
N_{ke}\ge2.0.
}
$$

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig13-nke-ocr.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig13-nke-ocr.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor Nke plotted against OCR for the 2005 database"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 24.</b> Cone factor <i>N</i><sub>ke</sub> versus OCR for the 2005 database. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

<figure style="text-align:center;">
  <a href="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig14-nke-bq.png"><img src="/images/cpt101/su-of-clay/karlsrud-2005-figures/fig14-nke-bq.png" style="max-width:640px;width:100%;height:auto;" alt="Cone factor Nke plotted against pore pressure ratio Bq for the 2005 database, with the proposed linear relationships for low- and high-sensitivity clays"></a>
  <figcaption style="font-size:0.85em;"><b>Figure 25.</b> Cone factor <i>N</i><sub>ke</sub> versus pore pressure ratio <i>B</i><sub>q</sub> with the proposed relationships for <i>S</i><sub>t</sub> &lt; 15 and <i>S</i><sub>t</sub> &gt; 15. Compare with the 1996 version in Figure 15. Redrawn after Karlsrud et al. (2005).</figcaption>
</figure>

An advantage of this approach is that no separate OCR estimate is required.

However, the method should be applied cautiously when

$$
B_q<0.6
$$

because relatively little calibration data were available in that range. At high $B_q$, the relative uncertainty in the resulting strength also becomes large.

The 2005 paper therefore places $N_{ke}$ between $N_{\Delta u}$ and $N_{kt}$ in terms of reliability.

---

### 3.6 Recommended use of the three strength estimates

The most useful interpretation is not to select one equation and ignore the remaining CPTU measurements. Instead, the three strength estimates should be compared.

The preferred estimate is

$$
\boxed{
s_{uc}^{(\Delta u)}
=
\frac{u_2-u_0}
{N_{\Delta u}}.
}
$$

Independent checks can then be obtained from

$$
s_{uc}^{(q_t)}
=
\frac{q_t-\sigma_{v0}}
{N_{kt}}
$$

and

$$
s_{uc}^{(q_t-u_2)}
=
\frac{q_t-u_2}
{N_{ke}}.
$$

Agreement between the three estimates increases confidence in the interpretation.

Disagreement is also informative. For example, a significantly low value derived from $N_{\Delta u}$ relative to the resistance-based estimates may indicate inadequate saturation of the pore-pressure measurement system. The Bjørvika profiles in Figure 22 illustrate this kind of side-by-side comparison for the $N_{\Delta u}$- and $N_{kt}$-based estimates.

---

## 4. Coupling OCR and $s_u$ in CPTU interpretation

An interesting feature of the Karlsrud framework is that OCR and $s_{uc}$ are not completely independent interpretation problems.

The CPTU provides an estimate of OCR:

$$
Q_t
\rightarrow OCR,
$$

while OCR is then used to select the appropriate cone factor:

$$
OCR
\rightarrow N_{\Delta u},
$$

which gives

$$
N_{\Delta u}
\rightarrow s_{uc}.
$$

At the same time, the normalized strength

$$
\frac{s_{uc}}{\sigma'_{v0}}
$$

contains information about the likely stress history.

This makes an iterative interpretation possible:

$$
\boxed{
Q_t
\rightarrow
OCR
\rightarrow
N_{\Delta u}
\rightarrow
s_{uc}
\rightarrow
\frac{s_{uc}}{\sigma'_{v0}}
\rightarrow
\text{check OCR}
}
$$

Karlsrud et al. (2005) suggest that an initial OCR estimate may be obtained from geological history or CPTU. The corresponding $N_{\Delta u}$ gives a first estimate of $s_{uc}$. The normalized strength can then be checked against the expected OCR-strength relationship, and the procedure repeated if necessary.

Usually only one or two iterations are required.

This procedure is preferable to treating all CPTU correlations as independent empirical equations because it forces the interpreted stress history and strength profile to remain mechanically compatible.

---

## 5. Practical interpretation workflow

A practical interpretation of clay from CPTU can be summarized as follows:

| Stage | Calculation | Purpose |
|---|---|---|
| 1 | $q_t=q_c+(1-a)u_2$ | Correct measured cone resistance |
| 2 | Establish $\sigma_{v0}$, $\sigma'_{v0}$, and $u_0$ | Define the in-situ stress state |
| 3 | $B_q=(u_2-u_0)/(q_t-\sigma_{v0})$ | Characterize pore-pressure response |
| 4 | $Q_t=(q_t-\sigma_{v0})/\sigma'_{v0}$ | Normalize cone resistance |
| 5 | Estimate $OCR$ primarily from $Q_t$ | Obtain a continuous stress-history profile |
| 6 | Select $N_{\Delta u}$ from OCR, $S_t$, and $I_p$ | Main strength correlation |
| 7 | $s_{uc}=(u_2-u_0)/N_{\Delta u}$ | Preferred estimate of CAUC compression strength |
| 8 | Calculate $s_{uc}$ independently from $N_{kt}$ | First consistency check |
| 9 | Calculate $s_{uc}$ independently from $N_{ke}$ | Second consistency check |
| 10 | Compare with high-quality laboratory tests | Site-specific calibration |
| 11 | Convert $s_{uc}$ to appropriate anisotropic design strengths | Apply the interpretation to the actual failure mechanism |

The final step is essential. The direct output of the correlations is primarily

$$
\boxed{
s_{uc,\mathrm{CAUC}}
}
$$

rather than a universal design value of $s_u$.

---

## 6. Interpretation limits

The correlations should be used with several limitations in mind.

First, the database is dominated by Norwegian marine clays, together with the Bothkennar clay from the UK. Mineralogy, geological history and structure may be substantially different in other deposits.

Second, sensitivity strongly influences several of the proposed relationships. A correct assessment of whether the clay belongs to the low- or high-sensitivity group is therefore important.

Third, reliable measurement of $u_2$ requires a well-saturated pore-pressure system. The strongest correlation in the framework, $N_{\Delta u}$, is also the one most directly affected by poor filter saturation.

Fourth, the correlations represent **peak CAUC compression strength from high-quality block samples**. They should not be confused with remoulded strength, DSS strength, extension strength, residual strength, or a generic isotropic shear strength.

Fifth, the CPTU-derived OCR profile should be treated as a stress-history interpretation rather than a direct measurement of $p'_c$. For major projects, oedometer tests on high-quality samples remain important.

Finally, the two papers themselves emphasize the value of local calibration. Even in Norwegian practice, block sampling was recommended for important projects to verify the applicability of the CPTU correlations for the particular soil and cone equipment.

---

## 7. Conclusions

The main lesson from the two Karlsrud studies is that CPTU interpretation in clay should begin with an understanding of the clay itself rather than with a fixed cone factor.

Undrained shear strength is controlled by stress history, anisotropy, sensitivity, plasticity and natural structure. OCR is an important descriptor of this state, but natural clays do not exhibit a unique relationship between $s_u/\sigma'_{v0}$ and OCR because geological processes such as ageing, bonding, cementation and leaching also influence the soil.

Within the investigated database, the normalized cone resistance

$$
Q_t=
\frac{q_t-\sigma_{v0}}
{\sigma'_{v0}}
$$

provides the most useful CPTU indicator of OCR, although the scatter remains significant.

For undrained compression strength, the excess pore-pressure response is particularly valuable. The correlation

$$
\boxed{
s_{uc}
=
\frac{u_2-u_0}
{N_{\Delta u}}
}
$$

was substantially more consistent than the conventional net-cone-resistance interpretation, provided that OCR, sensitivity and plasticity were appropriately considered.

The most robust practical interpretation is therefore not simply

$$
\boxed{
CPTU\rightarrow s_u
}
$$

but

$$
\boxed{
\text{CPTU}
\rightarrow
\text{stress history}
\rightarrow
s_{uc}
\rightarrow
\text{anisotropic design strength}
}
$$

with independent checks using all available CPTU measurements and calibration against high-quality laboratory data wherever possible.

---

## References

Andersen, K. H., Kleven, A. & Heien, D. (1988). **Cyclic soil data for design of gravity structures**. Journal of Geotechnical Engineering, ASCE, 114(5).

Gu, C., Wang, J., Cai, Y., Sun, L., Wang, P. & Dong, Q. Y. (2016). **Deformation characteristics of overconsolidated clay sheared under constant and variable confining pressure**. Soils and Foundations, 56(3), 427–439. <https://doi.org/10.1016/j.sandf.2016.04.009>

Karlsrud, K., Lunne, T. & Brattlien, K. (1996). **Improved CPTU interpretations based on block samples**.

Karlsrud, K., Lunne, T., Kort, D. A. & Strandvik, S. (2005). **CPTU Correlations for Clays**.

Ladd, C. C. et al. (1977). SHANSEP framework for the stress-history-normalized behavior of cohesive soils. Cited and discussed by Karlsrud et al. (2005).

