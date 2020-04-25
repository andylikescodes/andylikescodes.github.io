---
layout: post
title: Fieldtrip Neuronal Oscillation and Synchrony
tag: [Fieldtrip]
category: Brain
---

Notes for the tutorial: [Fieldtrip Neuronal Osciallation and Synchrony](https://www.youtube.com/watch?v=dHTuzMsjVJA&list=PLbVcEw60xnKNSXSKMAoBpTJ9BFFnxw21p&index=2)

Different tapers have different leakage profile. The simplest taper is a box taper, which cut offs everything for some specific values and only leave the values within a certain range. The leakage profile for the box taper is pretty bad - many frequencies near the target frequency are contributing to the power. A Hanning taper or Gaussian taper is attenuating the the contribution of the frequencies further away (side lobes) from the target frequency while having a wider main lobe.

A multitaper method is applied to smooth the frequency power

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwODYxMTIzMDIsLTk4NTUxNTg2LC0yMD
AwNTM0NzkzXX0=
-->