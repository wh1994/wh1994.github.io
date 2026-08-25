---
title: "Why CPTU Data Must Be Corrected for Pore Pressure — and What Filter Location, Saturation and Resolution Do to Your Measurements"
excerpt: "The unequal-area correction, filter location, saturation and sensor resolution — the practical measurement issues that decide whether soft-clay CPTU data are usable, with a worked example of what skipping the correction does to interpreted strength."
collection: cpt101
parent: interpretation
order: 2
toc: true
toc_sticky: true
---

*Part of the [CPT interpretation series](/cpt-101/02-interpretation/).*


The piezocone gives us three continuous signals — cone resistance $q_c$,
sleeve friction $f_s$ and pore pressure $u_2$ — and in soft clay all three
are small numbers measured by a tool designed to survive hard ground. That
combination is unforgiving: effects that would disappear in sand (a few tens
of kPa of water pressure — the unequal-area effect; a warm morning — the
temperature effect; a coarse load cell — sensor resolution) become
first-order errors in clay. This article walks through the main effects and
ends with a worked example showing what happens to interpreted undrained
strength when the most important correction is skipped.

## 1. The unequal-area effect: why $q_c$ is not the true tip resistance

A cone penetrometer is not a solid spear. Behind the conical tip there is a
groove (where the $u_2$ filter sits) and the shaft continues at a smaller
cross-section $A_n$ than the full cone base area $A_c$. Water pressure acting
in that groove pushes on the exposed shoulder annulus, so part of the true
tip stress never reaches the load cell:

$$q_t = q_c + (1-a)\,u_2, \qquad a = A_n / A_c$$

The friction sleeve has end areas too ($A_{sb}$, $A_{st}$), so the measured
sleeve friction is biased in the same way:

$$f_t = f_s - \frac{u_2 A_{sb} - u_3 A_{st}}{A_s}$$

<figure style="margin:2.2em auto; max-width:460px; text-align:center;">
  <img src="/images/cpt101/pore-pressure-correction/fig-3-01-pore-pressure-areas.png" alt="Schematic of the penetrometer geometry showing where u2 and u3 act and the areas Ac, An, As, Asb and Ast" style="width:100%; height:auto;">
  <figcaption style="font-size:0.88em; color:#6b6a66; margin-top:0.5em; text-align:left;"><strong>Figure 1.</strong> Where the water pushes on the penetrometer. Unequal end areas make the measured <em>q</em><sub>c</sub> and <em>f</em><sub>s</sub> pressure-dependent.</figcaption>
</figure>

The net area ratio $a$ is a property of each individual cone. It is measured
by pressurizing the suspended penetrometer in a calibration vessel: the slope
of measured $q_c$ against applied water pressure is $a$ directly. Commercial
cones typically fall between 0.55 and 0.9, and values as low as 0.38 exist —
a cone that reports barely a third of the water pressure it should feel as
tip stress.

<figure style="margin:2.2em auto; max-width:620px; text-align:center;">
  <img src="/images/cpt101/pore-pressure-correction/fig-3-02-area-ratio-calibration.png" alt="Measured qc versus applied water pressure for two piezocones, with slopes a = 0.84 and a = 0.38" style="width:100%; height:auto;">
  <figcaption style="font-size:0.88em; color:#6b6a66; margin-top:0.5em; text-align:left;"><strong>Figure 2.</strong> Calibration-vessel test: the slope of <em>q</em><sub>c</sub> vs applied pressure is the area ratio <em>a</em>. Redrawn from Lunne et al. (1997), Fig. 3.2, after Battaglio & Maniscalco (1983).</figcaption>
</figure>

How much this matters is best shown by running two very different cones in
the same soft clay. In the classic comparison by Aas et al. (1984), cones
with $a$ = 0.38 and $a$ = 0.86 disagree on $q_c$ by roughly a factor of 1.5 —
and collapse onto a single profile once each is corrected to $q_t$ with its
own area ratio:

