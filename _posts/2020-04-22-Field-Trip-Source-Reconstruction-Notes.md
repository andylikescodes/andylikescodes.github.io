---
layout: post
title: Fieldtrip Source Reconstruction Notes
tag: [Brain]
category: Brain
---

Notes for the tutorial: [Source reconstruction using beamforming techniques](https://www.youtube.com/watch?v=pE0WAKd_Ve4)

Source reconstruction methods:

1. Single and multiple (point like) dipole models
	- Assume a small number of sources
	- Where (& how many) are strongest source

2. Distributed dipole models
	- Assume activity everywhere
	- What is the distribution of activity over the brain

3. Spatial filtering
	- Assume that the time-courses of different sources are uncorrelated
	- What is the amount of activity at a given brain location

Use multitapers to smooth the frequency spectrum, and get the targeted time window and the frequency range. Multitapering - increase frequency smoothing without changing length time window.

The beamformer (LCMV & DICS) are source localization methods for time domain signals and frequency domain signals using spatial filtering. This method estimate the source activity on every point of a grid, find a matrix that maximize the variance of the target source point and minimize that for the others. (Will need to follow up with the original papers for LCMV and DICS).



<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA0NTQwNjQ0NywyNzU2Njc5NTgsLTU1Mz
M4OTYsLTE1NTAzMTQ0NDJdfQ==
-->