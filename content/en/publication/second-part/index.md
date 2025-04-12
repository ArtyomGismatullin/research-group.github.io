---
title: "The second stage of the project. Theoretical description of the problem. Description of the model."
authors:
- admin
date: "2025-04-11T00:00:00Z"
doi: ""
publishDate: "2025-04-11T00:00:00Z"
publication_types: 'article'
publication: ""
publication_short: ""
abstract: |
The paper presents an algorithm for studying the oscillations of linear chains of coupled oscillators. Based on the matrix approach, a method for solving the system of equations of motion has been developed, including:
1. Constructing a tridiagonal matrix of coefficients,
2. Finding natural frequencies and vectors of normal oscillations,  
  3. Restoration of the general solution as a superposition of modes.  

  Special attention is paid to:
1. **Analytical constraints**: solutions for long chains (N > 3) exist only in special cases (homogeneous, periodic systems).  
  2. **Numerical methods**: the algorithm includes solving systems of linear equations for initial conditions and phase analysis.  
  3. **Of practical importance**: the models are applicable in solid state physics, radiophysics and other fields.  

  Results:
- Expressions for the laws of mass motion through a superposition of normal oscillations are obtained.  
  - A step-by-step algorithm has been developed that allows analyzing systems with arbitrary parameters (mass, stiffness).  

  The work demonstrates the connection between theoretical mechanics and computational methods, which is relevant for educational courses and applied research.  

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
url_pdf: 'https://docs.yandex.ru/docs/view?url=ya-disk%3A%2F%2F%2Fdisk%2Freport-2.pdf&name=report-2.pdf&uid=641931395'
url_code: 'https://github.com/daBorovikov/study_2024-2025_mathmod/releases/tag/v1.3.1'
url_project: ''
url_slides: ''
url_source: 'https://docs.yandex.ru/docs/view?url=ya-disk-public%3A%2F%2Fb8Nq4N8dwaj%2FoqClBOxGaevtLqpQ4BsQlPlp6PTDqZRwJE%2FVhWQcp5XGYGI7CD4Eq%2FJ6bpmRyOJonT3VoXnDag%3D%3D&name=%D0%9C%D0%B5%D0%B4%D0%B2%D0%B5%D0%B4%D0%B5%D0%B2_%D0%94_%D0%90_%D0%9C%D0%BE%D0%B4%D0%B5%D0%BB%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D1%84%D0%B8%D0%B7%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D1%85_%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%BE%D0%B2_%D0%B8_%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9_%D0%BD%D0%B0_%D0%9F%D0%9A.pdf&nosw=1'
url_video: 'https://rutube.ru/video/private/3bafd7b3ae7888790f9bf919f33856d3/?p=fdtwcqBuCpg3OX7mNvfFvA'
image:
projects:
- internal-project
slides: example

---

# Content  
1. [Introduction](#1-Introduction)  
2. [Equations of motion](#2-equations of motion)
3. [General solution](#3-general solution)
4. [Algorithm of solution](#4-algorithm of solution)
5. [Conclusion](#5-conclusion)
6. [References](#6-references)  

---

## 1. Introduction  
Linear chain models [1], consisting of a finite or infinite number of coupled oscillators, are used in:  
- Solid state physics,  
- Continuum Physics,
- Chemical Physics,  
- Radiophysics [2].  

Example: a system of three masses m(1), m(2), m(3) connected by springs of stiffness k simulates three electrical circuits [1]. Such models allow us to study:  
- Wavelength,  
- Group/phase velocity [3],  
- The variance.  

### Features of analytical solutions  
For chains with N > 3, solutions exist only in special cases [2]:
1. **Homogeneous chain**:
k(0) = k(1) = ... = k(N-1),
m(0) = m(1) = ... = m(N-1).
2. **Periodic rigidity**:  
   k(0) = k(2) = ..., k(1)=k(3) = ...,
m(i) = const.
3. **Mass alternation**:
k(i) = const,
m(0) = m(2) =..., m(1) = m(3) = ....  

---

## 2. Equations of motion  
The system of equations for masses:
``
m(0)*x"(0) = -k(0)*x(0) - k(1)*(x(0)-x(1))
m(i)*x"(i) = -k(i)*(x(i)-x(i-1)) - k(i+1)*(x(i)-x(i+1)), i=1,...,N-2
m(N-1)*x"(N-1) = -k(N-1)*(x(N-1)-x(N-2)) - k(N)*x(N-1)  
```

In matrix form:
``
B * A = 0  
``
where **B** is a tridiagonal matrix:
- B(0,0) = -w^2 + w(00)^2 + w(10)^2
- B(i,i) = -w^2 + w(ii)^2 +w(i+1,i)^2  
- B(i,i±1) = -ω(ii)^2 or -ω(i+1,i)^2  

**Characteristic equation**:
``
det(B) = 0 → ω(ij)^2 - ω^2 =0  
```

---

## 3. The general solution  
The solution of the system is a superposition of normal oscillations:
`
x(t) = Σ C(α)*A(α)*cos(ω(α)*t + φ(α))  
```
Velocities:
``
x'(t) = -Σ C(α)*ω(α)*A(α)*sin(ω(α)*t + φ(α))  
```

**Initial conditions**:
``
x(0)= Σ C(α)*A(α)*cos(φ(α))
x'(0) = -Σ C(α)*ω(α)*A(α)*sin(φ(α))  
```

The phases φ(α) are calculated using:
``
φ(α) = arctan(C(α)/Cv(α))
``
taking into account the quadrants (see the rules for angle selection [3]).

---

## 4. The solution algorithm  
1. Set N, m(i), k(i).
2. Construct the matrix B.  
3. Find the eigenvalues of ω(α)^2 and the vectors A(α).
4. Solve the systems:
``
   M*C1 = x(0)  
   Mv*C2 = x'(0)  
   ```  
5. Calculate C(α) = sqrt(C1(α)^2 + C2(α)^2).  
6. Determine the phases φ(α).
7. Write down the laws of motion.  

---

## 5. Conclusion  
An algorithm for solving the problem of chain oscillations has been developed, including:  
- Building a matrix model,  
- Natural frequency analysis,  
- Restoration of the laws of motion through the superposition of modes.  

---

## 6. The list of references  
1. D.A. Medvedev and others. *Modeling of physical processes*. Novosibirsk: NSU, 2010.
2. Getmanova E.G., Kostarev D.B. *Resonant phenomena in oscillator systems*. 2001.
3. Andronov A.A., Witt A.A. *Theory of oscillations*. Moscow: FIZMATLIT, 1981.  
```