<figure style="margin:2.2em auto; max-width:720px; text-align:center;">
  <img src="/images/cpt101/pore-pressure-correction/fig-3-03b-qc-correction-aas.png" alt="Two cones with area ratios 0.38 and 0.86: measured qc and u2 differ strongly, corrected qt profiles coincide" style="width:100%; height:auto;">
  <figcaption style="font-size:0.88em; color:#6b6a66; margin-top:0.5em; text-align:left;"><strong>Figure 3.</strong> Two very different cones, one <em>q</em><sub>t</sub> profile. Redrawn from Lunne et al. (1997), Fig. 3.3b, after Aas et al. (1984).</figcaption>
</figure>

Two practical consequences:

- **In soft, fine-grained soil the correction is mandatory.** $u_2$ can be of
  the same order as $q_c$ (in the example below it exceeds half of $q_c$), so
  uncorrected data are not comparable between cones, and not usable for
  quantitative interpretation.
- **Prefer cones with a high area ratio.** When $a$ is small the correction
  becomes the dominant term in $q_t$, and its uncertainty dominates too.

## 2. Filter location: $u_1$, $u_2$ and $u_3$ are different measurements

Pore pressure around an advancing cone is anything but uniform. It peaks on
the cone face where normal stresses are highest, then drops sharply just
behind the shoulder, where the soil is unloaded and sheared along the shaft.
How sharply it drops depends on the soil: contractive, normally consolidated
clays keep large positive pressures along the shaft, while dilative soils —
dense silts, heavily overconsolidated clays — can drop to hydrostatic or even
negative values a few millimetres behind the tip:

<figure style="margin:2.2em auto; max-width:860px; text-align:center;">
  <img src="/images/cpt101/pore-pressure-correction/fig-pore-pressure-distributions.png" alt="Normalized pore pressure u/u0 along the penetrometer for clays (top) and silts and sands (bottom)" style="width:100%; height:auto;">
  <figcaption style="font-size:0.88em; color:#6b6a66; margin-top:0.5em; text-align:left;"><strong>Figure 4.</strong> Measured pore-pressure distributions along the penetrometer: clays (top) and silts/sands (bottom). Dilative, heavily OC and dense soils collapse behind the shoulder, while cementation (Taranto clay) keeps <em>u</em> high along the whole shaft. Data digitized from Robertson et al. (1986), updated compilation.</figcaption>
</figure>

The contrast between clay types shows up directly in the field records. In a
lightly overconsolidated clay the ordering $u_1 \approx u_{tip} > u_2 > u_3$
holds through the whole profile; in a heavily overconsolidated clay the cone
face still generates large positive pressures, but the shaft positions
measure almost nothing, or slightly negative values. A similar contrast is observed in sands. Loose sand tends to exhibit a pore-pressure distribution resembling that of normally consolidated or lightly overconsolidated clay, with predominantly positive excess pore pressures around the cone and shaft. Dense sand, by contrast, behaves more like highly overconsolidated clay: positive pore pressures may develop immediately in front of the cone, while the strongly dilative response around and behind the shoulder can produce very small or negative pore pressures at the shaft locations. Thus, despite the fundamental differences between clay and sand, the spatial pattern of pore pressure around the cone reflects a common transition from predominantly contractive behaviour in loose or lightly overconsolidated soils to increasingly dilative behaviour in dense or highly overconsolidated soils.

The $u_2$ position (immediately behind the cone) is the reference location,
and for good reasons: the filter is protected from wear, less affected by
element compressibility, and — decisively — it measures the pressure exactly
where the unequal-area correction needs it. But the flip side follows from
the figures above: in heavily OC clays $u_2$ is small or negative, thin
layers are better resolved by other positions, and a proper $f_s$ correction
would need $u_3$ as well. Dual- or triple-element piezocones exist precisely
because no single filter position tells the whole story.

## 3. Saturation: a filter with gas in it is a low-pass filter

The pore-pressure system only responds quickly if the filter and cavity are
fully saturated with de-aired fluid. Any gas makes the system compressible:
the response becomes sluggish, thin layers vanish, and the profile shows
step-like plateaus instead of sharp excursions. The three panels below are
the same soft-clay site with poorly, partly and well saturated systems — only
the right-hand one can support layer detection or dissipation testing:

