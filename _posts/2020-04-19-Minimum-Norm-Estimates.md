---
layout: post
title: Minimum Norm Estimates
tag: [Paper Review]
category: Brain
---

This post is a summary of the paper: Interpreting magnetic fields of the brain: minimum norm estimates [(Hämäläinen and Ilmoniemi, 1994)](https://www.zotero.org/google-docs/?jt8HpZ).
### Minimum Norm Estimates (MNE): One Way of Getting to the Source
# Getting to the Source

To work on the source space of MEG data, it is required that we have a good understanding of how source models work and how the signal in the sensor space is projected onto the source space. One of the basic algorithms for solving this inverse problem is Minimum Norm Estimates (MNE) [(Hämäläinen and Ilmoniemi, 1994)](https://www.zotero.org/google-docs/?1psagd).

The interesting question is how we are able to get to the source space from the sensor space. This classical inverse problem, unfortunately, does not have a unique solution; “there are infinite current distributions that can explain the measurements”, as says in the paper.

One potential method is to regularize or constrain the current distribution under some particular assumptions, such as limiting the source current in a small area (single dipole model) and in several sites (multi-dipole models). If these assumptions are not met, the result of the source current distribution might be incorrect.

The MNE method gives the best estimate for the current when minimal a priori information about the source is available. The mathematical details of how the final current distribution is derived are too complicated for me to understand no, but the main idea is to mathematically construct an equation between the magnetometer and primary-current distribution. To recover the primary-current distribution, one needs to find the lead field, which describes the sensitivity distribution of the magnetometers. The lead field depends on the conductivity, which is determined by the head model (spherically symmetric or horizontally layered conductor).

The equation shows that there are infinite solutions to the lead field; “any primary-current distribution (together with volume currents) to which the measuring instrument is not sensitive may be added to the solution.” Regularization also applied to improve stability.

![enter image description here](https://lh3.googleusercontent.com/en4bn7B1U70bjzY4jrkXdUrvY0WOikGDYsaM02GKrYCWg1aVaE9swr8c0gCyLPpigDXwrfmB494cGDHc2on9bogfrrvF7mrK7OuZdeLoXRL36iGSTXLodKqEcT_YkuT--AqwlsiMTBlINE4XKUYCEfTjR0iRsvK8YvOtadFRzUWRi4qOhMe3NRvVcU18eAu4GQir9pJd1ZwV6k39quPDc1mqyG4uKUXkemn_YdOy_tHC_8IJuQ3QSBx6hthUPOB_iVeMDpSrK7Jyn1xehblu5mBL9nIIuWnvH64vKnupKHSA5ZGu-_9rC3D8eoBW8tBY9GdG_RaETbTaUs9kL0U33WGvnSc0EgO-FbsveNvLmD1qJGwRTyydwGJ0o-e25Yf3hrs6XNfvjQGqbnnoM7Y-Kc5flb-aJ8fMs2g06of3jB4iEDEfLo8bRDeJCnDWMe1wN31uptRFPJcSe7wIY4RGLQl5qf7w7Tw1Ytr4o7QDExdGZB2Qnml-zTVA121ADYvlJzW-HjUSKJQYSN_OS0R89PPAFbLUv63k54uFTCQn7BRWMhsA-p4a7xSDwKOeOFecJDL4e6qp_CDbDiIlD9_8l49AjYBFC0qZkN8JDocZF_huqfLDfQf0C9Q139OHA3H4bdOEs5EsjCWzry3_vt9qB2UVLpKeEgOMtNs8FCYzi99GdYZxQeYGBSZfPSLw=w942-h1660-no)

The estimation of the primary-current distribution has direction and magnitude, as shown in the above image.

(Question remains to be answered) What still unclear to me is whether dipoles are different from the primary current distribution. My guess is that the later is what we really want to estimate, and using the single dipole assumption as the constrain to find a single solution.

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDA5ODI3ODE0LC0yMDk3Mzg1NTM4LDc2Mz
k4MzcyMiwzNjcwMTg1MDgsMTA0NDQ4ODk4MSwzMDgxNDI4OTQs
LTE4MDI0Mjc1MzksMTYxOTA0MTI5NV19
-->