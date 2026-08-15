---
layout: archive
title: "Datasets"
permalink: /datasets/
author_profile: true
---

{% include base_path %}

Curated research datasets from my experimental programmes, hosted on external repositories. All datasets are openly available under CC BY 4.0.

## Sand Triaxial Test Database: drained monotonic triaxial compression tests on 32 granular materials
**Repository:** [4TU.ResearchData](https://doi.org/10.4121/086847a6-ba39-4d66-973b-6b93028c7ad8) · **DOI:** 10.4121/086847a6-ba39-4d66-973b-6b93028c7ad8 · **Year:** 2026

Wang, H.

This dataset is a curated database of drained monotonic triaxial compression tests on granular soils, compiled from published literature and open datasets into a single, uniform, machine-readable format. It covers 32 materials — 30 natural and industrial sands, one rockfill, and one set of glass beads — tested at 18 laboratories worldwide, comprising 195 isotropically consolidated tests with approximately 42,000 digitized measurement records of axial strain, volumetric strain, and effective radial and vertical stress.

The materials span a wide range of gradations (median grain size d50 from 0.12 to 7.2 mm, coefficient of uniformity Cu from 1.0 to 431) and the tests cover initial relative densities from very loose to very dense and effective confining stresses from 20 to 3500 kPa. Each material is stored as a single self-contained CSV file with six standardized sections: file information, full source references with DOIs, index properties (d50, Cu, Gs, e_max, e_min, critical-state friction angle), particle size distribution(s), a test programme catalogue (initial stresses, void ratio, relative density per test), and the stress–strain–volumetric measurement records. An index file summarizes all materials for browsing, and a README documents the format, sign conventions, and ready-to-use Python code for reading the files. Empty cells consistently indicate values not reported in the original source; most test curves were digitized from published figures and carry the usual digitization tolerance.

The database is intended as a benchmark resource for the development, calibration, and validation of constitutive models for sand, for data-driven and machine-learning approaches to soil behaviour, and for comparative studies of monotonic sand response across gradations, densities, and stress levels. The compilation draws on the cited publications, the GEOLAB Material Properties Database, and the SoilModels standard datasets.

This database is a compilation of previously published experimental work. Users are kindly asked to cite both this database and the original source publication(s) of each material they use; the sources are listed per material in the SOURCES section of each CSV file and compiled in references.csv.

**Related article:** [An Open Database of Drained Monotonic Triaxial Tests on Sands (blog post)](/posts/2026/08/sand-triaxial-database/)

## MIDAS centrifuge dataset: Cyclic lateral response of monopiles in sand from centrifuge tests conducted at Deltares
**Repository:** [4TU.ResearchData](https://doi.org/10.4121/fa710994-f591-453a-b9c8-2759d6cd2f21) · **DOI:** 10.4121/fa710994-f591-453a-b9c8-2759d6cd2f21 · **Year:** 2026

Wang, H., Zwaan, R., Askarinejad, A., Peccin da Silva, A., Konstadinou, M. & Pisanò, F.

This dataset contains the experimental results from a comprehensive centrifuge testing programme investigating the monotonic and cyclic lateral response of monopiles in sand. The experiments were conducted at the Deltares Geotechnical Centrifuge laboratory in Delft, the Netherlands, as part of the [MIDAS](/portfolio/midas/) (Monopile Improved Design through Advanced cyclic Soil modelling) research project.

The dataset includes measurements from instrumented model piles tested under varying pile geometries, loading conditions, soil densities, and saturation states. Recorded quantities include applied loads and corresponding pile and soil response parameters. The tests were designed to investigate the influence of cyclic load amplitude, loading sequence, and soil state on monopile behaviour, with particular emphasis on very dense sand conditions. These data provide an experimental benchmark for the development, calibration, and validation of numerical and analytical models for offshore monopile foundations subjected to cyclic loading.

**Related publication:** [Physical modelling of cyclically loaded monopiles in sand: the MIDAS centrifuge testing programme (ISFOG 2025)](/publication/2025-06-03-physical-modelling-of-cyclically-loaded-monopiles-in-sand)

## MIDAS centrifuge dataset: Cyclic lateral response of monopiles in sand from centrifuge tests conducted at TU Delft
**Repository:** [4TU.ResearchData](https://doi.org/10.4121/d04edde3-c05d-4818-9f64-bf1a2f3f86a6) · **DOI:** 10.4121/d04edde3-c05d-4818-9f64-bf1a2f3f86a6 · **Year:** 2026

Wang, H., Askarinejad, A. & Pisanò, F.

This dataset contains results from a centrifuge testing programme investigating the monotonic and cyclic lateral response of monopiles in dense sand. The experiments were conducted at the Delft University of Technology (TU Delft), the Netherlands, as part of the [MIDAS](/portfolio/midas/) (Monopile Improved Design through Advanced cyclic Soil modelling) project. The dataset comprises 23 centrifuge tests (2 monotonic and 21 cyclic) performed on an instrumented aluminium model pile (outer diameter 18 mm, embedded length-to-diameter ratio L/D = 5) in dense Geba sand (relative density Dr = 80%) at 100 × g. Each test is provided as a CSV file containing metadata and time-series measurements from load cells, displacement sensors, and strain gauge instrumentation, including lateral load, pile displacement, rotation, and bending moments, together with processed response quantities (such as ground-surface displacement and rotation). The cyclic tests examine the effects of load amplitude, asymmetry, and loading sequence. The dataset provides a high-quality benchmark for developing, calibrating, and validating analytical, empirical, and numerical models for offshore monopile foundations in sand.

**Related publications:** [Data article: A centrifuge test dataset for cyclically loaded monopile in dense sand (Data in Brief, under review)](/publication/2026-01-05-a-centrifuge-test-dataset-for-cyclically-loaded-monopile) · [Physical modelling of cyclically loaded monopiles in sand: the MIDAS centrifuge testing programme (ISFOG 2025)](/publication/2025-06-03-physical-modelling-of-cyclically-loaded-monopiles-in-sand)

<!-- Template for each dataset entry — copy, uncomment, and fill in:

## Dataset title
**Repository:** [Zenodo](https://doi.org/10.xxxx/zenodo.xxxxxxx) · **DOI:** 10.xxxx/zenodo.xxxxxxx · **Year:** 20XX

Author list.

One- or two-sentence description of the dataset: what was tested, what is included
(raw/processed data, test protocols, soil characterisation), and the related publication.

**Related publication:** [Author list (Year), Journal](/publications/)

-->

The two centrifuge datasets were produced within the [MIDAS](/portfolio/midas/) joint industry project (RVO grant TEHE111013).
