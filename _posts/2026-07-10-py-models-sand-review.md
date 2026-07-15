---
title: "A Critical Review of p-y Models for Laterally Loaded Piles in Sand"
date: 2026-07-10
permalink: /posts/2026/07/py-models-sand-review/
excerpt: "From the classical Reese/API formulation to hyperbolic, CPT-based, PISA and mechanism-based models for offshore monopiles."
tags:
  - p-y curves
  - monopile
  - offshore wind
  - sand
toc: true
toc_sticky: true
---

> **Revision note.** This article was first drafted in 2020 and was substantially revised in 2026. The revised version separates local soil reaction from global foundation response, distinguishes flexible piles from rigid and intermediate foundations, and includes developments in PISA, rotational-spring, installation-aware and CPT-based modelling.
>
> **Engineering note.** This is a technical review, not a substitute for project-specific design verification. Published equations should be checked against the original papers and the edition of the governing standard adopted by the project.

## Executive summary

Piles are among the oldest foundation types in engineering, but for most of that history their job was to carry vertical load. Their systematic use as the primary *lateral* load-resisting element is comparatively recent. When the offshore oil and gas industry moved into deeper water from the 1950s onwards, fixed platforms came to rest on long steel piles driven through the seabed, and wave, current and wind loading made lateral response a governing design condition. Much of the classical theory for laterally loaded piles - including the field tests behind today's standard design curves - was developed in that era, for that type of structure.

The rise of offshore wind has changed the problem. A jacket pile in oil and gas is slender - typically one to two metres in diameter with an embedded length of thirty diameters or more - and resists load by bending, with the jacket frame restraining the pile head. A modern offshore wind monopile is a different object altogether: diameters of six to ten metres or more, embedment of only three to six diameters, and a large overturning moment delivered by the tower through a single unrestrained connection. Instead of flexing like a beam, a monopile tends to rotate almost as a rigid body. The soil resistance it mobilises, and the way that resistance should be modelled, differ accordingly.

For both generations of structure, the most widely used design tool has been the same one: the *p-y* method. It represents a laterally loaded pile as a beam supported by nonlinear springs. At a given depth, the spring law relates lateral soil reaction per unit pile length, $p$, to local pile displacement, $y$. The method remains popular because it is computationally efficient, transparent and easy to couple to structural models.

Its apparent simplicity hides several problems:

1. A *p-y* curve is not a unique soil property. It depends on pile geometry, deformation mode, stress level, installation method, loading path and the assumptions used to separate lateral force from rotational resistance.
2. The classical Reese/O'Neill-Murchison/API sand curve was calibrated mainly from tests on relatively slender piles. Direct application to large-diameter monopiles can give the wrong initial stiffness, stiffness degradation and ultimate resistance.
3. For low-$L/D$ monopiles, rotation dominates the response. Distributed moment, base shear and base moment may need to be considered, although their significance depends on geometry and the conditions investigated.
4. No single curve is best for every design problem. The suitable model depends on whether the target is ultimate capacity, serviceability stiffness, natural frequency, cyclic accumulation or a complete load-displacement response.
5. The most defensible modern workflow is to choose a model family that matches the pile deformation mechanism, calibrate it to site data - preferably CPT and small-strain stiffness data - and validate the *global* pile response rather than only comparing isolated local curves.

![Concept of the p-y method](/images/posts/py-sand-review/py-method-concept.svg)

*Figure 1. Classical beam-on-nonlinear-Winkler-foundation idealisation. The soil reaction $p(z)$ has units of force per unit pile length.*

## 1. Scope and notation

This review focuses on the monotonic lateral response of single piles in drained sand. Cyclic loading is discussed because the monotonic curve normally forms the backbone of a cyclic model, but a monotonic curve alone cannot describe hysteresis, ratcheting, permanent rotation or cycle-dependent stiffness.

The main symbols are:

| Symbol | Meaning |
|---|---|
| $D$ | pile outside diameter |
| $L$ | embedded pile length |
| $z$ | depth below seabed or ground surface |
| $p$ | net lateral soil reaction per unit pile length |
| $y$ | local lateral pile displacement |
| $p_u$ | ultimate lateral soil reaction per unit length |
| $k_i$ | initial tangent stiffness of a local *p-y* curve |
| $\sigma'_v$ | vertical effective stress |
| $\gamma'$ | effective unit weight |
| $\phi'$ | effective friction angle |
| $D_r$ | relative density |
| $q_c$ | CPT cone resistance |
| $G_0$ or $G_{max}$ | small-strain shear modulus |
| $EI$ | pile bending stiffness |

