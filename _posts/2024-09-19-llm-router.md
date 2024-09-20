---
title: "Cost vs Efficiency: LLM-Routing"
date: 2024-09-19
tags: [nlp, llm, llm-router]
# header:
#   overlay_image: "/images/..."
excerpt: "Reducing cost and maintaining quality is possible"
use_math: true
---

Nowadays, we have access to a wide range of Small Language Models (SMLs) and Large Language Models (LLMs), each with their own strengths and weaknesses. Because of this, it’s essential to choose the right model for the task at hand. Ideally, you want to strike a balance between cost and performance, aiming for a satisfactory level of quality while keeping expenses low.

You can select a model based on the specific task it will perform. For example:

Imagine you're developing an educational assistant to help students with general geography questions. This assistant would receive queries like: "What is the capital of the state of Goiás?", "Name the biomes found in the state of Mato Grosso.", "What was the region where the Vikings lived called?", "What is the predominant biome in northern Italy?" and similar questions. Let's take a look at how different models respond to these questions on the first try:


<details>
  <summary>What is the capital of the state of Goiás?</summary>

  <ul>
    <li><strong>llama3.1-8B</strong>: The capital of the state of Goiás in Brazil is Goiânia.</li>
    <li><strong>gemma2-9B-8k</strong>: The capital of the state of Goiás is <strong>Goiânia</strong>.</li>
    <li><strong>llama3.1-70B</strong>: The capital of the state of Goiás in Brazil is Goiânia.</li>
    <li><strong>gpt4o-mini</strong>: The capital of the state of Goiás is Goiânia.</li>
    <li><strong>gpt4o</strong>: The capital of the state of Goiás is <strong>Goiânia</strong>.</li>
  </ul>

</details>

<br>

