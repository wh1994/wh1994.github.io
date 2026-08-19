---
title: "Bright Spark Lecture at ICPMG 2026: Physical Modelling of Monopiles in Sand"
date: 2026-08-19
permalink: /posts/2026/08/bright-spark-lecture-icpmg2026/
excerpt: "The video of my Bright Spark Lecture at the 11th ICPMG in Zurich is now online — a generalized scaling law for laterally loaded monopiles in sand, and what a unique MIDAS centrifuge dataset tells us about long-term cyclic response."
tags:
  - news
  - offshore wind
  - monopile
  - centrifuge modelling
  - ICPMG
---

This June I had the honour of delivering a **Bright Spark Lecture** at the 11th International Conference on Physical Modelling in Geotechnics ([ICPMG 2026](https://icpmg2026.ethz.ch/), 8–12 June 2026, Zurich). The recording is now available, and I am happy to share it here.

<div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;max-width:720px;margin:1em auto;">
  <iframe src="https://www.youtube-nocookie.com/embed/XDLxX0MG4E0" title="Bright Spark Lecture — Physical modelling of monopiles in sand" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

The lecture, *Physical modelling of monopiles in sand: a generalized scaling law and long-term cyclic response*, brings together two threads of my recent work on offshore wind monopile foundations.

## 1. A generalized scaling law for laterally loaded monopiles

Centrifuge datasets on monopiles in sand are fragmented: different programmes use different pile geometries, loading eccentricities, stress levels and interpretation methods, which makes direct comparison difficult. The first part of the lecture presents a mechanism-based scaling law that links each monopile to an **equivalent rigid-pile twin** rotating about a centre located approximately 0.75L below the seabed.

Moment equilibrium about the rotation centre gives the normalized resistance $H(h+0.75L)/(DL^3\gamma')$, stress-dependent sand stiffness is captured by normalizing the rigid-pile rotation by $(L\gamma'/p_a)^{0.5}$, and the additional bending of non-rigid piles is estimated with a soil-restrained cantilever correction. The response is thereby decomposed into a soil-controlled rigid-body component and a structure-controlled bending component.

Validated against monotonic centrifuge tests from the MIDAS programme at Deltares and independent literature datasets, the framework collapses responses across different diameters, embedment ratios, g-levels and testing conditions into a narrow band — a practical tool for test planning, synthesis of fragmented databases and first-order prediction.

## 2. Long-term cyclic response from the MIDAS centrifuge dataset

> **Note.** The recorded lecture above covers the first contribution — the generalized scaling law. This second part is not included in the video; it is presented in detail in the accompanying journal paper.

The second part interprets a unique MIDAS cyclic centrifuge dataset from TU Delft: 2 monotonic repeat tests and 21 cyclic tests at 100g on the same model pile in dry dense Geba sand, covering cyclic load amplitude, cyclic load ratio, loading sequence and monotonic preloading. The headline observations:

- Rotation accumulates rapidly during early cycles and then approaches a stable or quasi-stable state.
- Cyclic load amplitude is the dominant first-order control — but the normalized trends differ markedly from empirical models calibrated on 1g tests.
- The cyclic load ratio has a **non-monotonic** effect, because increasing it raises the mean load while reducing the cyclic load range.
- Loading sequence matters: ascending load packages produced the smallest final rotation, severe early packages the largest — so cyclic accumulation is only partly compatible with Miner's superposition.
- Loading–unloading stiffness remains relatively stable, with temporary reductions at high mean load that recover when the mean load is reduced.

Together, the two contributions argue for **stress-correct physical modelling** as the basis for cyclic monopile design, database synthesis and model validation.

## Extended abstract and related publications

The two-page extended abstract from the conference proceedings is available here: [Physical modelling of monopiles in sand: a generalized scaling law and long-term cyclic response (PDF)](/files/Wang-2026-ICPMG-Bright-Spark-Lecture-extended-abstract.pdf).

The underlying work is described in detail in the papers below — see my [publications](/publications/) page for the full list:

- Wang, H., Lehane, B. M., Bransby, M. F., Wang, L. Z. & Hong, Y. (2022). "Field and numerical study of the lateral response of rigid piles in sand." *Acta Geotechnica*.
- Wang, H., Bransby, M. F., Lehane, B. M., Wang, L. & Hong, Y. (2022). "Numerical investigation of the monotonic drained lateral behaviour of large-diameter rigid piles in medium-dense uniform sand." *Géotechnique*.
- Wang, H., Lehane, B. M., Bransby, M. F., Askarinejad, A., Wang, L. Z. & Hong, Y. (2022). "A simple rotational spring model for laterally loaded rigid piles in sand." *Marine Structures*, 84, 103225. <https://doi.org/10.1016/j.marstruc.2022.103225>
- Wang, H., Lehane, B. M., Bransby, M. F., Wang, L. Z., Hong, Y. & Askarinejad, A. (2023). "Lateral behavior of monopiles in sand under monotonic loading: insights and a new simple design model." *Ocean Engineering*. <https://doi.org/10.1016/j.oceaneng.2023.114334>

## Acknowledgements

The MIDAS project was developed within the GROW joint research programme, with funding from Topsector Energiesubsidie under RVO grant TEHE111013. My sincere thanks to the MIDAS project team and partners, and to the ISSMGE TC104 community and the ICPMG 2026 organisers in Zurich for the invitation.
