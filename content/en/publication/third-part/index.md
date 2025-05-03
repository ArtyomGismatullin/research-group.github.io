---
title: "Stage 3. Description of the software implementation of the Oscillation Chain project"
authors:
- admin
date: "2025-05-2T00:00:00Z"
doi: ""
publishDate: "2025-05-02T00:00:00Z"
publication_types: 'article'
publication: ""
publication_short: ""
abstract: |
   In this paper, we consider the development and software implementation of a method for modeling oscillatory chains in the Julia language. The aim of the study was to study the dynamics of a three-massive system consisting of three links with spring stiffness (k=[1,1,1,1]) and mass(m=[1,2,1]), as well as to visualize its main characteristics: displacements, velocities, phase trajectories and spectral densities of vibrations 

   The main stages of the work include:
   1. Construction of the stiffness matrix Ω and calculation of its eigenvalues and vectors.  
   2. Solving equations using normal coordinates to determine the amplitudes(C) and phases(alpha) of each normal oscillation.  
   3. Calculation of time dependencies of offsets \(X(t)\) and speeds \(V(t)\) on a uniform grid of \(2^{13}\) points in the interval \(t\in[0.80]\).  
   4. Visualization of the received data:
   - Graphs of displacements and velocities as functions of time.  
   - Phase trajectories for each of the three bodies .  
   - Spectral density of oscillations using FFT. 

   The results obtained are in good agreement with the theoretical predictions of normal oscillation modes: the amplitude-phase relations and spectral peaks visible on the graphs correspond to the natural frequencies of the system. This confirms the correctness of the developed algorithm and the implemented software package.

   **Keywords:** oscillatory chains, normal oscillations, eigenvalues, phase trajectory, spectral density, Julia.

   <iframe width="720" height="405" src="https://rutube.ru/play/embed/323bd636ba9f2daa3eba7c696f1003d4/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

summary: |
  This paper presents a numerical method for modeling a three-mass oscillatory chain in the Julia language. The study includes constructing a stiffness matrix, calculating its eigenvalues and vectors, as well as solving for the amplitudes and phases of normal modes. The time dependences of the displacements and velocities in the interval \(t\in [0.80]\) with \(2^{13}\) points were calculated. To analyze the dynamics of the system, time series graphs, phase trajectories, and spectral densities are constructed using the fast Fourier transform. The obtained natural frequencies and forms of normal oscillations are in good agreement with the theory, which confirms the correctness of the developed algorithm.
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
url_video: 'https://rutube.ru/video/private/323bd636ba9f2daa3eba7c696f1003d4/?r=wd'
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