<details>
  <summary>Name the biomes found in the state of Mato Grosso.</summary>
  
  <ul>
    <li><strong>llama3.1-8B</strong>: Mato Grosso is a state located in the western-central region of Brazil. The state has a diverse range of biomes, including:
      <ol>
        <li>Cerrado: A tropical savanna biome that covers approximately 60% of the state. The Cerrado biome is characterized by open grasslands, scrublands, and forests.</li>
        <li>Pantanal: A tropical wetland biome that covers a small portion of the state, mainly in the southwestern region. The Pantanal is the world's largest tropical wetland area, known for its unique ecosystem and biodiversity.</li>
        <li>Amazon Rainforest: A portion of the Amazon Rainforest biome extends into the state, mainly in the northwestern region. This biome is characterized by dense, humid forests with a vast array of plant and animal species.</li>
        <li>Caatinga: A semi-arid biome that covers a small portion of the state, mainly in the northeastern region. The Caatinga biome is characterized by dry forests, scrublands, and grasslands.</li>
        <li>Atlantic Forest: A small portion of the Atlantic Forest biome extends into the state, mainly in the southeastern region. This biome is characterized by dense, humid forests with a rich biodiversity.</li>
      </ol>
    </li>
    <li><strong>gemma2-9B-8k</strong>: Mato Grosso is a state in Brazil with a diverse range of biomes. Here are some of the most prominent:
      <ul>
        <li><strong>Cerrado:</strong> This is the dominant biome in Mato Grosso, covering a vast majority of the state. It's characterized by savanna-like grasslands with scattered trees, a distinct dry season, and rich biodiversity.</li>
        <li><strong>Amazon Rainforest:</strong> A portion of the eastern part of Mato Grosso falls within the Amazon rainforest, the largest tropical rainforest in the world. This biome is known for its incredible biodiversity, dense vegetation, and crucial role in global climate regulation.</li>
        <li><strong>Pantanal:</strong> A significant portion of the Pantanal, the world's largest tropical wetland, extends into Mato Grosso. This biome is characterized by seasonal flooding, abundant wildlife, and unique adaptations to waterlogged conditions.</li>
      </ul>
    </li>
    <li><strong>llama3.1-70B</strong>: Mato Grosso is a state in Brazil that is home to several biomes. Here are some of the main biomes found in Mato Grosso:
      <ol>
        <li><strong>Amazon Rainforest:</strong> The largest tropical rainforest in the world covers a significant portion of Mato Grosso, particularly in the north and northwest regions. This biome is characterized by dense vegetation, high temperatures, and high levels of rainfall.</li>
        <li><strong>Cerrado:</strong> The Cerrado is a savanna-like biome that covers about 60% of Mato Grosso. It is a tropical grassland with scattered trees, and is characterized by a dry season and a rainy season. The Cerrado is home to a diverse range of plant and animal species.</li>
        <li><strong>Pantanal:</strong> The Pantanal is the world's largest tropical wetland, covering an area of approximately 140,000 square kilometers in Mato Grosso. It is a floodplain biome, characterized by seasonal flooding and a diverse range of aquatic and terrestrial ecosystems.</li>
        <li><strong>Atlantic Forest:</strong> Although not as extensive as the other biomes, the Atlantic Forest biome is also present in Mato Grosso, particularly in the eastern and southeastern regions. This biome is characterized by a mix of tropical and subtropical forests.</li>
      </ol>
    </li>
    <li><strong>gpt4o-mini</strong>: Mato Grosso, a state in Brazil, features several distinct biomes, including:
      <ol>
        <li><strong>Amazon Rainforest</strong> - Located primarily in the northern part of the state, this biome is characterized by high biodiversity and dense vegetation.</li>
        <li><strong>Cerrado</strong> - This tropical savanna biome covers much of central Mato Grosso, known for its unique flora, including grasses and shrubs, as well as a variety of wildlife.</li>
        <li><strong>Pantanal</strong> - A vast tropical wetland, the Pantanal is located in the southwestern part of Mato Grosso. It is famous for its rich biodiversity and seasonal flooding.</li>
        <li><strong>Mato Grosso Plateau</strong> - This region features a mix of cerrado and transition areas with various ecosystems, including forests and grasslands.</li>
      </ol>
    </li>
    <li><strong>gpt4o</strong>: The state of Mato Grosso in Brazil is home to three major biomes:
      <ol>
        <li><strong>Amazon Rainforest (Amazônia):</strong> Found in the northern region of the state, this biome is known for its rich biodiversity, dense forests, and significant rainfall.</li>
        <li><strong>Cerrado:</strong> Covering much of central Mato Grosso, the Cerrado is a tropical savanna characterized by vast open landscapes, grasslands, and scattered trees.</li>
        <li><strong>Pantanal:</strong> Located in the southwestern region, the Pantanal is the world's largest tropical wetland area, known for its seasonal floods and abundant wildlife.</li>
      </ol>
    </li>
  </ul>

</details>

<br>

<details>
  <summary>What was the region where the Vikings lived called?</summary>
  
  <ul>
    <li><strong>llama3.1-8B</strong>: The region where the Vikings lived was called Scandinavia. Scandinavia is a peninsula in Northern Europe, and it includes present-day countries such as Denmark, Norway, and Sweden. The Vikings originated from various regions within Scandinavia, including present-day Denmark, Norway, and southern Sweden.
      <br>However, the Vikings also referred to their homeland as 'Norse' or 'Nordic' lands.
    </li>
    <li><strong>gemma2-9B-8k</strong>: The region where the Vikings lived is called <strong>Scandinavia</strong>.
      <ul>
        <li><strong>Denmark</strong></li>
        <li><strong>Norway</strong></li>
        <li><strong>Sweden</strong></li>
      </ul>
      Let me know if you have any other questions about the Vikings!
    </li>
    <li><strong>llama3.1-70B</strong>: The region where the Vikings lived is commonly referred to as Scandinavia or the Nordic countries. More specifically, it includes present-day Denmark, Norway, and Sweden. However, the term 'Viking Age Scandinavia' often refers to a broader area that also encompasses the Faroe Islands, Iceland, parts of Finland, and the Baltic regions.
      <br>In the Viking Age, the region was divided into several smaller kingdoms and territories, including:
      <ul>
        <li>Denmark (present-day Denmark)</li>
        <li>Norway (present-day Norway)</li>
        <li>Sweden (present-day Sweden)</li>
        <li>Iceland (settled by the Vikings in the late 9th century)</li>
        <li>The Faroe Islands (settled by the Vikings in the 9th century)</li>
      </ul>
      These regions were inhabited by various tribes and communities, including the Danes, Norwegians, Swedes, and others, who shared a common cultural and linguistic heritage.
    </li>
    <li><strong>gpt4o-mini</strong>: The region where the Vikings lived is commonly referred to as Scandinavia, which includes modern-day countries such as Norway, Sweden, and Denmark. The term "Viking" specifically refers to the Norse seafarers from this area during the late eighth to early eleventh centuries.
    </li>
    <li><strong>gpt4o</strong>: The region where the Vikings lived was called <strong>Scandinavia</strong>. This area encompasses the modern countries of <strong>Norway</strong>, <strong>Sweden</strong>, and <strong>Denmark</strong>, as well as parts of <strong>Finland</strong> and <strong>Iceland</strong>. During the Viking Age (approximately 793–1066 AD), the Norse people from these regions were known for their seafaring expeditions, exploration, and settlement across Europe and beyond.
    </li>
  </ul>

