---
title: "Interpreting the CPT: From Measurements to Soil Properties"
excerpt: "What q_c, f_s and u_2 tell you — soil behaviour type, strength, stiffness, and consolidation properties from the three channels of a piezocone."
collection: cpt101
order: 2
---

A modern piezocone measures three things continuously with depth: cone resistance q<sub>c</sub>, sleeve friction f<sub>s</sub>, and pore pressure u₂. Almost everything else is interpretation.

## The basic corrections and normalised parameters

* **Corrected cone resistance:** q<sub>t</sub> = q<sub>c</sub> + (1 − a)·u₂ — the unequal-area correction, essential in clays.
* **Normalised parameters:** Q<sub>t</sub> (normalised cone resistance), F<sub>r</sub> (normalised friction ratio), and B<sub>q</sub> (pore pressure ratio) remove the effect of overburden stress and are the axes of modern interpretation charts.

## Soil behaviour type

The CPT does not sample — it classifies soils by how they *behave* during penetration. Robertson's soil behaviour type (SBT) charts, in their normalised form (SBTn), map Q<sub>t</sub>–F<sub>r</sub> space into zones from sensitive clays to gravelly sands, and the continuous index I<sub>c</sub> allows automated stratigraphy from any sounding.

## Soil properties — the classical correlations

* **Sands (drained penetration):** relative density D<sub>r</sub> from calibration-chamber correlations (Baldi, Jamiolkowski and co-workers); peak friction angle; state parameter approaches for a more fundamental description.
* **Clays (undrained penetration):** undrained shear strength s<sub>u</sub> = (q<sub>t</sub> − σ<sub>v0</sub>)/N<sub>kt</sub>, with the cone factor N<sub>kt</sub> typically 10–20 and best calibrated locally; preconsolidation and OCR from normalised resistance; sensitivity from the friction ratio.
* **Stiffness:** small-strain shear modulus G₀ directly from shear-wave velocity when a seismic cone is used, or via correlations otherwise.
* **Consolidation:** the coefficient of consolidation c<sub>h</sub> from piezocone dissipation tests (t₅₀ method, Teh & Houlsby).
* **Drainage conditions:** the normalised penetration velocity V = vd/c<sub>v</sub> indicates whether penetration is drained, undrained, or partial — a topic that connects directly to [centrifuge scaling](/centrifuge-101/02-scaling-laws/) and to intermediate soils where standard correlations need care.

## In-depth articles

Each soil parameter deserves more than a paragraph. This series works through the interpretation methods one parameter at a time — the equations, the calibration data behind them, and the pitfalls:

{% include series-list.html collection="cpt101" parent="interpretation" %}

*Planned articles: relative density of sand, OCR and preconsolidation, K₀, friction angle, small-strain stiffness, consolidation coefficient from dissipation tests — and interpretation in problematic soils such as glauconitic sands (a core theme of the [PIGS](/portfolio/pigs/) JIP).*
