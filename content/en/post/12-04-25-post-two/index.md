---
title: Report on the second stage of the project
date: 2025-04-11
url_pdf: 'https://docs.yandex.ru/docs/view?url=ya-disk%3A%2F%2F%2Fdisk%2Freport-2.pdf&name=report-2.pdf&uid=641931395'
---

In this news, we will talk about the implementation of the second stage of our project.

Protection of the second stage:

<iframe width="720" height="405" src="https://rutube.ru/play/embed/323bd636ba9f2daa3eba7c696f1003d4/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

<!--more-->

# Introduction  
Linear chain models [1] consisting of a finite or infinite number of coupled oscillators are widely used in various fields of physics.:  
- Solid state physics,  
- Physics of continuous media,
- Chemical Physics,  
- Radiophysics [2].  

For example, in [1] a system of three connected electric oscillatory circuits is described as a chain of three masses m(1), m(2), m(3) connected by springs of the same stiffness k. Such models allow us to study wave processes in a natural way, introducing key concepts.:  
- Wavelength,  
- Group and phase velocity [3],  
- The variance.  

### Features of analytical solutions  
For long linear chains (N > 3), analytical solutions can be obtained only in a limited number of cases [2]:
1. **A homogeneous chain**:  
   k(0) = k(1) = ... = k(N-1),  
   m(0) = m(1) = ... = m(N-1).  

2. **Periodic stiffness of springs**:
k(0) = k(2) = k(4) = ...,
k(1) = k(3) = k(5) = ...,
m(i) = const.  

3. **Mass alternation**:
k(i) = const,
m(0) = m(2) = m(4) = ...,
m(1) = m(3) = m(5) = ....  

4. **Exponential change in stiffness**:
k(i) = k* w_k^N,
m(i) = const.  

5. **Exponential change of masses**:
k(i) = const,
m(i)= m* w_m^(N-1).  

However, even for these cases, the solutions become extremely cumbersome as N increases, which requires the use of computer modeling to analyze them.  

### Significance of the study  
The study of linear chains remains relevant in educational courses on physics and computational methods. Nevertheless, the limitations of analytical approaches emphasize the importance of numerical methods that make it possible to study the dynamics of systems with arbitrary parameters.