</details>

<br>

<details>
  <summary>What is the predominant biome in northern Italy?</summary>
  
  <ul>
    <li><strong>llama3.1-8B</strong>: The predominant biome in northern Italy is the Temperate Deciduous Forest biome, also known as the Temperate Broadleaf and Mixed Forest biome. This biome is characterized by deciduous trees such as oak, beech, and chestnut, which lose their leaves seasonally.
      <br>However, northern Italy also has a significant portion of the Mediterranean biome, particularly in the coastal regions. The Mediterranean biome is characterized by evergreen trees such as olive, cypress, and pine, as well as scrublands and maquis.
      <br>In the mountainous regions of northern Italy, such as the Alps and the Apennines, the Alpine Tundra biome is found at high elevations. This biome is characterized by low-growing vegetation, such as grasses and shrubs, and is often treeless due to harsh weather conditions.
      <br>Overall, the biome of northern Italy is diverse and varies depending on the region, elevation, and climate.
    </li>
    <li><strong>gemma2-9B-8k</strong>: The predominant biome in northern Italy is <strong>temperate deciduous forest</strong>.
      <ul>
        <li><strong>Climate:</strong> Northern Italy has a humid subtropical climate with warm summers and mild, wet winters. This climate is ideal for deciduous trees like oak, beech, and maple, which lose their leaves in the fall.</li>
        <li><strong>Geography:</strong> The region is characterized by rolling hills and mountains, providing diverse habitats for a variety of plant and animal life.</li>
      </ul>
      While other biomes like Mediterranean woodland and grassland exist in pockets, the temperate deciduous forest dominates the landscape of northern Italy.
    </li>
    <li><strong>llama3.1-70B</strong>: The predominant biome in northern Italy varies depending on the specific region and elevation. However, some of the main biomes found in northern Italy include:
      <ol>
        <li>Temperate broadleaf and mixed forests: These forests are found in the lower elevations of northern Italy, particularly in the Po Valley and the surrounding foothills. They are characterized by deciduous tree species such as oak, beech, and chestnut.</li>
        <li>Alpine forests: At higher elevations, the biome shifts to alpine forests, which are dominated by coniferous tree species such as spruce, fir, and pine. These forests are found in the Italian Alps, including the Dolomites and the Julian Alps.</li>
        <li>Montane grasslands and shrublands: Above the treeline, the biome transitions to montane grasslands and shrublands, which are characterized by low-growing vegetation such as grasses, shrubs, and alpine flowers.</li>
      </ol>
      Overall, the predominant biome in northern Italy is likely to be temperate broadleaf and mixed forests, given the region's mild climate and fertile soils. However, the specific biome can vary depending on the location and elevation.
    </li>
    <li><strong>gpt4o-mini</strong>: The predominant biome in northern Italy is the temperate forest biome, specifically characterized by deciduous forests. This region features a mix of deciduous trees such as oaks, maples, and beeches, along with coniferous species in the higher elevations of the Alps. Additionally, the area includes diverse habitats like grasslands and wetlands, particularly in the Po Valley.
    </li>
    <li><strong>gpt4o</strong>: The predominant biome in northern Italy is the <strong>temperate deciduous forest biome</strong>. This region, particularly the Po Valley and the surrounding areas, is characterized by a temperate climate with seasonal variations. Forests in this biome typically consist of broad-leaf trees like oak, beech, and chestnut.
      <br>In the higher elevations of the Alps and Apennines in northern Italy, the biome transitions to alpine forests and meadows, with coniferous trees like fir and pine dominating the landscape.
    </li>
  </ul>

