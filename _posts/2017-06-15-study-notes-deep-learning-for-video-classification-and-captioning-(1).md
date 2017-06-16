---
layout: post
title: Study Notes - Deep Learning for Video Classification and Captioning (1)
tag: [Deep Learning, Computer Vision]
category: Deep Learning
---

This blog post is a study note summary for the paper [Deep Learning for Video Classification and Captioning](https://arxiv.org/abs/1609.06782) published by Zuxuan Wu, Ting Yao, Yuanwei Fu, and Yu-Guang Jiang in 2016.

This paper provides a great introduction and review of the research on video classification and video captioning. It is a very good first read for researchers who are new to the video processing and natural language processing with some machine learning and deep learning background.

## Problem
With the availability of video data, a need has raised to develop applications to understand the meaning of video streams. Video captioning and video classification are two main lines of research to this problem. This paper is a review of resent research on the two topics with an emphasis on deep learning and feature extraction.

## Deep Learning Modules
- Convolutional Neural Networks (CNNs)
  - LeNet-5: back-prop, end-to-end
  - Deep Brief Network: greedy? train each layer in an unsupervised manner
  - AlexNet: 5 conv layers + 3 fully connected layers, RuLU, Dropout
  - VGGNet: 16-19 layers, 3x3 conv filters, able to capture details of input
  - GoogLeNet: multi-scale processing, 22 layers, inception
  - ResNet: 152 - 1000 layers
  - Trend: increasing depth
- Recurrent Neural Networks (RNNs)
  - Good for sequence labeling (speech, sentence, words)
  - cyclicle connection to form cycle, memory
  - unable to carry long-range dependencies
  - vanishing and exploding gradient problems
- Long Short-term Memory (LSTM)
  - store and access information in a long run sequence

## Video Classification
Classify video streams into different categories, for example, human activities.
- Image-based video Classification
  - video treated as a collection of frames
  - each frame feed in pre-trained start-of-the-art deep models (AlexNet, GoogLeNet, etc.) till a certain fully connected layer
  - average the output and feed into a standard classifier such as SVM
- End-to-end CNN Architecture
  - learn hidden spatial-temporal patterns
  - 3D CNN - not performing well because lack of large labeled training data and training is slow
  - 2D CNN - two-stream approach, break the image down in to spatial and temporal clues, Trajectory-Pooled Descriptors - alot of other approaches
- Modeling Long-Term Temporal Dynamics
  - The two stream approach does not take into account the order of of the video stream since the input is taking in frame by frame
  - Leverage RNN (LSTM)
  - LSTM and CNN are highly complementary
- Incorporating Visual Attention
  - detect useful and relevant frames
  - attention mechanism to identify the most discriminative spatial-temporal volumes
  - Motion based Attention
- Unsupervised Video Feature Learning
  - Challenge - not enough training data
  - Use unsupervised learning to find video patterns
