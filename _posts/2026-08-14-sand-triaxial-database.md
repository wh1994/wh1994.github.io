---
title: "An Open Database of Drained Monotonic Triaxial Tests on Sands"
date: 2026-08-14
permalink: /posts/2026/08/sand-triaxial-database/
excerpt: "195 drained monotonic triaxial compression tests on 32 granular materials, compiled into a single uniform, machine-readable format and released under CC-BY-4.0 on 4TU.ResearchData."
tags:
  - sand
  - triaxial test
  - database
  - constitutive modelling
  - open data
toc: true
toc_sticky: true
---

> **Data availability.** The database is openly available under a CC-BY-4.0 license
> on 4TU.ResearchData: [doi.org/10.4121/086847a6-ba39-4d66-973b-6b93028c7ad8](https://doi.org/10.4121/086847a6-ba39-4d66-973b-6b93028c7ad8).
> If you use it, please cite the database DOI **and** the original data source(s)
> listed in each material file.

## Why another database?

The drained monotonic triaxial compression test is the workhorse of sand
characterisation. It underpins the calibration of practically every
constitutive model for granular soils — from Mohr–Coulomb through critical-state
models such as SANISAND to hypoplasticity — and it is increasingly used as
training data for machine-learning surrogates of soil behaviour. Yet the
underlying test data remain scattered across journal papers, theses, project
reports, and institutional repositories, in inconsistent formats, units, and
sign conventions. Anyone who has tried to assemble a multi-sand calibration
study knows the routine: hunting down PDFs, digitizing stress–strain curves,
and reconciling conventions, material by material.

This database is an attempt to do that work once, carefully, and share the
result. It compiles **195 drained monotonic triaxial compression tests on 32
granular materials** — 30 natural sands from laboratories across Europe,
North America, Asia, and Australia, plus one rockfill and one set of glass
beads as end members — into a single, uniform, machine-readable format.
Every test is traceable to its published source.

## What the database covers

The figure below summarises the coverage: one row per material (sorted from
fine to coarse), showing the median grain size d₅₀, the initial effective
confining stress of every test, the initial relative density of every test,
and the number of tests per material.

![Coverage of the sand triaxial test database: median grain size, initial confining stress, and initial relative density of all 195 tests on 32 materials](/images/posts/sand-triaxial-database/database_coverage.png)

A few observations on the coverage:

- **Grain size.** Median grain sizes range from 0.12 mm (Geba sand) to about
  7 mm (Lianghekou rockfill) — from fine sand through coarse sand into gravel.
  Most materials are clean fine-to-medium silica sands, the type most relevant
  to offshore foundation and liquefaction problems.
- **Stress level.** Initial effective confining stresses span 20 kPa to
  3.5 MPa. The bulk of the tests sit in the 50–500 kPa range typical of
  onshore and offshore foundation engineering; the rockfill tests extend the
  database to dam-scale stresses.
- **Density.** Initial relative densities cover the full spectrum from very
  loose (Dr₀ ≈ 0–15 %) to very dense (Dr₀ ≈ 100 %). Several materials —
  Karlsruhe fine sand being the richest, with 25 tests — provide systematic
  density–stress grids well suited for calibrating state-dependent models.
- **Replication across laboratories.** Two materials were deliberately
  included with data from multiple laboratories: Fontainebleau NE34 sand
  (Université Gustave Eiffel, DTU, KIT) and UWA superfine silica sand (UWA,
  TUHH, RUB). These parallel datasets allow inter-laboratory scatter to be
  assessed — a useful reality check on how precisely any model should be
  expected to fit a single test series.

## The index

The table below is the database index (`index.csv`): one row per material with
its index properties, test count, and the ranges of initial confining stress
and relative density. An en dash (–) means the value was not reported in the
source.

| # | Material | Type | d<sub>50</sub> (mm) | C<sub>u</sub> | G<sub>s</sub> | e<sub>max</sub> | e<sub>min</sub> | φ<sub>c</sub> (°) | Tests | σ′<sub>r0</sub> (kPa) | D<sub>r0</sub> (%) | Data source |
|---|----------|------|------|------|------|------|------|------|------|------|------|-------------|
| 01 | Karlsruhe fine sand | natural silica sand | 0.14 | 1.5 | 2.65 | 1.054 | 0.677 | 33.1 | 25 | 49–401 | 15–95 | [Wichtmann & Triantafyllidis (2016)](https://doi.org/10.1007/s11440-015-0402-z) |
| 02 | Geba sand | natural silica sand | 0.119 | 1.59 | 2.67 | 1.07 | 0.64 | 31.7 | 5 | 55–406 | 41–76 | [Liu et al. (2026)](https://doi.org/10.1016/j.soildyn.2026.110177) |
| 03 | Hokksund sand | natural sand | 0.38 | 2.04 | 2.71 | – | – | 38 | 12 | 125–700 | 30–87 | Tadesse (2000) |
| 04 | Perth sand | natural silica sand | 0.2 | 1.53 | 2.65 | 0.98 | 0.471 | 29.6 | 4 | 50–400 | 90 | Sakellariadis & Anastasopoulos (2022) |
| 05 | Darmstadt sand | natural sand | 0.48 | 2.41 | 2.617 | 0.788 | 0.444 | 32.7 | 6 | 50–500 | 28–89 | [GEOLAB database, Beroya-Eitner et al. (2024)](https://doi.org/10.5281/zenodo.12697903) |
| 06 | Fontainebleau sand (Eiffel) | natural silica sand | 0.21 | 1.466 | 2.65 | 0.87 | 0.53 | 31.5 | 9 | 100–400 | 46–87 | Li (2013) |
| 07 | Fontainebleau sand (DTU) | natural silica sand | 0.21 | 1.466 | 2.655 | 0.853 | 0.549 | 33.4 | 9 | 50–200 | 48–79 | [Latini & Zania (2016)](https://orbit.dtu.dk) |
| 08 | Fontainebleau sand (KIT) | natural silica sand | 0.201 | 1.659 | 2.659 | 0.887 | 0.547 | 31.4 | 4 | 50–300 | 15–98 | Zuern et al. (2025) |
| 09 | Ottawa F-65 sand | natural silica sand | 0.2 | 1.62 | 2.65 | 0.7389 | 0.4915 | 34.6 | 11 | 100–700 | 7–63 | Parra Bastidas (2016) |
| 10 | UWA superfine silica sand (UWA) | natural silica sand | 0.18 | 1.67 | 2.65 | 0.7809 | 0.5028 | 33 | 6 | 50–1000 | 37–89 | Chow et al. (2019) |
| 11 | UWA superfine silica sand (TUHH) | natural silica sand | 0.18 | 1.67 | 2.65 | 0.7809 | 0.5028 | 33 | 6 | 50–200 | 29–91 | Chow et al. (2019) |
| 12 | UWA superfine silica sand (RUB) | natural silica sand | 0.24 | 1.5 | 2.65 | 0.787 | 0.521 | 32.1 | 9 | 50–200 | 50–94 | [Canales-Brenlla et al. (2026)](https://doi.org/10.1007/s11440-026-02969-9) |
| 13 | Nevada sand | natural silica sand | 0.15 | 1.75 | 2.67 | 0.887 | 0.51 | 29 | 7 | 20–300 | 81 | Arulmoli et al. (1992) |
| 14 | SFS sand | natural silica sand | 0.25 | 1.87 | 2.65 | 0.703 | 0.516 | 31 | 3 | 50–200 | 87 | Hao et al. (2019) |
| 15 | Leighton Buzzard sand (fraction E) | natural silica sand | 0.14 | 1.58 | 2.65 | 1.014 | 0.613 | 33.4 | 2 | 100–200 | 70–81 | [Lanzano et al. (2016)](https://doi.org/10.1007/s10706-016-0019-5) |
| 16 | Blessington sand | natural sand | 0.15 | 2.4 | – | – | – | 35 | 3 | 50–200 | 30 | Barzan & Igoe (2025) |
| 17 | Nakatashima Dune sand | natural dune sand | 0.41 | 1.59 | 2.74 | 0.863 | 0.519 | 33.7 | 3 | 30–100 | 44–56 | [Nakano (2024)](https://doi.org/10.1680/jgele.24.00029) |
| 18 | Dunkirk sand | natural marine sand | 0.28 | 1.72 | 2.65 | 0.91 | 0.54 | 32 | 5 | 50–400 | 75–100 | Chow (1996) |
| 19 | Stvanice sand | natural sand | 0.1205 | 17.5 | 2.72 | – | – | 36.7 | 3 | 50–200 | – | [SoilModels standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/) |
| 20 | Rohatec sand | natural sand | 0.483 | 3.25 | – | – | – | 35 | 3 | 50–200 | – | [SoilModels standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/) |
| 21 | Motol sand | natural sand | 0.4028 | 431 | 2.67 | – | – | 38 | 3 | 50–200 | – | [SoilModels standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/) |
| 22 | Kralupy sand | natural sand | 0.1655 | 12.82 | 2.71 | – | – | 35 | 3 | 50–200 | – | [SoilModels standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/) |
| 23 | Komorany sand | natural sand | 1.1831 | 4 | 2.65 | – | – | 35.1 | 4 | 100–500 | – | [SoilModels standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/) |
| 24 | Kolny sand | natural sand | – | – | 2.65 | – | – | 36 | 1 | 200 | – | [SoilModels standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/) |
| 25 | Jablonec sand | natural sand | 0.669 | 171 | 2.65 | – | – | 36.8 | 3 | 100–400 | – | [SoilModels standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/) |
| 26 | Hrusovany sand | natural sand | 2.125 | 10.93 | 2.65 | – | – | 35.2 | 3 | 50–200 | – | [SoilModels standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/) |
| 27 | Dobrany sand | natural sand | 0.4641 | 4.44 | 2.65 | – | – | 35.5 | 3 | 50–200 | – | [SoilModels standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/) |
| 28 | Chyne sand | natural sand | 0.215 | 45.56 | 2.65 | – | – | 35.2 | 3 | 50–150 | – | [SoilModels standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/) |
| 29 | Lianghekou rockfill | sandstone rockfill | 7.175 | 19.975 | 2.749 | 0.457 | 0.197 | 40 | 20 | 500–3500 | 60–90 | [Jin et al. (2024)](https://doi.org/10.1007/s10035-024-01428-0) |
| 30 | Changi sand | natural marine sand | 0.3 | 2 | 2.6 | 0.916 | 0.533 | 33.4 | 8 | 35–300 | −3–68 | Wanatowski & Chu (2007) |
| 31 | Stockton Beach sand | natural beach sand | 0.36 | 2.11 | 2.65 | 0.79 | 0.51 | 31.1 | 6 | 25–100 | 48–83 | [Ansari et al. (2018)](https://doi.org/10.1139/cgj-2017-0559) |
| 32 | Glass beads | glass beads | 1.325 | 1 | 2.45 | – | – | – | 3 | 50–200 | – | [Hazzar et al. (2020)](https://doi.org/10.1016/j.powtec.2019.09.095) |

*d₅₀ = median grain size; Cᵤ = coefficient of uniformity; Gₛ = specific
gravity; e_max / e_min = maximum / minimum void ratio; φ_c = critical state
friction angle; σ′_r0 = initial effective confining stress; D_r0 = initial
relative density after consolidation. Data sources are given as short
citations; the full citations, together with supporting references (site
characterisation reports, related publications), are listed in the `SOURCES`
section of each material file.*

## How the data are organised

Each material is a **single self-contained CSV file** with six clearly
delimited sections, so a file can be understood — and parsed — without any
external documentation:

1. **FILE_INFO** — material name, type, testing laboratory, origin, license,
   and compilation metadata.
2. **SOURCES** — every reference used, with its role (data source, site
   characterisation, related publication, dataset repository), full citation,
   and DOI or URL.
3. **INDEX_PROPERTIES** — d₅₀, Cᵤ, Gₛ, e_max, e_min, φ_c, with units.
4. **PARTICLE_SIZE_DISTRIBUTION** — grain diameter vs. percent finer by
   weight; multiple sievings are stacked in long format.
5. **TEST_PROGRAMME** — one row per test: drainage, loading and consolidation
   conditions, initial stresses, initial void ratio e₀ and relative density
   D_r0, number of data points, and the source of the data.
6. **TEST_DATA** — the measurement records themselves:
   `test_id, eps_a[%], eps_v[%], sigma_r[kPa], sigma_v[kPa]`.

The conventions are deliberately strict and uniform across all 32 files:

- All tests are **drained monotonic triaxial compression tests**,
  isotropically consolidated.
- **Compression positive** for strains and stresses; all stresses are
  effective stresses in kPa.
- An **empty cell always means "not reported in the source"** — never zero.
- e₀ and D_r0 describe the state after consolidation, at the start of
  shearing.

A short Python snippet in the package README reads any material file into a
dictionary of sections in about fifteen lines — no dependencies beyond the
standard library, and one further line converts any section to a pandas
DataFrame.

## An example: Karlsruhe fine sand

To show what the test data actually look like, the figure below plots the
richest dataset in the database: the 25 tests on Karlsruhe fine sand
([Wichtmann & Triantafyllidis, 2016](https://doi.org/10.1007/s11440-015-0402-z)).
Each row is one confining stress level (σ′_r0 ≈ 50, 100, 200, 300, and
400 kPa); the left column shows the deviator stress q and the right column the
volumetric strain ε_v, both against axial strain ε_a, with five relative
densities from loose (D_r0 ≈ 15–25 %) to dense (D_r0 ≈ 85–95 %) at each
stress level.

![Drained monotonic triaxial compression tests on Karlsruhe fine sand: deviator stress and volumetric strain versus axial strain at five confining stress levels and five relative densities each](/images/posts/sand-triaxial-database/karlsruhe_fine_sand_tests.png)

The dataset is a textbook illustration of state-dependent sand behaviour, and
of why a systematic density–stress grid is so valuable for calibration: dense
specimens show a pronounced peak followed by post-peak softening and strong
dilation, loose specimens harden monotonically and contract, and the same
material shifts along this spectrum as the confining stress increases. All 25
curves come from a single `TEST_DATA` section in one CSV file; the initial
state of every test (e₀, D_r0, σ′_r0) is catalogued in the `TEST_PROGRAMME`
section of the same file. Equivalent plots for every material are included in
the dataset package.

## Honesty about data quality

Most of the stress–strain curves were digitized from published figures rather
than taken from original data files. Digitized values are rounded (strains to
four decimals, stresses to 0.01 kPa) and carry the usual digitization
tolerance; minor artifacts — for example a percent-finer value marginally
above 100 — may remain. In a few cases the reported void ratios and relative
densities are mutually inconsistent with the reported e_max and e_min; these
are flagged in the notes where known, and users who need strict consistency
should recompute D_r from e₀, e_max, and e_min. The index properties of the
poorly graded Czech sands (materials 19–28) include some very high uniformity
coefficients reported as-is from the source. None of this is unusual for
compiled experimental data — but it is stated explicitly, per file, rather
than left for the user to discover.

## Intended uses

- **Constitutive model calibration and validation** across a wide range of
  materials, densities, and stress levels — including checking whether a
  parameter set calibrated on one sand generalises to others.
- **Benchmarking**: the multi-laboratory Fontainebleau and UWA sand datasets
  provide a measure of inter-laboratory scatter against which model accuracy
  can be judged fairly.
- **Machine learning**: 195 uniformly formatted stress–strain–dilatancy
  curves with consistent metadata (initial state, index properties, grading)
  make a clean starting point for data-driven modelling of granular soils.
- **Teaching**: real, traceable test data on well-known reference sands
  (Fontainebleau, Ottawa F-65, Nevada, Karlsruhe, Leighton Buzzard) in a
  format students can load in one line.

## Acknowledgements

This compilation stands on the shoulders of the researchers who published
their test data in the first place — every material file lists them
explicitly. It also draws on two existing open resources: the
[GEOLAB Material Properties Database](https://doi.org/10.5281/zenodo.12697903)
and the [SoilModels sand and clay standard datasets](https://soilmodels.com/sand-and-clay-standard-datasets/).

## Citation

Please cite the database as:

> Wang, H. (2026). *Sand Triaxial Test Database: drained monotonic triaxial
> compression tests on 32 granular materials* [Data set]. 4TU.ResearchData.
> https://doi.org/10.4121/086847a6-ba39-4d66-973b-6b93028c7ad8

and cite the original data source(s), listed in each material file's
`SOURCES` section, for every material you use.

---

*License: the database and this article are released under
[CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/).*
