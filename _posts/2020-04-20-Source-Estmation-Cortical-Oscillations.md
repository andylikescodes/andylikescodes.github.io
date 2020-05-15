---
layout: post
title: Spactral Spatiotemporal Imaging of Cortical Oscillations
tag: [Paper Review]
category: Brain
---

This post is a summary of the paper: Spectral Spatiotemporal Imaging of Cortical Oscillations and Interactions in the Human Brain [(Lin et al., 2004)](https://www.zotero.org/google-docs/?pQbZyv)

  

A Computationally Efficient Source Estimation Algorithm that Localizes cortical oscillations and their phase relationships.

  

This paper proposed a method to do source estimation that localizes cortical oscillations and their phase relationships.

  

> (1) It creates a map of the cortical oscillations on the cortical surface
>
> (2) It is able to detect rapidly changing power and phase relations
>
> (3) It can combine prior information from other functional imaging techniques such as fMRI

  

The signal is firstly processed by a band-pass filter, then use a cortically constrained minimum norm estimate (MNE) that mentioned in a previous blog. The phase-locking value is also calculated using the source converted signal.

  

It is worth to mention that the source estimation algorithm here (the MNE) is demonstrated a lot more clear than the original paper (Hamalainen). 
>The source covariance matrix incorporates a priori assumption on the spatial distribution of the source currents... MNE is known to have a bias towards superficial currents, caused by the attenuation of the MEG lead fields with increasing source depth.

Therefore, a correction is made to scale the A matrix, the gain matrix, which is the solution of the free source orientation forward problem

>... thus having three columns for each source location, representing the solution according to each orthogonal direction.

After the wavelet transformation, the matrix obtained from source estimation is applied to each channel and the time-varying power and synchronization (PLV) can be computed. After complex wavelet transformation and applying the source estimation matrix, we get a time series of complex signals. The power is getting the amplitude of the complex signal. Here the source synchronization is done using a reference channel (seed method).

 
> ### Reference
>[Lin, F.-H., Witzel, T., Hämäläinen, M.S., Dale, A.M., Belliveau, J.W., Stufflebeam, S.M., 2004. Spectral spatiotemporal imaging of cortical oscillations and interactions in the human brain. NeuroImage 23, 582–595. https://doi.org/10.1016/j.neuroimage.2004.04.027](https://www.zotero.org/google-docs/?Svci2m)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAwMTYxNDcwNV19
-->