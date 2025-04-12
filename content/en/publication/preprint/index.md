---
title: "The first presentation of the project. Theoretical description of the problem. Description of the model."
authors:
- admin
date: "2025-03-22T00:00:00Z"
doi: ""
publishDate: "2025-03-22T00:00:00Z"
publication_types: 'article'
publication: ""
publication_short: ""
abstract: |
  At the first stage of the project, a model of vibrations of one-dimensional chains of particles is investigated within the framework of mathematical modeling. A harmonic chain (a linear model with independent modes, standing waves, and dispersion relations) and an anharmonic chain (a nonlinear model of the Fermi-Pasta-Ulama problem) are theoretically described. In the latter, a nonlinear term is introduced, leading to the absence of thermalization of energy and quasi-periodic behavior of the system. The main scientific problem is to identify the conditions for the transition to thermal equilibrium, including the influence of the number of particles, the magnitude of the nonlinearity and the initial conditions. The Fourier transform is used for the analysis, which makes it possible to study the spectral distribution of energy. The results of the stage emphasize the fundamental difference between linear and nonlinear systems, and also raise questions for further study of the dynamics of complex oscillatory systems.

  <iframe width="720" height="405" src="https://rutube.ru/play/embed/323bd636ba9f2daa3eba7c696f1003d4/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

summary: |
  Linear (harmonic) and nonlinear (anharmonic) models of chain oscillations are investigated. The harmonic system retains independent modes, in the anharmonic (FPU) energy is not thermalized, quasi-periodicity is revealed. The main problem is the conditions of transition to thermal equilibrium.
tags:
- Source Themes
featured: false
links:
- name: GitHub source
  icon: github
  icon_pack: fab
  link: https://github.com/daBorovikov/study_2024-2025_mathmod
url_pdf: 'https://docs.yandex.ru/docs/view?url=ya-disk-public%3A%2F%2F%2B6JZgzZNwCMQwpL0fkeHyhtUlAzwad0jdVQiTnKdHkcK6ST5Axj2mbX0KfHOtZRKq%2FJ6bpmRyOJonT3VoXnDag%3D%3D&name=report.pdf&nosw=1'
url_code: 'https://github.com/daBorovikov/study_2024-2025_mathmod/releases/tag/v1.3.1'
url_project: ''
url_slides: ''
url_source: 'https://docs.yandex.ru/docs/view?url=ya-disk-public%3A%2F%2Fb8Nq4N8dwaj%2FoqClBOxGaevtLqpQ4BsQlPlp6PTDqZRwJE%2FVhWQcp5XGYGI7CD4Eq%2FJ6bpmRyOJonT3VoXnDag%3D%3D&name=%D0%9C%D0%B5%D0%B4%D0%B2%D0%B5%D0%B4%D0%B5%D0%B2_%D0%94_%D0%90_%D0%9C%D0%BE%D0%B4%D0%B5%D0%BB%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D1%84%D0%B8%D0%B7%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D1%85_%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%BE%D0%B2_%D0%B8_%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9_%D0%BD%D0%B0_%D0%9F%D0%9A.pdf&nosw=1'
url_video: 'https://rutube.ru/video/private/323bd636ba9f2daa3eba7c696f1003d4/?p=YUrzDpB0l5eOgbdXS0oiZQ'
image:
projects:
- internal-project
slides: example
---

# Theoretical description of the model

##1. Harmonic Chain

### Basic provisions
- **N particles** with a mass of **m**, connected by springs of stiffness **k**.  
- The extreme particles are fixed → **N + 1 springs** (length **d**).  
- Equilibrium positions:
``x(i) = i·d (i = 1, 2, ..., N)``  
- Offsets: **y(i)** (assumed **y(i) << d**).

---

### Equations of motion
**Force for the ith particle**:
``F i = k·(y(i+1) - 2·y(i) + y(i-1))``

**Differential equation**:
``m·d2y(i)/dt2 = k·(y(i+1) - 2·y(i) + y(i-1))``

**Total energy**:
``U = (m/2)·Σ(dy(i)/dt)2 +(k/2)·Σ(y(i) - y(i-1))2``

---

### Solution: Standing waves
**Particle displacements**:
``y(i) = B·sin(p·x(i))·cos(ω·t)```

**Boundary conditions**:
- ``y(0) = 0``, `` y(N+1) = 0``  
- Acceptable wave numbers:
``p(l) = l·π / [(N + 1)·d] (l = 1, 2, ..., N)``

**Dispersion relation**:
``w(l) = 2·w(0)·sin(l·π / [2·(N + 1)]), ω(0) = sqrt(k/m)```

---

## 2. Anharmonic chain (Fermi-Pasta-Ulama problem)

### The nonlinear model
**Force with an anharmonic term**:
``F = -k·x·(1 - α·x/d)``  
(**α** is the coefficient of nonlinearity).

**Potential energy**:
``U = (k/2)·Σ(y(i) - y(i-1))2 - (k·α)/(3·d)·Σ(y(i) - y(i-1))3``

---

### Key results
1. **Lack of thermalization**:
- Energy is not distributed between modes (for **N = 32** modes **l > 5** received **< 1%** of energy).  
   - **Quasi-periodicity**: return to the initial state after **~160 periods**.  

2. **Superperiodicity**:
- Recovery of **98% of energy** over long time intervals.  

---

##3. The scientific problem

**Goal**:  
Study of the conditions of transition to thermal equilibrium in oscillatory systems.

**Influencing factors**:
1. Number of particles (**N**).  
2. The level of nonlinearity (**α**).  
3. Initial conditions.  

**Methods of analysis**:  
- **Fourier transform** for spectral energy distribution.  
- Numerical simulation of mode dynamics.  

---

## 4. Conclusion of the stage
1. **Harmonic model**: Mode independence → absence of thermalization.  
2. **FPU problem**: Violation of classical expectations → quasi-periodicity.  
3. **Nonlinear effects**: Complex dynamics (superperiodicity).