---
layout: post
title: Fieldtrip Neuronal Oscillation and Synchrony
tag: [Fieldtrip]
category: Brain
---

Notes for the tutorial: [Fieldtrip Neuronal Osciallation and Synchrony](https://www.youtube.com/watch?v=dHTuzMsjVJA&list=PLbVcEw60xnKNSXSKMAoBpTJ9BFFnxw21p&index=2)

Different tapers have different leakage profile. The simplest taper is a Boxcar taper, which cut offs everything for some specific values and only leave the values within a certain range. The spectral leakage profile for the Boxcar taper is pretty bad - many frequencies near the target frequency are contributing to the power. A Hanning taper or Gaussian taper is attenuating the the contribution of the frequencies further away (side lobes) from the target frequency while having a wider main lobe.

A multitaper method is applied to smooth the frequency power ususally used in more high frequency range. It can smooth the high frequency powers that usually contain high variance across trials and hard to obtain statistical significance. The smoothing smooth a single frequency into a range of frequency, e.g., if our target frequency is 30Hz, then a 8 taper smoothing frequency gives a frequency range from 22Hz to 38Hz (still need to look into why this is the case). Multitapering is a common technique to control spectral leackage. 

For low frequency, using a Hanning taper is good enough. Using too many tapers will smooth all the important signals in lower frequencies. The example gives in the video is that from 1-30Hz, Hanning, from 30Hz and above, use 'dpss' multitapering.

Brain signal is not stationary. That's why we need time-frequenct analysis. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMzNjQ5NzY0NSwxMzg4NTI1NTIwLC0yMD
g2MTEyMzAyLC05ODU1MTU4NiwtMjAwMDUzNDc5M119
-->