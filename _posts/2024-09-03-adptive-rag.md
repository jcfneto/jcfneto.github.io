---
title: "Adptive-RAG"
date: 2024-09-03
tags: [rag, gen-ai, nlp]
# header:
#   overlay_image: "/images/..."
excerpt: "Adptive-RAG"
mathjax: true
---

RAG (Retrieval Augmented Generation) is a technique used to improve the performance of language models. It combines the power of generative language with the ability to retrieve relevant information from a text repository, generating more accurate and relevant responses.

However, the standard RAG is not a universal solution for all problems.

There are three types of question complexity that the user may ask:

1. Questions that can be answered solely with the model's knowledge, without the need to retrieve external information.
2. Questions that can be answered based on the context found in a document.
3. Questions that require searching across multiple documents to be answered.

A RAG system adapted to answer more complex questions must also be capable of answering less complex questions, but at a much higher cost.

In the real world, many questions are not so complex as to justify a scenario where all questions are treated as complex in order to answer the majority of questions of varying complexities.

A solution to address this is to adopt a hybrid approach called Adaptive-RAG. This approach involves dynamically deciding whether the question should be answered based on the document's context or the model's knowledge.

For this, a classifier is used to infer the complexity of the user's question and select the appropriate strategy to respond.

As you may have already guessed, there is no labeled dataset with the pair: question complexity and response strategy. Therefore, it is necessary to produce a labeled dataset. One strategy that can be adopted is, given a set of questions, to pass them through the three approaches (response based on the model's knowledge, response based on a document's context, and response based on the context of multiple documents), and label according to the approach that produced the correct answer. In case of a tie, preference should be given to the simpler approach, taking care to avoid creating a biased dataset.

With this classifier in hand, we now have a router that can select the appropriate approach to answer the user's question, as shown in the image below:

![precision](/images/adptive_rag.png)
<p align="center"><strong>Source: <a href="https://arxiv.org/pdf/2403.14403">Adaptive-RAG: Learning to adapt retrieval-augmented large language models through question complexity</a></strong></p>


I hope this summary of the Adaptive-RAG concept has provided a clear understanding of the key ideas. However, I encourage you to explore further details in the article referenced below. Thanks for reading!


## References

[Jeong, S., Baek, J., Cho, S., Hwang, S. J., & Park, J. C. (2024). Adaptive-rag: Learning to adapt retrieval-augmented large language models through question complexity. arXiv preprint arXiv:2403.14403.](https://arxiv.org/pdf/2403.14403)
