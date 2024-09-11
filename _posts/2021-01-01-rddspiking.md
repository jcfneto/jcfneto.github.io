---
title: "New preprint: Neural Spiking for Causal Inference"
categories:
  - deep learning
tags:
  - "biologically plausible deep learning"
  - "causal inference"
  - "regression discontinuity design"
use_math: true
published: true
---

How do neurons learn their effect on downstream reward, so that they can update their synaptic weights? An important problem known as the credit assignment problem. Konrad and I propose the novel idea that neurons exploit their spiking discontinuity in order to solve this problem.

When a neuron is driven beyond its threshold it spikes, and the fact that it does not communicate its continuous membrane potential is usually seen as a computational liability. Here we show that this spiking mechanism allows neurons to produce an unbiased estimate of their causal influence, and a way of approximating gradient descent learning. Importantly, neither activity of upstream neurons, which act as confounders, nor downstream non-linearities bias the results. By introducing a local discontinuity with respect to their input drive, we show how spiking enables neurons to solve causal estimation and learning problems.

<p style="text-align: center"><img src="../../images/fig1_pretty.png" width="70%" align="middle"></p>

**Lansdell B**, Kording K, [bioRxiv](https://www.biorxiv.org/content/biorxiv/early/2019/10/15/253351.full.pdf) 2019