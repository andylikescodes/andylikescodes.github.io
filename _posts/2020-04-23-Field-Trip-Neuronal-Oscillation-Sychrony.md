---
layout: post
title: Fieldtrip Neuronal Oscillation and Synchrony
tag: [Fieldtrip]
category: Brain
---

Notes for the tutorial: [Fieldtrip Neuronal Osciallation and Synchrony](https://www.youtube.com/watch?v=dHTuzMsjVJA&list=PLbVcEw60xnKNSXSKMAoBpTJ9BFFnxw21p&index=2)

Different tapers have different leakage profile. The simplest taper is a box taper, which cut offs everything for some specific values and only leave the values within a certain range. The leakage profile for the box taper is pretty bad - many frequencies near the target frequency are contributing to the power. A Hanning taper or Gaussian taper is attenuating the the contribution of the frequencies further away (side lobes) from the target frequency while having a wider main lobe.

A multitaper method is applied to smooth the frequency power ususally used in more high frequency range. It can smooth the high frequency powers that usually contain high variance across trials and hard to obtain statistical significance. The smoothing smooth a single frequency into a range of frequency, e.g., if our target frequency is 30Hz, then a 8 taper smoothing frequency gives a frequency range from 22Hz to 38Hz. ()

<!--stackedit_data:
eyJoaXN0b3J5IjpbNDQxMTEyNDI4LC0yMDg2MTEyMzAyLC05OD
U1MTU4NiwtMjAwMDUzNDc5M119
-->