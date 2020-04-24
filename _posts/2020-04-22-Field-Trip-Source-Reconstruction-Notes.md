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

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjc1NjY3OTU4LC01NTMzODk2LC0xNTUwMz
E0NDQyXX0=
-->