The word **pile** is used broadly. A long flexible jacket pile and a short rigid monopile may have similar diameters but fundamentally different soil-flow and deformation mechanisms. ISO 19901-4:2025 explicitly distinguishes intermediate foundations, typically $0.5 \leq L/D \leq 10$, from long and flexible piles with $L/D>10$ [ISO, 2025](#ref-iso2025). That distinction should also be reflected in model selection.

## 2. What a p-y curve represents - and what it does not

### 2.1 The Winkler idealisation

In the classical formulation, the pile is discretised as a beam and the soil is replaced by independent nonlinear springs. For a beam model containing lateral springs only, local equilibrium is commonly written in a form equivalent to

$$
EI\frac{d^4y}{dz^4}=p(z),
$$

subject to the adopted sign convention and variation of $EI$ with depth.

This equation makes the method attractive: once a *p-y* relation is supplied at each depth, a standard beam solver can predict deflection, rotation, shear and bending moment.

However, the independent-spring assumption omits vertical shear transfer between neighbouring soil layers. It also assumes that all relevant soil resistance can be represented by a lateral force acting at the pile centreline. For a large-diameter pile, the soil can exert a distributed moment on each cross-section. If a distributed moment law $m$-$\theta$ is introduced, the lateral reaction inferred from the fourth derivative of displacement or the second derivative of bending moment is no longer the complete soil-structure interaction description.

### 2.2 A p-y curve is an equivalent response, not an intrinsic material law

Unlike a triaxial stress-strain curve, a *p-y* curve depends on both soil and structure. Important dependencies include:

- pile diameter, embedded length and bending stiffness;
- rigid-body rotation versus flexural bending;
- load eccentricity and pile-head restraint;
- sand density, stress level, fabric and dilatancy;
- drainage and loading rate;
- installation-induced changes in density and stress;
- interface roughness, gapping and remoulding;
- layering, slope and scour;
- monotonic, one-way cyclic, two-way cyclic or multidirectional loading.

Consequently, the phrase **diameter effect** is often too vague. A change in diameter also changes stress level, flexural rigidity, $L/D$, the rotation profile and the relative importance of distributed moment. A useful model should separate these effects rather than absorb all of them into one empirical diameter correction.

### 2.3 Extracting p-y curves is numerically delicate

Experimental *p-y* curves are often derived from measured bending moments. The operation requires differentiating a fitted moment profile twice, which amplifies measurement noise and makes the result sensitive to smoothing, gauge spacing and boundary assumptions. Curves extracted from three-dimensional finite-element analyses are also model-dependent: the result changes with the constitutive model, interface treatment, installation simulation and the method used to partition distributed force and moment.

For this reason, a local *p-y* curve should not be accepted merely because it looks plausible. It should be tested by reconstructing quantities that are directly measured or required in design, such as pile-head load-displacement response, rotation, bending-moment distribution and ultimate capacity.

## 3. Historical development of sand p-y models

### 3.1 McClelland and Focht: the load-transfer concept

The modern load-transfer approach is generally traced to McClelland and Focht (1956), who introduced the use of nonlinear soil reactions to analyse laterally loaded piles [McClelland and Focht, 1956](#ref-mcclelland1956). The key conceptual step was to avoid treating the soil as a single elastic continuum while retaining a one-dimensional beam representation of the pile.

### 3.2 Reese, Cox and Koop: the first practical sand model

Reese et al. (1974) developed the first widely adopted practical sand *p-y* procedure using full-scale lateral pile tests at Mustang Island [Cox et al., 1974](#ref-cox1974); [Reese et al., 1974](#ref-reese1974). The principal test pile was approximately $0.61$ m in diameter and $21$ m long, with $L/D\approx34$. The deposit was very dense sand.

The original curve was assembled from straight and parabolic segments. Its principal ingredients were:

- an initial stiffness increasing linearly with depth;
- shallow and deep ultimate-resistance mechanisms;
- empirical correction factors introduced to fit the field tests;
- specified displacements at characteristic points on the curve.

The shallow mechanism was idealised as a passive wedge, while the deep mechanism represented soil flowing around the pile. The ultimate resistance was taken as the smaller of the shallow and deep values.

The model was a major engineering advance, but the calibration database was narrow. Several constants, characteristic displacements and correction factors are therefore better regarded as test-specific empirical components than universal sand behaviour.

### 3.3 Bogard-Matlock and Scott simplifications

Bogard and Matlock (1980) simplified the Reese construction by expressing ultimate resistance through coefficients related to friction angle and by tabulating normalised curve points [Bogard and Matlock, 1980](#ref-bogard1980). Scott (1980) proposed a bilinear representation with a reduced post-yield slope rather than a finite ultimate plateau [Scott, 1980](#ref-scott1980).

These models are historically important because they show two recurring design choices:

- retain a detailed empirical curve assembled from several branches; or
- replace it with a simpler mathematical function that is easier to implement but less able to represent all stages of response.

### 3.4 O'Neill and Murchison: the hyperbolic-tangent API family

O'Neill and Murchison (1983) replaced the segmented curve with a continuous hyperbolic-tangent relation [O'Neill and Murchison, 1983](#ref-oneill1983):

$$
p=A p_u\tanh\left(\frac{kzy}{A p_u}\right),
$$

where $k$ is a depth-stiffness coefficient and $A$ is an empirical factor. In the commonly used legacy form,

$$
A=\max\left(3-0.8\frac{z}{D},\,0.9\right)
$$

for static loading, while $A=0.9$ was used for cyclic curves.

A convenient simplified expression for the ultimate resistance is

$$
p_u=\min\left[\left(C_1z+C_2D\right)\sigma'_v,\,C_3D\sigma'_v\right],
$$

where $C_1$, $C_2$ and $C_3$ depend on $\phi'$. With $\sigma'_v=\gamma'z$, the two branches represent shallow and deep mechanisms.

The initial tangent is

$$
\left.\frac{dp}{dy}\right|_{y=0}=kz.
$$

This model became the basis of the familiar API sand *p-y* curve. It is compact and numerically stable, but its limitations are significant:

- the initial tangent is imposed by an empirical $k$ value and increases linearly with depth;
- the transition from initial response to ultimate resistance is fixed by the $\tanh$ shape;
- the static factor $A$ is an empirical depth correction;
- the cyclic version is a reduced monotonic envelope, not a hysteretic cyclic constitutive model;
- the underlying tests were not representative of modern low-$L/D$, large-diameter monopiles.

The direction of error is not universal. Many monotonic tests and numerical studies report that the API local curve is initially too stiff and degrades unrealistically, while some operational back-analyses of wind turbines motivate an increase in very-small-strain foundation stiffness. These observations concern different strain ranges and often compare local spring stiffness with global foundation stiffness; they should not be treated as direct contradictions.

### 3.5 Hyperbolic p-y models

A two-parameter hyperbola is widely used to represent the backbone curve:

$$
p=\frac{y}{\dfrac{1}{k_i}+\dfrac{y}{p_u}}
=\frac{k_i y}{1+k_i y/p_u}.
$$

The model has a clear initial tangent $k_i$ and approaches $p_u$ asymptotically. Georgiadis et al. (1992) adopted this form after centrifuge tests in medium-dense sand and found that several earlier formulations overpredicted pile stiffness [Georgiadis et al., 1992](#ref-georgiadis1992). Related hyperbolic forms were subsequently used or modified by Kim et al. (2004), Klinkvort and Hededal (2013), Kirkwood (2016) and Zhu et al. (2016) [Kim et al., 2004](#ref-kim2004); [Klinkvort and Hededal, 2013](#ref-klinkvort2013); [Kirkwood, 2016](#ref-kirkwood2016); [Zhu et al., 2016](#ref-zhu2016).

The main differences between these models are not the curve shape but the expressions used for $k_i$, $p_u$ and any depth correction.

**Advantages**

- only two parameters;
- smooth and easy to implement;
- clear separation of initial stiffness and ultimate resistance;
- often fits monotonic test data better than a fixed API $\tanh$ curve.

**Limitations**

- the rate of stiffness degradation is fixed once $k_i$ and $p_u$ are selected;
- the ultimate value is approached only at infinite displacement;
- model parameters are frequently calibrated to a limited geometry and sand state;
- a good fit to one local curve does not ensure a correct global pile response.

### 3.6 Diameter and small-strain stiffness corrections

As offshore wind monopiles increased in diameter, several studies modified the initial stiffness of the API curve. Wiemann et al. (2004), Sørensen et al. (2010) and Kallehave et al. (2012) are representative contributions [Wiemann et al., 2004](#ref-wiemann2004); [Sørensen et al., 2010](#ref-sorensen2010); [Kallehave et al., 2012](#ref-kallehave2012).

Kallehave et al. introduced stress- and strain-level corrections to the API initial stiffness, motivated partly by measured dynamic behaviour of operating turbines. The important lesson is broader than the specific correction: the stiffness controlling natural frequency and fatigue loading occurs at much smaller strains than the stiffness mobilised in a monotonic pushover test.

A single tangent $k_i$ is therefore a poor descriptor across all load levels. For serviceability and dynamics, a model tied to $G_0$ and an explicit modulus-reduction law is preferable to a constant empirical subgrade modulus.

### 3.7 CPT-based p-y models

CPT-based models use $q_c$ as a direct proxy for in-situ sand state and stress level. This avoids converting CPT data into a single relative density or peak friction angle and then feeding those interpreted values into another empirical model.

Representative models include Novello (1999), Dyson and Randolph (2001), Li et al. (2014), Suryasentana and Lehane (2014, 2016), and Liu et al. (2025) [Novello, 1999](#ref-novello1999); [Dyson and Randolph, 2001](#ref-dyson2001); [Li et al., 2014](#ref-li2014); [Suryasentana and Lehane, 2014](#ref-suryasentana2014); [Suryasentana and Lehane, 2016](#ref-suryasentana2016); [Liu et al., 2025](#ref-liu2025).

Early CPT-based relations often used a power law of the generic form

$$
p=C\,D\,\sigma_v'^a q_c^b\left(\frac{z}{D}\right)^c\left(\frac{y}{D}\right)^d.
$$

A power law is convenient over the displacement range used for calibration, but it has no finite ultimate resistance. Exponential forms introduce an asymptote:

$$
p=p_u\left[1-\exp\left(-a\left(\frac{y}{D}\right)^b\right)\right].
$$

The 2016 Suryasentana-Lehane formulation combined a small-displacement stiffness related to $G_{max}$ with a CPT-based nonlinear response. Liu et al. (2025) proposed a four-parameter modified hyperbola in which initial stiffness, ultimate resistance, transition-shape parameter and resistance adjustment are related to $q_c$.

CPT-based models are especially attractive for layered offshore sites, but four cautions are necessary:

1. $q_c$ is affected by stress level, compressibility, ageing and particle crushing; the same $q_c$ does not guarantee the same lateral response in all sands.
2. A local CPT correlation does not automatically include installation effects for a large open-ended monopile.
3. The pile geometry and deformation mode represented by the calibration database must match the design case.
4. The transition from a point measurement to a representative profile requires filtering and layer-boundary treatment.

### 3.8 PISA: a multi-component soil-reaction model

The PISA project was developed specifically for offshore wind monopiles and combined field testing with calibrated three-dimensional finite-element analyses [McAdam et al., 2020](#ref-mcadam2020); [Taborda et al., 2020](#ref-taborda2020); [Burd et al., 2020](#ref-burd2020).

PISA does not represent the foundation using a distributed *p-y* curve alone. Its one-dimensional model includes:

- distributed lateral load, $p$-$y$;
- distributed moment, $m$-$\theta$;
- base shear, $H_B$-$y_B$;
- base moment, $M_B$-$\theta_B$.

Each component is represented by a flexible conic function with parameters controlling:

- initial tangent;
- ultimate resistance;
- displacement or rotation required to mobilise the ultimate value;
- curvature of the transition region.

The model uses dimensionless normalisation involving effective stress, pile diameter and small-strain shear modulus. This is a substantial improvement over a fixed empirical $kz$ initial tangent because it acknowledges both stress level and small-strain stiffness.

The published sand calibration was developed for the dense marine sand at Dunkirk over the geometry and loading range studied in PISA. The framework is general, but the numerical parameter functions should not be assumed universal without checking sand type, density, stress state and geometry.

PISA also makes an important conceptual point: when a pile behaves as an intermediate or rigid foundation, a *p-y*-only representation may force several physical mechanisms into an equivalent lateral spring. Adding more spring components can improve transferability, but also increases calibration effort and parameter uncertainty.

### 3.9 Rotational-spring and mechanism-based models

An alternative is to simplify the response around the dominant rigid-pile mechanism rather than adding many distributed components. Wang et al. (2022, 2023) showed that the monotonic response of rigid monopiles in uniform sand can be represented by a nonlinear rotational spring located near the pile rotation centre, with a flexibility correction for non-rigid piles [Wang et al., 2022](#ref-wang2022rotation); [Wang et al., 2023](#ref-wang2023).

For the conditions investigated, the pile base contribution was small, and normalised net-pressure curves and ultimate soil pressure were largely independent of pile diameter and load eccentricity. This supports an important distinction:

> The local soil pressure may not possess a strong intrinsic diameter effect for a rigid mechanism, even though the global pile response changes strongly with diameter because $EI$, $L/D$, stress level and kinematics change.

The rotational-spring approach is efficient and physically transparent for rigid piles in reasonably uniform sand. Its limitations are equally clear: it is not intended to replace a distributed model where pile bending, strong layering or local structural demand along the shaft must be resolved explicitly.

### 3.10 Recent p-y + m-theta and flexible-shape models

Recent work has continued in two directions:

- retaining a distributed beam model but adding rotational springs, such as *p-y* + $m$-$\theta$ formulations; and
- retaining a *p-y*-only model but introducing extra shape parameters so stiffness degradation is not fixed by a two-parameter hyperbola.

Zhang et al. (2024) quantified the contributions of distributed lateral load, distributed moment, base shear and base moment and proposed a simplified *p-y* + $m$-$\theta$ model [Zhang et al., 2024](#ref-zhang2024). Fuentes et al. (2021) proposed a model for large-diameter monopiles under static and long-term cyclic loading [Fuentes et al., 2021](#ref-fuentes2021). Liu et al. (2025) used a four-parameter CPT-based modified hyperbola to control the transition region independently [Liu et al., 2025](#ref-liu2025).

These developments indicate a general trend away from changing only $p_u$ or $k_i$. Modern models increasingly treat the complete curve shape, pile kinematics and site characterisation as separate modelling problems.

![Comparison of backbone functions](/images/posts/py-sand-review/model-family-comparison.svg)

*Figure 2. Schematic normalised backbone shapes. The curves are illustrative and do not represent a specific published calibration.*

## 4. Comparison of the main model families

| Model family | Typical basis | Curve controls | Main inputs | Main strength | Main limitation |
|---|---|---|---|---|---|
| Reese segmented curve | full-scale field test | several empirical branches and characteristic points | $\phi'$, $D_r$, $z$, $D$, $\gamma'$ | historically validated and transparent construction | narrow original database; cumbersome; empirical point locations |
| O'Neill-Murchison/API | Reese database and re-evaluation | $k$, $p_u$, fixed $\tanh$ transition, factor $A$ | $\phi'$, density category, $z$, $D$, $\gamma'$ | simple, robust and widely implemented | fixed degradation shape; weak representation of low-$L/D$ monopiles and small-strain response |
| Bilinear | simplified mechanics or test fit | initial and post-yield slopes | model-specific | computationally simple | no realistic smooth degradation; may have no finite capacity |
| Two-parameter hyperbola | centrifuge, 1g or FE calibration | $k_i$, $p_u$ | model-specific | clear parameters; easy fitting | transition shape fixed; asymptotic ultimate |
| Power-law CPT | CPT plus tests or FE | amplitude and exponent | $q_c$, $\sigma'_v$, $z/D$, $y/D$ | direct use of site data | no finite ultimate; validity limited to calibration displacement range |
| Exponential/CPT | CPT plus FE or tests | $p_u$, rate and exponent | $q_c$, $G_0$, stress and geometry | finite asymptote and site-specific profile | parameter transferability and piecewise continuity can be problematic |
| PISA conic components | field tests plus calibrated 3D FE | initial tangent, ultimate, mobilisation displacement, curvature | $G_0$, $\sigma'_v$, $D_r$, geometry | represents force, moment and base components; flexible curve shape | more parameters; published calibration is site- and range-dependent |
| Rotational spring | rigid-pile mechanism plus tests and FE | moment-rotation backbone and flexibility correction | sand state, $L$, $D$, $EI$, loading | very efficient for rigid piles; clear mechanism | unsuitable where distributed bending response or layering dominates |
| Modern modified hyperbola / *p-y* + $m$-$\theta$ | databases and 3D FE | independent stiffness, ultimate and transition controls | CPT or interpreted soil state plus geometry | better control of degradation and rotation effects | still requires independent validation outside calibration database |

## 5. The five ingredients that should be assessed separately

A useful review should not rank models only by their curve equation. Five ingredients control the prediction.

### 5.1 Initial and small-displacement stiffness

The initial tangent controls pile-head stiffness, natural frequency and bending moments at small load. The classical assumption $k_i=kz$ is entirely empirical. A more rational description links stiffness to $G_0$ and a strain-dependent modulus-reduction law:

$$
k_i \sim G_0\,f\left(\frac{z}{D},\frac{L}{D},\nu,\text{pile kinematics}\right).
$$

The exact function is model-dependent, but three principles are robust:

- $G_0$ should be evaluated at the in-situ effective stress and density;
- the stiffness relevant to a wind-turbine frequency calculation is not the secant stiffness at a large monotonic displacement;
- the foundation stiffness matrix should include horizontal-rocking coupling when the pile response is rotation-dominated.

### 5.2 Ultimate soil resistance

Most models assume shallow wedge failure and deep flow-around resistance. The unresolved issue is how the transition depends on $z/D$, $z/L$, pile kinematics and sand state.

A classical form implies

$$
p_u=\sigma'_vD\,N_p\left(\frac{z}{D},\phi'\right),
$$

whereas rigid-pile studies often support an ultimate soil pressure $P_u=p_u/D$ that is primarily a function of actual depth and sand state over the investigated range:

$$
P_u=\frac{p_u}{D}\approx f\left(\sigma'_v,\phi',D_r,z/L\right).
$$

These forms are not automatically inconsistent. They correspond to different normalisations and potentially different failure mechanisms. The appropriate expression should be checked against the deformation mode represented by the model.

### 5.3 Shape of stiffness degradation

The initial tangent and ultimate resistance do not uniquely define the response at working load. Two curves can have identical $k_i$ and $p_u$ but very different secant stiffness at $y/D=0.1\%$ or $1\%$.

This is the central weakness of a two-parameter hyperbola and a fixed $\tanh$ function. A third or fourth parameter controlling curvature is valuable when data cover the transition region. It is not automatically beneficial when data are sparse: extra parameters can hide non-uniqueness rather than improve prediction.

### 5.4 Pile kinematics and rotational resistance

The pile deformation mode should be checked before selecting the spring model. Useful indicators include:

- $L/D$;
- relative pile-soil stiffness;
- the depth of zero displacement or rotation centre;
- the proportion of head displacement caused by rigid rotation versus bending;
- the significance of distributed moment and base reactions.

A rigid pile with nearly linear displacement along depth should not be analysed as though each section deforms independently. Conversely, a flexible pile with substantial curvature cannot be represented adequately by a single rotational spring.

### 5.5 Site state and installation

Sand response is state-dependent. Relative density alone cannot distinguish sands with different stress histories, compressibility, ageing, fabric or particle crushing. CPT and shear-wave measurements provide more direct constraints on current state.

Installation may change both density and lateral stress around the pile. Fan et al. (2021) showed that installation can affect subsequent initial stiffness and lateral capacity [Fan et al., 2021](#ref-fan2021). Wished-in-place numerical models therefore need an explicit justification, especially for displacement piles and large open-ended monopiles.

## 6. Issues that are often missing from p-y reviews

### 6.1 Local curves versus global validation

A local curve can be made to match an extracted *p-y* data set and still predict the wrong head response. The final validation should cover, at minimum:

- pile-head load-displacement and moment-rotation response;
- bending-moment profile;
- rotation centre and displacement shape;
- ultimate load or a clearly defined displacement-based limit state;
- sensitivity to uncertain soil and model parameters.

### 6.2 Serviceability, ultimate limit state and fatigue require different evidence

A model calibrated to ultimate capacity is not automatically suitable for natural-frequency prediction. A model calibrated to tiny operational strains may not predict soil flow at large displacement. It is often better to use a consistent framework with different parameter sets or modulus branches than to force one empirical curve to cover six orders of strain.

### 6.3 Cyclic loading cannot be represented by a reduced static envelope

A cyclic model must describe at least some of the following:

- unloading and reloading stiffness;
- hysteretic damping;
- gapping and contact recovery;
- permanent displacement or rotation;
- densification or cyclic mobility;
- dependence on mean load, amplitude, directionality and number of cycles;
- memory of previous load packages.

The classical API cyclic factor changes the envelope but does not provide those mechanisms. Achmus et al. (2009) and LeBlanc et al. (2010) demonstrated the importance of cyclic load characteristics and accumulation [Achmus et al., 2009](#ref-achmus2009); [LeBlanc et al., 2010](#ref-leblanc2010). Fuentes et al. (2021) and later overlay, bounding-surface and accumulation models extend the backbone in different ways.

A practical review should therefore present the monotonic curve as one component of a cyclic formulation, not as the complete cyclic model.

### 6.4 Scour and layering are not simple depth shifts

Removing soil above the scour level changes more than the origin of $z$. It changes stress state, free-surface geometry, local flow mechanism and the pile deformation mode. Similarly, independent springs generated layer by layer may produce unrealistic jumps at interfaces unless the model includes transition treatment and the influence of neighbouring layers.

For strongly layered profiles, a site-specific three-dimensional analysis or a calibrated one-dimensional model is usually more defensible than applying a uniform-sand equation independently at every CPT point.

### 6.5 Model uncertainty should be separated from soil uncertainty

Uncertainty in $q_c$, $D_r$, $\phi'$, $G_0$ and unit weight is **soil uncertainty**. Uncertainty in curve shape, normalisation, diameter scaling and force-moment partition is **model-form uncertainty**. Running low, best and high soil profiles through one model captures only the first category.

A robust design comparison should include at least two credible model forms when the design is sensitive to soil-structure interaction.

## 7. A practical model-selection workflow

![Model selection workflow](/images/posts/py-sand-review/model-selection-workflow.svg)

*Figure 3. Suggested workflow. The numerical $L/D$ boundaries are indicative; relative stiffness and deformation mode should also be checked.*

### Step 1 - Define the design quantity

Decide whether the critical output is:

- ultimate lateral capacity;
- pile-head displacement or rotation;
- bending moment and fatigue damage;
- foundation stiffness and natural frequency;
- long-term accumulated rotation;
- response under combined lateral load and moment.

### Step 2 - Classify the foundation response

Use $L/D$, $EI$, soil stiffness and a preliminary beam or continuum analysis to determine whether the response is flexible, intermediate or rigid. Do not classify the pile from $L/D$ alone.

### Step 3 - Match the model to the mechanism

- **Long flexible pile:** an established distributed *p-y* formulation may be suitable, provided stiffness and capacity are calibrated to the site.
- **Intermediate or rigid monopile:** use PISA, a *p-y* + $m$-$\theta$ model, a validated rotational-spring model, or site-specific distributed curves that reproduce rotation-dominated behaviour.
- **Strong layering, scour or unusual installation:** derive or calibrate curves from high-quality field, centrifuge or 3D numerical analyses.

### Step 4 - Use in-situ data directly where possible

Use CPT to define stratigraphy and state, and use SCPT, seismic CPT or laboratory bender-element data to constrain $G_0$. Friction angle and relative density correlations should be treated as intermediate interpretations, not exact soil properties.

### Step 5 - Calibrate different response regions consciously

Identify evidence for:

- very-small-strain stiffness;
- working-load secant stiffness;
- transition curvature;
- ultimate resistance and mobilisation displacement;
- cyclic accumulation and damping.

Do not infer all five from one short monotonic test.

### Step 6 - Validate global response

Reproduce measured or trusted reference values of head displacement, rotation and bending moment. If only a finite-element calibration is available, compare against more than one geometry and load level to avoid reproducing a single numerical case.

### Step 7 - Quantify sensitivity and model form uncertainty

Vary both soil parameters and the modelling framework. A neat deterministic curve is not evidence of low uncertainty.

## 8. Recommendations for developing the next generation of sand p-y models

A broadly transferable model for piles in sand should meet the following requirements.

### 8.1 Separate soil state, geometry and kinematics

The model inputs should distinguish:

- in-situ state: $q_c$, $G_0$, $\sigma'_v$, density and compressibility;
- geometry: $D$, $L$, wall thickness and base condition;
- structural response: $EI$ and head restraint;
- loading: eccentricity, monotonic/cyclic character and drainage regime.

### 8.2 Use a flexible but identifiable backbone

A three- or four-parameter curve can independently control initial stiffness, ultimate resistance, mobilisation displacement and transition curvature. The parameters must be identifiable from available data; otherwise the apparent flexibility creates non-unique calibration.

### 8.3 Preserve mechanism changes with pile flexibility

A unified model should transition continuously between rigid rotation and flexible bending. This can be achieved through:

- explicit distributed force and moment springs;
- a rigid rotational mechanism plus a flexibility correction; or
- a work-equivalent distributed stiffness derived from continuum solutions.

### 8.4 Treat cyclic response as path-dependent

The cyclic extension should use the monotonic backbone but add history variables for accumulated displacement, stiffness change, gapping and load reversal. Cycle number alone is insufficient; mean load and load direction are essential.

### 8.5 Build calibration databases around raw observations

Databases should retain pile geometry, installation method, load history, CPT/SCPT, stress level, measured moments and uncertainty. Publishing only processed *p-y* curves makes it impossible to assess the effect of smoothing and force-moment partition.

### 8.6 Validate out of sample

A proposed equation should be tested against sites, sand types and pile geometries that were not used for calibration. Comparisons only against the source data demonstrate curve fitting, not predictive capability.

## 9. Conclusions

The classical sand *p-y* method remains useful, but it should no longer be treated as a universal soil law. The Reese and O'Neill-Murchison/API formulations were transformative for slender offshore piles, yet their empirical initial stiffness, fixed degradation shape and calibration geometry limit direct application to modern monopiles.

Hyperbolic models improve simplicity and interpretability but do not independently control the transition region. CPT-based models improve site characterisation, while modern four-parameter models improve curve flexibility. PISA extends the Winkler framework by including distributed moment and base reactions. Rotational-spring models take the opposite route and simplify the foundation around the dominant rigid-pile mechanism.

The most important conclusion is therefore not that one mathematical function is universally superior. A credible model must match the pile deformation mechanism, strain range, loading history and site state. For design, the model should be judged by its ability to predict global foundation response and structural demand, with uncertainty stated explicitly.

---

## References

1. <a id="ref-achmus2009"></a>Achmus, M., Kuo, Y.-S. and Abdel-Rahman, K. (2009). "Behavior of monopile foundations under cyclic lateral load." *Computers and Geotechnics*, 36(5), 725-735. <https://doi.org/10.1016/j.compgeo.2008.12.003>
2. <a id="ref-bogard1980"></a>Bogard, D. and Matlock, H. (1980). *Simplified calculation of p-y curves for laterally loaded piles in sand*. Earth Technology Corporation.
3. <a id="ref-burd2020"></a>Burd, H. J., Taborda, D. M. G., Zdravković, L., Abadie, C. N., Byrne, B. W., Houlsby, G. T., Gavin, K. G., Igoe, D. J. P., Jardine, R. J., Martin, C. M., McAdam, R. A., Pedro, A. M. G. and Potts, D. M. (2020). "PISA design model for monopiles for offshore wind turbines: application to a marine sand." *Géotechnique*, 70(11), 1048-1066. <https://doi.org/10.1680/jgeot.18.P.277>
4. <a id="ref-cox1974"></a>Cox, W. R., Reese, L. C. and Grubbs, B. R. (1974). "Field testing of laterally loaded piles in sand." *Offshore Technology Conference*. <https://doi.org/10.4043/2079-MS>
5. <a id="ref-dyson2001"></a>Dyson, G. J. and Randolph, M. F. (2001). "Monotonic lateral loading of piles in calcareous sand." *Journal of Geotechnical and Geoenvironmental Engineering*, 127(4), 346-352.
6. <a id="ref-fan2021"></a>Fan, S., Bienen, B. and Randolph, M. F. (2021). "Effects of monopile installation on subsequent lateral response in sand. II: Lateral loading." *Journal of Geotechnical and Geoenvironmental Engineering*, 147(5), 04021022. <https://doi.org/10.1061/(ASCE)GT.1943-5606.0002504>
7. <a id="ref-fuentes2021"></a>Fuentes, W., Gil, M. and Rivillas, G. (2021). "A p-y model for large-diameter monopiles in sands subjected to lateral loading under static and long-term cyclic conditions." *Journal of Geotechnical and Geoenvironmental Engineering*, 147(2), 04020152. <https://doi.org/10.1061/(ASCE)GT.1943-5606.0002448>
8. <a id="ref-georgiadis1992"></a>Georgiadis, M., Anagnostopoulos, C. and Saflekou, S. (1992). "Centrifugal testing of laterally loaded piles in sand." *Canadian Geotechnical Journal*, 29(2), 208-216. <https://doi.org/10.1139/t92-024>
9. <a id="ref-iso2025"></a>International Organization for Standardization (ISO) (2025). *ISO 19901-4:2025, Oil and gas industries including lower carbon energy - Specific requirements for offshore structures - Part 4: Geotechnical design considerations*. 3rd edition.
10. <a id="ref-kallehave2012"></a>Kallehave, D., LeBlanc Thilsted, C. and Liingaard, M. A. (2012). "Modification of the API p-y formulation of initial stiffness of sand." *7th International Conference on Offshore Site Investigation and Geotechnics*, London, 465-472.
11. <a id="ref-kim2004"></a>Kim, B. T., Kim, N. K., Lee, W. J. and Kim, Y. S. (2004). "Experimental load-transfer curves of laterally loaded piles in Nak-Dong River sand." *Journal of Geotechnical and Geoenvironmental Engineering*, 130(4), 416-425. <https://doi.org/10.1061/(ASCE)1090-0241(2004)130:4(416)>
12. <a id="ref-kirkwood2016"></a>Kirkwood, P. B. (2016). *Cyclic lateral loading of monopile foundations in sand*. PhD thesis, University of Cambridge.
13. <a id="ref-klinkvort2013"></a>Klinkvort, R. T. and Hededal, O. (2013). "Lateral response of monopile supporting an offshore wind turbine." *Proceedings of the Institution of Civil Engineers - Geotechnical Engineering*, 166(2), 147-158. <https://doi.org/10.1680/geng.12.00033>
14. <a id="ref-leblanc2010"></a>LeBlanc, C., Houlsby, G. T. and Byrne, B. W. (2010). "Response of stiff piles in sand to long-term cyclic lateral loading." *Géotechnique*, 60(2), 79-90. <https://doi.org/10.1680/geot.7.00196>
15. <a id="ref-li2014"></a>Li, W., Igoe, D. and Gavin, K. (2014). "Evaluation of CPT-based p-y models for laterally loaded piles in siliceous sand." *Géotechnique Letters*, 4(2), 110-117. <https://doi.org/10.1680/geolett.14.00021>
16. <a id="ref-liu2025"></a>Liu, Z., Zhang, Y. and Guo, P. (2025). "A CPT-based p-y model for laterally loaded monopiles in sand." *Marine Structures*, 101, 103767. <https://doi.org/10.1016/j.marstruc.2024.103767>
17. <a id="ref-mcadam2020"></a>McAdam, R. A., Byrne, B. W., Houlsby, G. T., Beuckelaers, W. J. A. P., Burd, H. J., Gavin, K. G., Igoe, D. J. P., Jardine, R. J., Martin, C. M., Muir Wood, A., Potts, D. M., Skov Gretlund, J., Taborda, D. M. G. and Zdravković, L. (2020). "Monotonic laterally loaded pile testing in a dense marine sand at Dunkirk." *Géotechnique*, 70(11), 986-998. <https://doi.org/10.1680/jgeot.18.PISA.004>
18. <a id="ref-mcclelland1956"></a>McClelland, B. and Focht, J. A. (1956). "Soil modulus for laterally loaded piles." *Journal of the Soil Mechanics and Foundations Division*, ASCE, 82(SM4), 1-22.
19. <a id="ref-novello1999"></a>Novello, E. A. (1999). "From static to cyclic p-y data in calcareous sediments." *Proceedings of the 2nd International Conference on Engineering for Calcareous Sediments*, 17-27.
20. <a id="ref-oneill1983"></a>O'Neill, M. W. and Murchison, J. M. (1983). *An evaluation of p-y relationships in sands*. Report to the American Petroleum Institute, University of Houston.
21. <a id="ref-reese1974"></a>Reese, L. C., Cox, W. R. and Koop, F. D. (1974). "Analysis of laterally loaded piles in sand." *Offshore Technology Conference*. <https://doi.org/10.4043/2080-MS>
22. <a id="ref-scott1980"></a>Scott, R. F. (1980). *Analysis of centrifuge pile tests: simulation of pile driving*. Research Report, OSAPR Project 13, American Petroleum Institute.
23. <a id="ref-sorensen2010"></a>Sørensen, S. P. H., Ibsen, L. B. and Augustesen, A. H. (2010). "Effects of diameter on initial stiffness of p-y curves for large-diameter piles in sand." *Numerical Methods in Geotechnical Engineering*, 907-912.
24. <a id="ref-suryasentana2014"></a>Suryasentana, S. K. and Lehane, B. M. (2014). "Numerical derivation of CPT-based p-y curves for piles in sand." *Géotechnique*, 64(3), 186-194. <https://doi.org/10.1680/geot.13.P.026>
25. <a id="ref-suryasentana2016"></a>Suryasentana, S. K. and Lehane, B. M. (2016). "Updated CPT-based p-y formulation for laterally loaded piles in cohesionless soil under static loading." *Géotechnique*, 66(6), 445-453. <https://doi.org/10.1680/jgeot.15.P.156>
26. <a id="ref-taborda2020"></a>Taborda, D. M. G., Zdravković, L., Potts, D. M., Burd, H. J., Byrne, B. W., Gavin, K. G., Houlsby, G. T., Jardine, R. J., Liu, T., Martin, C. M. and McAdam, R. A. (2020). "Finite-element modelling of laterally loaded piles in a dense marine sand at Dunkirk." *Géotechnique*, 70(11), 1014-1029. <https://doi.org/10.1680/jgeot.18.PISA.006>
27. <a id="ref-wang2022rotation"></a>Wang, H., Lehane, B. M., Bransby, M. F., Askarinejad, A., Wang, L. Z. and Hong, Y. (2022). "A simple rotational spring model for laterally loaded rigid piles in sand." *Marine Structures*, 84, 103225. <https://doi.org/10.1016/j.marstruc.2022.103225>
28. <a id="ref-wang2023"></a>Wang, H., Lehane, B. M., Bransby, M. F., Wang, L. Z., Hong, Y. and Askarinejad, A. (2023). "Lateral behavior of monopiles in sand under monotonic loading: insights and a new simple design model." *Ocean Engineering*, 278, 114334. <https://doi.org/10.1016/j.oceaneng.2023.114334>
29. <a id="ref-wiemann2004"></a>Wiemann, J., Lesny, K. and Richwien, W. (2004). "Evaluation of pile diameter effects on soil-pile stiffness." *7th German Wind Energy Conference (DEWEK)*.
30. <a id="ref-zhang2024"></a>Zhang, X., Zou, D., Liu, J., Chen, K., Li, X. and Wang, T. (2024). "A developed soil reaction model for large-diameter monopiles in sand based on hyperbolic curves." *Computers and Geotechnics*, 172, 106468. <https://doi.org/10.1016/j.compgeo.2024.106468>
31. <a id="ref-zhu2016"></a>Zhu, B., Li, T., Xiong, G. and Liu, J. C. (2016). "Centrifuge model tests on laterally loaded piles in sand." *International Journal of Physical Modelling in Geotechnics*, 16(4), 160-172. <https://doi.org/10.1680/jphmg.15.00029>
