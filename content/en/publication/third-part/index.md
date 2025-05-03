---
title: "Stage 3. Description of the software implementation of the Oscillation Chain project"
authors:
- admin
date: "2025-05-02T00:00:00Z"
doi: ""
publishDate: "2025-05-02T00:00:00Z"
publication_types: 'article'
publication: ""
publication_short: ""
abstract: |

   In this paper, we consider the development and software implementation of a method for modeling oscillatory chains in the Julia language. The aim of the study was to study the dynamics of a three-massive system consisting of three links with spring stiffness k = [1,1,1,1] and mass m= [1,2,1], as well as to visualize its main characteristics: displacements, velocities, phase trajectories and spectral densities of vibrations.

   The main stages of the work include:

   1. Construction of the Omega stiffness matrix and calculation of its eigenvalues and vectors.
   2. Solving equations in normal coordinates to determine the amplitudes C and phases alpha of each normal oscillation.
   3. Calculation of time dependences of displacements X(t) and velocities V(t) on a uniform grid of 2^13 points in the interval t ∈ [0, 80].
   4. Visualization of the received data:
    - graphs of displacements X(t) and velocities V(t) as functions of time;
    - phase trajectories for each of the three bodies;
    - spectral density of oscillations using FFT.

   The results obtained are in good agreement with the theoretical predictions of normal oscillation modes: the amplitude-phase relations and spectral peaks visible on the graphs correspond to the natural frequencies of the system. This confirms the correctness of the developed algorithm and the implemented software package.

   **Keywords:** oscillatory chains, normal oscillations, eigenvalues, phase trajectory, spectral density, Julia.    

   <iframe width="720" height="405" src="https://rutube.ru/play/embed/323bd636ba9f2daa3eba7c696f1003d4/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

summary: |
  This paper presents a numerical method for modeling a three-massive oscillatory chain in the Julia language. The study includes constructing a stiffness matrix, calculating its eigenvalues and vectors, as well as solving for the amplitudes and phases of normal modes. The time dependences of the displacements and velocities in the interval \(t\in [0.80]\) with \(2^{13}\) points were calculated. To analyze the dynamics of the system, time series graphs, phase trajectories, and spectral densities are constructed using the fast Fourier transform. The obtained natural frequencies and forms of normal oscillations are in good agreement with the theory, which confirms the correctness of the developed algorithm.
tags:
- Source Themes
featured: false
links:
- name: GitHub source
  icon: github
  icon_pack: fab
  link: https://github.com/daBorovikov/study_2024-2025_mathmod
url_pdf: 'https://disk.yandex.ru/i/0EzTp67-MOxFhQ'
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
1. [Introduction](#1-introduction)
2. [Task statement](#2-task statement)
3. [Methodology](#3-Methodology)
4. [Implementation description](#4-Implementation description)
5. [Results](#5-Results)
6. [Conclusion](#6-conclusion)  
7. [List of references](#7-list-of-references)  

## 1. Introduction

Oscillatory chains of connected masses and springs are a classical model in mechanics and solid state physics. Their study makes it possible to understand the properties of normal modes, dispersion, and resonance phenomena [1-3]. The aim of the work is to develop a software package for numerical modeling and visualization of the dynamics of a three-massive chain.

---

## 2. Setting the task

1. System parameters:
- Number of masses N = 3
- Masses m = [1, 2, 1]
- Spring stiffness k = [1, 1, 1, 1]
- Initial displacements R0 = [-0.2, 0, -0.3]
- Initial velocities v0 = [1, -3, 0]

2. Requirements:  
   - Construct a tridiagonal matrix Ω  
   - Find the eigenvalues of ωα^2 and the vectors Aa
- Determine the amplitudes Ca and phases φα
- Calculate Xi(t) and ẊI(t) on a grid of 2^13 points on t ∈ [0, 80]  
   - Visualize the key result — the time dependence of the displacement of the second body

---

## 3. Methodology

### 3.1 Stiffness matrix Ω  
The elements of the Ω matrix are given as:  
Ω(i,i) = (k_i + k_{i+1}) / m_i  
Ω(i,i+1) = -k_{i+1} / m_i  
Ω(i,i-1) = -k_i / m_i

### 3.2 Eigenvalues and vectors  
The problem is solved  
Ω * Aα = ωα^2 * Aα

### 3.3 Amplitudes and phases  
The system of equations for vector coefficients C1 and C2 in the initial state:
C1 * A = R0  
C2 * A = Ẋ(0)  
Then  
Cα = sqrt(C1_α^2 + C2_α^2)  
φα = atan2(C2_α, C1_α)

### 3.4 The Timing Grid  
t_j = (j - 1) / (2^13 - 1) * 80,  j = 1,…,2^13  
And the laws of motion:
Xi(t) = Σα Ca * Aa(i) * cos(ωα * t + φα)  
Ẋi(t) = -Σα Cα * ωα * Aα(i) * sin(ωα * t + φα)

---

## 4. Description of the implementation

The program for Julia includes:  
- Initialization of N, m, k, R0, v0  
- Construction of the W matrix  
- Calculation of the eigenvalues of ωα^2 and the vectors Α via eigen(Ω)  
- Solution for C1 and C2, calculation of Ca and φa  
- Generation of the time series Xi(t) and ẊI(t)  
- Plotting the displacement of the second body

---

## 5. Results

** Time dependence of displacement of bodies**
![Displacement of the second body in time](graph_1.png)
The graph shows how the displacement of the three links changes over time t ∈ [0, 80]. Characteristic fluctuations with a complex character are visible, due to the superposition of three normal modes.

---

##6. Conclusion

The developed algorithm and its implementation in the Julia language make it possible to effectively study the dynamics of an oscillatory system. The simulation results correspond to theoretical predictions, which confirms the correctness of the approach. Possible expansion directions:
- N > 3 masses  
- consideration of damping and external influences  
- modeling of uneven and periodic structures

---

## 7. List of literature

1. D. A. Medvedev and others. *Simulation of physical processes and phenomena on a PC*. Novosibirsk: NSU, 2010  
2. Getmanova E. G., Kostarev D. B. *Resonant phenomena in oscillator systems*, 2001  
3. Andronov A. A., Witt A. A. *Theory of oscillations*. Moscow: FIZMATLIT, 1981
``