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

Brain signal is not stationary. That's why we need time-frequenct analysis. There is a trade off between time resolution and frequency resolution. In general, if you want a better frequency resolution, you end up with a worse time resolution.

![Time frequency image](https://lh3.googleusercontent.com/33GId_NrnktLl2k62MvimVrHWP6Uc-V9Yji10_dpB9p8pkJ9Aw6vk7b6wAipPrLRvnCYmpm2sAZksST6OhYZ9Af3JP7_YjlWM0HG6DSTdcWdYEv6HP8koISs3fkRHgoIJKh16qM85YFzY2sd6IMQ-k47Fvf1yItIYiDZNl9zb3K2IiMJ1wVKdn5pOVhY2zkoFdGwkm9xkpfQNocftDjMNn4JrOgYzNknGY1pqbEzjGrh9-STIRw7Sdqdz_sADHrbrShKs265Zx0UpI7iV9MlxO37463taOs9aIRCp1O4U741DiYFLLh1kOFw1rDMn5VRMchUfUiDTq3jI6BoLRQ3ncaLiuJQ0487o0ZOuLwE8pIl3D6iuiS44ND5atx46mH3My-ieD3MEiV-0xDpDMBA-nYaD73QfcWQCLFoT8ZxRP08pv3HyRUKJeHqe89hkDijjZ464z7m8hXcpuxyx2MX54ek8dkYKMkogK76AQV6d1qpQE_woNZwT_FyTDR3fUFYzSuSu1bYq88MDGRan3vdpBNYqrMEG8v4UfEtnxPMQQ_vdsjp_XRHyxdQKNZgcbhnS7lG-VZgeG6hoiv6kO8ZcpS9fiQyi0iNfyHhq4zGgrkXYphZ1MNdinpkTnUSJvJxDZYuajN0LJ-gAzsPmx92vU8CipjDqQVV8WafCajp3yfxxCbSxm7q9YL5LqbX=w1840-h1312-no)


Wavelet is similar to Fourier, by applying convolution of wavelet components that capture different frequencies. A wavelet is a sine or cosine wave convolve with a taper. The only parameters that we can tune is the length of the wavelet - the number of cycles we use in the wavelet signal, usually use 5 (3 for lower frequencies and 7)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk3OTgyMjEyNiwxMzM2NDk3NjQ1LDEzOD
g1MjU1MjAsLTIwODYxMTIzMDIsLTk4NTUxNTg2LC0yMDAwNTM0
NzkzXX0=
-->