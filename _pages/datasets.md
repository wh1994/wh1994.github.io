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

Experimental data from the [MIDAS](/portfolio/midas/) centrifuge testing programme at Deltares on the monotonic and cyclic lateral response of monopiles in sand. Instrumented model piles were tested under varying pile geometries, loading scenarios, soil densities, and saturation conditions, with emphasis on very dense sand. The dataset (~2 GB of CSV data plus Python scripts) serves as an experimental reference for developing, calibrating, and validating numerical and analytical models of offshore monopile foundations under cyclic loading.

**Related publication:** [Physical modelling of cyclically loaded monopiles in sand: the MIDAS centrifuge testing programme (ISFOG 2025)](/publication/2025-06-03-physical-modelling-of-cyclically-loaded-monopiles-in-sand)

## MIDAS centrifuge dataset: Cyclic lateral response of monopiles in sand from centrifuge tests conducted at TU Delft
**Repository:** [4TU.ResearchData](https://doi.org/10.4121/d04edde3-c05d-4818-9f64-bf1a2f3f86a6) · **DOI:** 10.4121/d04edde3-c05d-4818-9f64-bf1a2f3f86a6 · **Year:** 2026

Wang, H., Askarinejad, A. & Pisanò, F.

Data from 23 centrifuge tests (2 monotonic, 21 cyclic) on an instrumented aluminium model pile in dense sand, conducted at TU Delft within the [MIDAS](/portfolio/midas/) project. Includes raw measurements from load cells, displacement sensors, and strain gauges (~600 MB of CSV time series with metadata), plus processed response data and Python scripts, for validating analytical and numerical monopile models.

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
