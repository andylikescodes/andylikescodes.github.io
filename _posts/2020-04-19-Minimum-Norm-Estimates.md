---  
layout: post  
title: Interpreting Magnetic Fields of the Brain: Minimum Norm Estimates
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



The estimation of the primary-current distribution has direction and magnitude, as shown in the above image.

(Question remains to be answered) What still unclear to me is whether dipoles are different from the primary current distribution. My guess is that the later is what we really want to estimate, and using the single dipole assumption as the constrain to find a single solution.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTA0NDQ4ODk4MSwzMDgxNDI4OTQsLTE4MD
I0Mjc1MzksMTYxOTA0MTI5NV19
-->