<figure style="margin:2.2em auto; max-width:860px; text-align:center;">
  <img src="/images/cpt101/pore-pressure-correction/fig-3-10-saturation.png" alt="Three u2 profiles at the same site: step-like poorly saturated, damped partly saturated, crisp well saturated" style="width:100%; height:auto;">
  <figcaption style="font-size:0.88em; color:#6b6a66; margin-top:0.5em; text-align:left;"><strong>Figure 5.</strong> Saturation of the pore-pressure system decides data quality. Redrawn from Lunne et al. (1997), Fig. 3.10.</figcaption>
</figure>

Poor saturation damages more than the $u_2$ channel itself: since $q_t$ is
computed from $u_2$, a lagging pore-pressure reading quietly corrupts the
corrected cone resistance too.

## 4. Resolution: the load cell must match the soil

Cone load cells are usually dimensioned for sand and gravel. Used in a soft
clay, a high-capacity cell operates at the bottom few percent of its range,
where electrical noise and zero-drift are comparable to the signal itself.
The result reads like a highly variable deposit — variability that is
entirely instrumental:

<figure style="margin:2.2em auto; max-width:780px; text-align:center;">
  <img src="/images/cpt101/pore-pressure-correction/fig-3-13-resolution.png" alt="Noisy qc and u profiles from a high-capacity load cell next to clean profiles from a matched load cell" style="width:100%; height:auto;">
  <figcaption style="font-size:0.88em; color:#6b6a66; margin-top:0.5em; text-align:left;"><strong>Figure 6.</strong> Same soft-clay site, two load cells: electrical noise on a high-capacity cell reads as soil variability. Redrawn from Lunne et al. (1997), Fig. 3.13, after Powell & Quarterman (1995).</figcaption>
</figure>

The same logic applies to temperature: zero readings taken at surface
temperature and used in colder ground shift the whole $q_c$ profile, by
amounts that matter when $q_c$ itself is only a few hundred kPa (Lunne et
al. 1986a). Soft-soil profiling calls for low-capacity (or well-compensated)
load cells, zero readings at ground temperature, and calibration over the
stress range actually expected.

## 5. Worked example: what the correction does to interpreted clay strength

Here is a typical soft-clay CPTU record:
15 m of data at 2 cm spacing, $q_c$ rising to ~0.6 MPa, $f_s$ of only
4–10 kPa, and $u_2$ climbing steadily to ~0.45 MPa — i.e. the water pressure
reaches about 70 % of the measured cone resistance. The cone's area ratio is
$a$ = 0.75. Figure 7 shows the measured $q_c$ and $u_2$, with the corrected
$q_t = q_c + (1-a)u_2$ overlaid on the $q_c$ panel; the shaded band is the
correction:

<figure style="margin:2.2em auto; max-width:780px; text-align:center;">
  <img src="/images/cpt101/pore-pressure-correction/fig-cpt-example.png" alt="Example CPTU record: qc with qt overlay and u2 versus depth" style="width:100%; height:auto;">
  <figcaption style="font-size:0.88em; color:#6b6a66; margin-top:0.5em; text-align:left;"><strong>Figure 7.</strong> The example sounding: measured <em>q</em><sub>c</sub> and <em>u</em><sub>2</sub>, with <em>q</em><sub>t</sub> (<em>a</em> = 0.75) overlaid. The shaded band — the correction — reaches ~20 % of <em>q</em><sub>c</sub> at depth.</figcaption>
</figure>

Now interpret undrained shear strength the standard way,

$$s_u = \frac{q_t - \sigma_{v0}}{N_{kt}}$$

with $N_{kt}$ = 15 and $\sigma_{v0}$ from an assumed bulk unit weight of
17 kN/m³ — once done correctly with $q_t$, and once (wrongly) with raw
$q_c$:

<figure style="margin:2.2em auto; max-width:760px; text-align:center;">
  <img src="/images/cpt101/pore-pressure-correction/fig-su-comparison.png" alt="Undrained shear strength interpreted from qt and from raw qc, and the percentage underestimation versus depth" style="width:100%; height:auto;">
  <figcaption style="font-size:0.88em; color:#6b6a66; margin-top:0.5em; text-align:left;"><strong>Figure 8.</strong> Undrained strength with and without the pore-pressure correction (<em>N</em><sub>kt</sub> = 15). The underestimate grows with depth as <em>u</em><sub>2</sub> outpaces <em>q</em><sub>c</sub>.</figcaption>
</figure>

The error is not a constant offset — it grows with depth, because $u_2$
increases faster than the net cone resistance:

| Depth | $s_u$ from $q_t$ | $s_u$ from raw $q_c$ | underestimate |
| --- | --- | --- | --- |
| 5 m | 11.4 kPa | 9.1 kPa | 21 % |
| 10 m | 20.7 kPa | 16.1 kPa | 22 % |
| 15 m | 29.1 kPa | 21.6 kPa | 26 % |

A fifth to a quarter of the clay's strength disappears if the correction is
skipped — with a cone of perfectly ordinary area ratio ($a$ = 0.75). With a
low-ratio cone ($a$ ≈ 0.4) the same sounding would lose closer to half. And
because the error masquerades as a plausible-looking profile, nothing about
the uncorrected curve warns you that it is wrong: it is smooth, it increases
with depth, and it is 25 % unsafe in the other direction for anyone
back-calculating $N_{kt}$ from it.

## Takeaways

1. **Always correct $q_c$ to $q_t$ in fine-grained soils.** The unequal-area
   effect is not noise; in soft clay it is a 20–50 % systematic bias, and it
   propagates one-for-one into $s_u$, OCR and every other derived parameter.
2. **Know your cone.** $a$ comes from a calibration vessel, not a datasheet
   default; low-$a$ cones amplify the correction and its uncertainty.
3. **Filter position is part of the measurement's identity.** $u_1$, $u_2$
   and $u_3$ differ systematically, and the difference itself is diagnostic
   (large $u_1$ with near-zero $u_2$ = heavily OC / dilative behaviour).
   Report which position was used; use $u_2$ for the correction.
4. **Saturate, and verify saturation.** A sluggish, step-like $u_2$ profile
   invalidates both the pore-pressure record and the $q_t$ computed from it.
5. **Match the sensors to the soil.** Load-cell capacity, temperature zeroing
   and system resolution set a noise floor that soft-clay signals can easily
   fall below.

## References

- Lunne, T., Robertson, P.K. & Powell, J.J.M. (1997). *Cone Penetration
  Testing in Geotechnical Practice*, Section 3.1. Blackie Academic &
  Professional.
- Aas, G., Lacasse, S., Lunne, T. & Madshus, C. (1984). In situ testing: new
  developments. *Nordiska Geotekniker-mötet, NGM-84*, Linköping, Sweden, 2,
  705–716. Swedish Geotechnical Society.
- Battaglio, M. & Maniscalco, R. (1983). Il piezocono: esecuzione ed
  interpretazione. *Politecnico di Torino*.
- Bruzzi, D. & Battaglio, M. (1987). Pore pressure measurements during cone
  penetration tests. *ISMES*.
- Lunne, T., Eidsmoen, T., Gillespie, D. & Howland, J. (1986a). Laboratory
  and field evaluation of cone penetrometers. *Proc. In Situ '86*, ASCE.
- Powell, J.J.M. & Quarterman, R.S.T. (1991/1995). Piezocone studies at
  Bothkennar and in soft clays.
- Robertson, P.K., Campanella, R.G., Gillespie, D. & Greig, J. (1986). Use of
  piezometer cone data. *Proc. In Situ '86*, ASCE.
- Skomedal, E. & Lunne, T. (1987). Application of new methods of offshore
  site investigation, Gullfaks C.
- Whittle, A.J. & Aubeny, C.P. (1991). Pore pressure fields around
  piezocone penetrometers installed in clays. *Proc. IACMAG '91*.
