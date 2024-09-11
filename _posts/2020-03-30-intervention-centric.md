---
title: "New paper: How to get AI to apply causal reasoning like us -- transferring from observation to action"
categories:
  - causality
tags:
  - "reinforcement learning"
  - "causal inference"
use_math: true
published: true
---

A super important problem in reinforcement learning, and machine learning more generally, is how to improve causal reasoning. I think a key part of the solution, for learning agents in particular, is admitting Russell's much-quoted observation that, when we closely examine the laws of physics, the concept of causality is no longer useful. What is causation if it can't be found within physics then? The answer, I think, is that causality is more part of how we parse the world -- our understanding as tool-using animals par excellence that, if *I* do something, then this will happen, and, importantly, the generalization that, if *someone or something else does something*, then the same thing may occur as if I had done it. 

What, after all, is an intervention, often used as a basis for defining causal relationships? Philosophies of causation admit that this is hard to define in non-causal terms. I believe a hard-coded notion of action spaces in terms of interventions is not flexible enough to allow robust reasoning about interventions. I suggest we focus on operationalizing the notion of internvention, and focus on agents that can solve each of these asepcts. A key aspect, as mentioned above, is the transfer of knowledge obtained from observation to an understanding of what will happen when the agent itself acts -- in this way recognizing the world as possessing causal relationships that exist separately to the agent, and that can be exploited by the agent. This is what philosopher Jim Woodward calls 'intervention-centric' causal reasoning.

This workshop paper presented at ICLR is my foray into developing such tasks and showing they can be solved with meta-reinforcement learning. 
These ideas are the result of discussions with folks in Yoshua Bengio's group at MILA and Upenn. Check out the abstract!

Interventions are central to causal learning and reasoning. Yet ultimately an intervention is an abstraction: an agent embedded in a physical environment (perhaps modeled as a Markov decision process) does not typically come equipped with the notion of an intervention -- its action space is typically ego-centric, without actions of the form 'intervene on X'. Such a correspondence between ego-centric actions and interventions would be challenging to hard-code. It would instead be better if an agent learnt which sequence of actions allow it to make targeted manipulations of the environment, and learnt corresponding representations that permitted learning from observation. Here we show how a meta-learning approach can be used to perform causal learning in this challenging setting, where the action-space is not a set of interventions and the observation space is a high-dimensional space with a latent causal structure. A meta-reinforcement learning algorithm is used to learn relationships that transfer on observational causal learning tasks. This work shows how advances in deep reinforcement learning and meta-learning can provide intervention-centric causal learning in high-dimensional environments with a latent causal structure.

<p style="text-align: center"><img src="../../images/fig1_motivating_example.svg" width="75%"></p>

**Lansdell B** ([pdf]({{site.baseurl}}/docs/Towards_intervention_centric_causal_reasoning_in_learning_agents__long_.pdf)) ICLR 2020 Workshop on Causal Learning for Decision Making