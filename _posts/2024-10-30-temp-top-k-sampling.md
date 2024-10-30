---
title: "Temperature and top-k scaling"
date: 2024-10-30
tags: [nlp, llm, python, hyperparameters]
excerpt: "What is it and how to calculate it"
use_math: true
header:
  overlay_image: https://wallpapers.com/images/high/plain-black-background-ms6uthqmbsf3weim.webp
  overlay_filter: 0.5
---


By now, it’s quite likely that you already know that text generation language models, LLMs, and SLMs aim to predict the next word, or rather, the next token, based on the one with the highest probability among all others given the input sequence. (I will use 'word' and 'token' interchangeably.)

Well, we can conclude that for the same input sequence, the next token will always be the same if the choice is based on the one with the highest probability. This method is known as greedy decoding. However, while it ensures consistency, it can also result in repetitive or dull responses.

You’ve probably noticed that, in an interaction with ChatGPT, even if you ask the same question multiple times, the response varies slightly. See the following example, both using GPT-4o:


![precision](/images/chatgpt1.png)
<p align="center"><strong>First answer</strong></p>

![precision](/images/chatgpt2.png)
<p align="center"><strong>Second answer</strong></p>


Note that, although the responses are similar, they are not identical. This variability arises because ChatGPT applies decoding strategies to control the randomness in its responses. Otherwise, it would always provide the same answer for the same input. 

Let’s illustrate how the process of choosing the next word works with Python code:


```python
import numpy as np


ID_TO_TOKEN = {
    0: 'friends',
    1: 'world',
    2: 'halford',
    3: 'flamengo',
    4: 'band',
    5: 'god',
    6: 'group'
}

def softmax(logits):
    exp_logits = np.exp(logits - np.max(logits))
    return exp_logits / exp_logits.sum()
    

output_logits_model = np.array(
    [1.188, -1.497, -1.239, 1.029, 2.144, -2.293, 1.869]
)
probs = softmax(output_logits_model)
print(probs)
# array([0.1511, 0.0103, 0.0133, 0.1289, 0.3931, 0.0046, 0.2986])

token_id = np.argmax(probs)
print(f'{input_sentence} {ID_TO_TOKEN[token_id]}')
# Judas Priest is the best heavy metal band
```

In the scenario above, the next word will always be 'band,' which has the highest probability at 39.31%. But how can we introduce randomness or creativity into the model’s output? See the example below:


```python
np.random.seed(42)
token_id = np.random.choice(len(probs), size=1, p=probs)
print(f'{input_sentence} {ID_TO_TOKEN[token_id]}')
# Judas Priest is the best heavy metal band
```

Notice that the response is the same, but only because we set a seed at the beginning of the code, ensuring the output matches the one obtained earlier. Now, let’s remove the seed and run this code 100 times:


```python
from collections import Counter

token_ids = []
for _ in range(100):
    token_ids.append(
        np.random.choice(len(probs), size=1, p=probs)[0]
    )

counter = Counter(token_ids)
for token_id, count in counter.items():
    print(f'{ID_TO_TOKEN[token_id]} --> {count} ({count / 100:.2f})')
    
# group -> 30 (0.30)
# band -> 35 (0.35)
# world -> 2 (0.02)
# flamengo -> 20 (0.20)
# war -> 12 (0.12)
# halford -> 1 (0.01)
```


In this scenario, the next word is selected based on its probability. If 'band' has a 39% probability, it will be chosen approximately 39% of the time, and 'group' 30% of the time. This means that about 70% of the time, we’ll get a coherent word for the input sentence.

If you’ve worked with LLM providers' APIs, you’ve probably encountered the **temperature** parameter. Temperature manipulates the probability distribution of the model’s output by scaling it. The higher the temperature, the more evenly the probabilities are spread, increasing the chance of selecting less probable words. However, it won’t create a perfectly uniform distribution. Let’s see an example:


```python
temperature = 1.42
scaled_output_logits_model = output_logits_model / temperature
probs_with_temp = softmax(scaled_output_logits_model)
print(scaled_output_logits_model)
# array([0.1762, 0.0460, 0.0524, 0.1627, 0.2842, 0.0309, 0.2477])

token_ids = []
for _ in range(100):
    token_ids.append(
        np.random.choice(len(probs_with_temp), size=1, p=probs_with_temp)[0]
    )

from collections import Counter
counter = Counter(token_ids)
for token_id, count in counter.items():
    print(f'{ID_TO_TOKEN[token_id]} --> {count} ({count / 100:.2f})')

# band -> 25 (0.25)
# war -> 18 (0.18)
# group -> 27 (0.27)
# halford -> 10 (0.10)
# flamengo -> 15 (0.15)
# world -> 3 (0.03)
# god -> 2 (0.02)
```

As the temperature increases, the probabilities become more balanced. Experiment with higher temperatures to observe how the distribution changes.

However, using only temperature can increase the chance of selecting incoherent words. To address this, **top-k sampling** selects the top k words with the highest probabilities before applying temperature. See the example below:

```python
def topk_sampling(array, k):
    indices = np.argpartition(array, -k)[-k:]
    topk_values = array[indices]
    sorted_indices = np.argsort(-topk_values)
    return topk_values[sorted_indices], indices[sorted_indices]

topk_output, topk_idxs = topk_sampling(output_logits_model, 2)
print(topk_output, topk_idxs)
# (array([2.144, 1.869]), array([4, 6]))


new_output_logits_model = np.where(
    output_logits_model < topk_output[-1],
    float('-inf'),
    output_logits_model
)
print(new_output_logits_models)
# array([ -inf,  -inf,  -inf,  -inf, 2.144,  -inf, 1.869])
```

In the code above, we replace all values except the top k with `-inf` before applying softmax, ensuring those tokens receive zero probability. (Try using 0 instead of `-inf` and see what happens.)

Additionally, there is a variant called **top-p sampling** (nucleus sampling), which selects a subset of tokens whose cumulative probability exceeds a given threshold (e.g., 0.9). This ensures flexibility in selecting tokens without limiting the number to a fixed k.

Now you can apply the temperature and proceed with the previous steps.

Well, now you not only understand what the temperature and top-k parameters are and what they’re used for, but you also know how to calculate them and have seen them in practice.