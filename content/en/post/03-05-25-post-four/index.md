---
title: Report on the fourth stage of the project
date: 2025-05-16
url_pdf: 'https://disk.yandex.ru/i/VXuhQ8-fUyCauw'
---

In this news, we will talk about the implementation of the fourth stage of our project.

Protection of the fourth stage:

<iframe width="720" height="405" src="https://rutube.ru/play/embed/c23ce537d2aaf99c68723148891e6ccf/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

<!--more-->

## 1. Introduction  
In this paper, the dynamics of a three-massive oscillatory circuit with harmonic and weakly anharmonic interactions is analyzed. The main goal is to discuss what physical conclusions numerical experiments provide and to what extent they are consistent with the theory of normal modes and the behavior of Fermi–Pasta–Ulam systems.

---

## 2. Setting the task  
System: three masses (m=[1,2,1]) connected by stiffening springs (k=[1,1,1,1]), the initial conditions are set by displacements and velocities.  
The task is to obtain a time series of displacements and velocities, construct a spectrum and phase trajectories, and then interpret the physical meaning of the observations.

---

## 3. Methodology  

- Solving equations of motion in normal coordinates;  
- Fast Fourier transform for spectral analysis;  
- Visualization of time series and phase trajectories in Julia.

---

## 4. Analysis of the results  

- **Natural frequencies and normal modes**  
  The calculated frequencies clearly coincided with the theory of the linear circuit, which confirms the correctness of the model.  

- **Spectral peaks**  
  Pronounced peaks at natural frequencies are observed in the FFT spectra, which indicates the dominant contribution of individual modes to the overall dynamics.

- **Energy distribution**  
  In the harmonic mode, energy is conserved in initially excited modes, whereas in anharmonic interactions, there is a gradual redistribution of energy between modes and manifestations of quasi-periodicity.

- **Phase trajectories**  
  The graphs of phase trajectories show well–ordered ellipses in the linear case and complicated, "blurring" trajectories under FPU perturbations, which reflects poor sensitivity to initial conditions.

---

## 5. Conclusion  

The discussion showed that the numerical approach in Julia reliably reproduces classical normal modes and effectively identifies nonlinear effects of FPU systems. This opens up opportunities for further study of the dynamics of more complex link chains and nonlinear oscillatory systems.