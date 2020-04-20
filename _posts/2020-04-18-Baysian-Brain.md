---
layout: post
title: The Baysian Brain
tag: [Paper Review]
category: Brain
---

This blog is a review of a paper: Bayes in the Brain -- On Bayesian Modelling in Neuroscience [(Colombo and Seriès, 2012)](https://www.zotero.org/google-docs/?9xYREt)

## How much Bayes is it in our brain?

I am having this thought that the neural network in our brain might encode information using a Baysian framework. There is a paper [(Colombo and Seriès, 2012)](https://www.zotero.org/google-docs/?B67pov) talking about Bayesian modelling in neuroscience. Before writing my thoughts about this, it is important to see what has already been studied.

> ..., a growing trend in theoretical neuroscience considers that the human perceptual system is akin to a Bayesian machine. The function of this machine would be to infer the causes of sensory inputs in an ‘optimal’ way.

To justify this point, the paper talks about the noise and ambiguity of sensory inputs. Our perception requires some mechanism to represent and handle uncertainty. Therefore, our neural network (“nerve systems”) needs to encode probabilistic models through neural processing. The sensory input is used to update the neural encoded probabilistic (Bayesian) models.

The paper addresses two questions:

> (1) How are Bayesian models used in theoretical neuroscience.
> (2) From the use of Bayesian models in theoretical neuroscience, have we learned, or can we hope to learn, that perception is Bayesian inference or that the brain is a Bayesian machine?

An important thing about the two questions is that, as Colombo and Series mentioned in the paper:

> Given the increasing influence on the neuroscience of ideas and tools from such fields, it’s not surprising that Bayesian modeling has a lot to offer to study the brain. Yet, that the brain is a Bayesian machine does not follow from the fact that Bayesian models are used to study the brain and the behavior it generates.

We need to be careful in the sense that what we are discussing here is not in an instrumentalist point of view towards Bayesian modeling. We are trying to look at it from a theoretical neuroscience perspective - the ‘fundamental implication for neuroscience’:

> … the Bayesian coding hypothesis: ‘the brain represents information probabilistically, by coding and computing with probability density functions or approximations to probability density functions’
> The hypothesis is tow-fold:
> (1) The brain performs Bayesian inference to enable us to make judgments and guide action in the world
> (2) The brain represents sensory information in the form of probability distributions.

The paper demonstrates an experiment that fits a Bayesian model to predict the stimuli with both haptic and visual information and compare it with fitting the model separately for each sensory input. The result shows that the behavioral result is accurately predicted by the models, indicating that “Humans integrate visual and haptic information in a statistically optimal fashion”.

Though, it is worth noticing that even if the model is able to compute the belief of the state of the world (the S) from sensory inputs, the model does not indicate any decision making or motor response mechanism. In order for this model to account for decision making or motor response, a loss function has to be optimized. It is also arguable that this kind of Bayesian modeling is feasible for brain neural processing due to its computational complexity. In that case, a linear function approximation might be applied instead of computing the exact probability distribution.(To be continue)

>### Reference
> [Colombo, M., Seriès, P., 2012. Bayes in the Brain—On Bayesian Modelling in Neuroscience. Br. J. Philos. Sci. 63, 697–723. https://doi.org/10.1093/bjps/axr043](https://www.zotero.org/google-docs/?gGyNfB)

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU5MDUyMjkwMCwtMTg1NzU5ODA3MCwtMT
kwMjE2MDQ4LC0xNDMxMjI5NTU0LC0xODg4NzM3Mzc4LC03OTE2
MDcxNDFdfQ==
-->