</details>
<br>


Considering that the highest-quality model from the list above is **gpt4o**, it’s worth noting that, upon a quick visual analysis, **gemma2-9B** is the smallest model that still managed to produce reasonable answers, even though it approached them differently. Its responses aligned with reality and the stronger model’s output. So, in a scenario where you're selecting a model based purely on the task, **gemma2-9B** could be a solid choice. It comes with a much lower cost per million tokens compared to **gpt4o** ([input/output at `$0.20`](https://groq.com/pricing/) vs. [input at `$5.00` and output at `$15.00`](https://openai.com/api/pricing/)) while providing sufficient quality for the task at hand.

If you're not convinced that this is the best way to pick a model, good for you! I believe that in data science, the best approach is to work within the given constraints to achieve the best possible outcome and to be able to defend that decision. So, while the approach outlined here is a strong one if you're constrained to this kind of evaluation, there’s always room for further refinement.

That said, the proposed approach has its limitations: there's a subset of geography questions where the weaker model might fail to provide the right answer—or worse, give a completely incorrect response. In such cases, the trade-off between cost and the quality of answers needs more careful consideration, as the price of a wrong answer could be customer churn and damage to your company’s reputation. A better strategy might be to route only the more complex questions to the best available model while handling simpler queries with the smaller, more cost-effective model. This way, you achieve a smarter balance between cost and quality.

In academic circles, this smarter approach is often referred to as LLM-Router or RouteLLM, among other names. In the following sections, I'll present some of the most efficient LLM routing strategies, drawing from three key papers (Hybrid LLM, RouteLLM, and RouterBench). If you want to dive deeper into the topic, I highly recommend reading the full papers.

## Hybrid LLM Inference

The idea is straightforward: this approach involves training a router capable of directing easy and hard queries between two models of different sizes. Easier queries are sent to a smaller, less expensive, but less accurate model, while harder queries are routed to a larger, more expensive, and more accurate model.

When we mention "easy queries", we actually mean queries where the smaller model can provide answers without losing quality compared to the larger model.

In this section, we will use the notations introduced in the reference paper to define key elements for understanding this approach. We denote the larger model as $L : \mathcal{X} \to \mathcal{Z}$ and the smaller model as $S : \mathcal{X} \to \mathcal{Z}$, where $\mathcal{X}$ represents the input queries and $\mathcal{Z}$ the possible responses. The router is defined as $r : \mathcal{X} \rightarrow \{0, 1\}$, meaning for a given query $x \in \mathcal{X}$, the router directs it to the smaller model $S(x)$ if $r(x) = 0$, or to the larger model $L(x)$ if $r(x) = 1$.

To evaluate this router, two key metrics are used:

