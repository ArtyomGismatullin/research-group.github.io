---
title: Report on the third stage of the project
date: 2025-05-03
url_pdf: 'https://disk.yandex.ru/i/0EzTp67-MOxFhQ'
---

In this news, we will talk about the implementation of the third stage of our project.

Protection of the third stage:

<iframe width="720" height="405" src="https://rutube.ru/play/embed/323bd636ba9f2daa3eba7c696f1003d4/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

<!--more-->

# Introduction  
Numerical simulation of oscillatory chains remains a key tool in mechanics, solid state physics, and radiophysics. Unlike analytical solutions, which are applicable only to special cases (homogeneous or periodic chains), numerical methods allow us to study systems with arbitrary parameters.

### Method and implementation  
In this paper, we have developed a software package in the Julia language for modeling a three-massive chain with the following parameters:
- masses m = [1, 2, 1]  
- spring stiffness k = [1, 1, 1, 1]  
- initial conditions R₀ = [-0.2, 0, -0.3], v₀ = [1, -3, 0]  

Main stages:  
- Construction of a tridiagonal stiffness matrix Ω and solution of the problem Ω·Aₐ = ωₐ2·aₐ  
- Calculation of the amplitudes Cₐ and phases φₐ from the initial state  
- Generation of time series xᵢ(t), vᵢ(t) on a grid of 213 points in the interval t ∈ [0, 80]  
- Visualization: graph of the displacement of the second link, phase portrait and spectral density via FFT  

### Results  
- The displacement graph of the second body clearly shows fluctuations caused by the superposition of three normal modes.  
- Spectral analysis showed bright peaks at natural frequencies ω₁, ω₂, ω₃, which confirms the correctness of the algorithm.

### Prospects  
The technique can be extended to chains with N > 3, taking into account damping and external influences, and also applied in educational courses in computational physics and engineering modeling.