1. **Answer Quality**, defined by $q(z), \ q : \mathcal{Z} \rightarrow \mathbb{R}$, through the **quality gap** $H(x) := q(S(x)) - q(L(x))$, which represents the difference in quality between the smaller model $S(x)$ and the larger model $L(x)$. The quality $q(z)$ is measured using the [BART score](https://proceedings.neurips.cc/paper_files/paper/2021/file/e4d2b6e6fdeca3e60e0f1a62fee3d9dd-Paper.pdf).
2. **Cost** $c(z)$, measured by how often queries are routed to the smaller model, since the smaller model has lower computational and financial costs.

The model used to serve as a router is a BERT-style model trained to predict a value $p_{w}(x)$, which can be interpreted as the probability $Pr[H(x) \geq 0] = Pr[q(S(x)) \geq q(L(x))]$, i.e., the probability that the smaller model $S(x)$'s quality is at least as good as the larger model $L(x)$. In cases where the larger model is significantly stronger, the router can also "relax" the threshold to $Pr[H(x) \geq -t] = Pr[q(S(x)) \geq q(L(x)) - t]$, allowing the smaller model to be used when its quality is within an acceptable margin $t$. When the predicted value $p_{w} \geq$ a certain threshold, the query is routed to the smaller model $S(x)$.

There are three different router types proposed: deterministic, probabilistic, and probabilistic with data transformation. We'll focus on the last one, as it handles scenarios where the larger model is far superior to the smaller model better than the others. For more details on the others, I recommend reading the original paper.

The probabilistic router with data transformation $r_{trans}$ introduces the "relaxation" threshold $t$ to handle scenarios where the quality difference between the models is significant. This allows the smaller model to be used even when its response isn’t identical to the larger model’s, but is close enough within the margin $t$. The equation that defines the transformed probabilistic label is:

<div>
$$
y_{i}^{trans} (t) = Pr[q(S(x_i)) \geq q(L(x_i)) - t]
$$
</div>

The larger $t$ is, the greater the tolerance for the quality difference between the two models. The optimal value for $t$ is found by maximizing the paired average difference between the transformed labels, aiming to distinguish as clearly as possible between the queries that should be routed to the smaller or larger models. This is defined by the following equation:

<div>
$$
t^* = \arg \max_t \frac{1}{N^2} \sum_{(i,j)} \left| y_i^{\text{trans}}(t) - y_j^{\text{trans}}(t) \right|
$$
</div>

With this, it’s possible to find the optimal value of $t$ that balances response quality and cost. If the idea isn’t entirely clear yet, let me explain with the following scenario:

Imagine we have three queries: $x_1$, $x_2$, and $x_3$, and we’re comparing the smaller model’s responses $S(x)$ with those of the larger model $L(x)$ to determine whether we can use the smaller model without compromising too much on quality. The table below shows the calculated quality for each model on each query.

| Query | $q(S(x))$ | $q(L(x))$ | $H(x)$ |
| :---: | :---: | :---: | :---: |
| $x_1$ | 0.85 | 0.90 | -0.05 |
| $x_2$ | 0.60 | 0.85 | -0.25 |
| $x_3$ | 0.95 | 0.95 | 0.00 |

**Step 1: Calculation of $y_i^{trans}(t)$**

Now, let’s calculate the transformed label **$y_i^{trans}(t)$** for different values of $t$. For each query $x_i$, we compute the probability $Pr[q(S(x_i)) \geq q(L(x_i)) - t]$, which determines if the smaller model can be used given the value of $t$.

- For $t = 0.1$:

  - For $x_1$: $q(S(x_1)) = 0.85$ and $q(L(x_1)) = 0.90$. With $t = 0.1$, we check if $q(S(x_1)) \geq q(L(x_1)) - 0.1$, i.e., $0.85 \geq 0.80$. This is true, so $y_1^{trans}(0.1) = 1$.
  - For $x_2$: $0.60 \geq 0.75$, false, so $y_2^{trans}(0.1) = 0$.
  - For $x_3$: $0.95 \geq 0.85$, true, so $y_3^{trans}(0.1) = 1$.

- For $t = 0.2$:

  - For $x_1$: $0.85 \geq 0.70$, true, so $y_1^{trans}(0.2) = 1$.
  - For $x_2$: $0.60 \geq 0.65$, false, so $y_2^{trans}(0.2) = 0$.
  - For $x_3$: $0.95 \geq 0.75$, true, so $y_3^{trans}(0.2) = 1$.

- For $t = 0.3$:

  - For $x_1$: $0.85 \geq 0.60$, true, so $y_1^{trans}(0.3) = 1$.
  - For $x_2$: $0.60 \geq 0.55$, true, so $y_2^{trans}(0.3) = 1$.
  - For $x_3$: $0.95 \geq 0.65$, true, so $y_3^{trans}(0.3) = 1$.

**Step 2: Comparison between queries $i$ and $j$**

Now, we calculate the difference between the labels $y_i^{trans}(t)$ for all pairs of queries $i$ and $j$ at different values of $t$.

- For $t = 0.1$:

  - $\vert y_1^{trans}(0.1) - y_2^{trans}(0.1) \vert = \vert 1 - 0\vert = 1$
  - $\vert y_1^{trans}(0.1) - y_3^{trans}(0.1) \vert = \vert 1 - 1\vert = 0$
  - $\vert y_2^{trans}(0.1) - y_3^{trans}(0.1) \vert = \vert 0 - 1 \vert = 1$
  - Average difference for $t = 0.1$: $\frac{1+0+1}{3} = 0.67$

- For $t = 0.2$:

  - $\vert y_1^{trans}(0.2) - y_2^{trans}(0.2) \vert = \vert 1 - 0 \vert = 1$
  - $\vert y_1^{trans}(0.2) - y_3^{trans}(0.2) \vert = \vert 1 - 1\vert = 0$
  - $\vert y_2^{trans}(0.2) - y_3^{trans}(0.2) \vert = \vert 0 - 1 \vert = 1$
  - Average difference for $t = 0.2$: $\frac{1+0+1}{3} = 0.67$

- For $t = 0.3$:

  - $\vert y_1^{trans}(0.3) - y_2^{trans}(0.3) \vert = \vert 1 - 1 \vert = 0$
  - $\vert y_1^{trans}(0.3) - y_3^{trans}(0.3) \vert = \vert 1 - 1 \vert = 0$
  - $\vert y_2^{trans}(0.3) - y_3^{trans}(0.3) \vert = \vert 1 - 1 \vert = 0$
  - Average difference for $t = 0.3$: $\frac{0+0+0}{3} = 0$

**Step 3: Choosing $t^*$**

- The average difference was $0.67$ for $t = 0.1$ and $t = 0.2$, and $0$ for $t = 0.3$.
- The value that maximizes the difference between labels is $t^* = 0.1$ or $t^* = 0.2$, as both yield the highest average difference between the query pairs.

Once $t^*$ is chosen, the router uses this parameter to train a probabilistic model that predicts $p_w(x)$, the probability that a query can be routed to the smaller model without significant quality loss.

The loss function used to train the router with these probabilistic labels is given by:

<div>
$$
\mathcal{L}(w) = -\frac{1}{N} \sum_{i=1}^{N} \left( y_i^{\text{trans}}(t^*) \log(p_w(x_i)) + (1 - y_i^{\text{trans}}(t^*)) \log(1 - p_w(x_i)) \right)
$$
</div>

This function minimizes the difference between the router’s predicted value $p_w(x_i)$ and the transformed label $y_i^{trans}(t^*)$, adjusting the model so that it can correctly predict when a query can be routed to the smaller model without compromising quality.

The dataset used to train the router was MixInstruct, which contains data for multiple tasks. For training, 10,000 examples were selected from the training set, and for each of these examples, 10 responses were generated from all LLMs under consideration. This helps capture the inherent uncertainty in LLM responses, which is crucial for training the router. The validation and test sets consist of 5,000 examples, following the same structure as the MixInstruct dataset.

The labels $y_i^{trans} (t)$ for training the router were produced based on the quality gap between the smaller and larger models incorporating the relaxation margin $t$. This margin allows the smaller model to be used when its quality is within an acceptable range compared to the larger model.

To be continued.


## References

[Ding, D., Mallick, A., Wang, C., Sim, R., Mukherjee, S., Ruhle, V., ... & Awadallah, A. H. (2024). Hybrid LLM: Cost-efficient and quality-aware query routing. arXiv preprint arXiv:2404.14618.](https://arxiv.org/pdf/2404.14618)
