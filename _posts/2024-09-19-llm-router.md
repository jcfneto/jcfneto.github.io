---
title: "Cost vs Efficiency: LLM-Routing"
date: 2024-09-19
tags: [nlp, llm, llm-router]
excerpt: "Reducing cost and maintaining quality is possible"
use_math: true
header:
  overlay_image: https://wallpapers.com/images/high/plain-black-background-ms6uthqmbsf3weim.webp
  overlay_filter: 0.5
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


Considering that the highest-quality model from the list above is **gpt4o**, it’s worth noting that, upon a quick visual analysis, **gemma2-9B** is the smallest model that still managed to produce reasonable answers, even though it approached them differently. Its responses aligned with reality and the stronger model’s output. So for this scenario, where you are selecting a model based purely on the task, **gemma2-9B** might be a solid choice. It comes with a much lower cost per million tokens compared to **gpt4o** ([input/output at \$0.20](https://groq.com/pricing/) vs. [input at \$5.00 and output at \$15.00](https://openai.com/api/pricing/)) while providing sufficient quality for the task at hand.

If you're not convinced that this is the best way to pick a model, good for you! I believe that in data science, the best approach is to work within the given constraints to achieve the best possible outcome and to be able to defend that decision. So, while the approach outlined here is a strong one if you're constrained to this kind of evaluation, there’s always room for further refinement.

That said, the proposed approach has its limitations: there's a subset of geography questions where the weaker model might fail to provide the right answer—or worse, give a completely incorrect response. In such cases, the trade-off between cost and the quality of answers needs more careful consideration, as the price of a wrong answer could be customer churn and damage to your company’s reputation. A better strategy might be to route only the more complex questions to the best available model while handling simpler queries with the smaller, more cost-effective model. This way, you achieve a smarter balance between cost and quality.

In academic circles, this smarter approach is often referred to as LLM-Router or RouteLLM, among other names. In the following sections, I'll present some of the most efficient LLM routing strategies, drawing from two papers ([Hybrid LLM](https://arxiv.org/pdf/2404.14618) and [RouteLLM](https://arxiv.org/pdf/2406.18665)). If you want to dive deeper into the topic, I highly recommend reading the full papers.

Next, I will introduce two approaches for routing queries between language models, utilizing mathematical notations extensively to enhance understanding. I believe it’s crucial—especially if you’re a data scientist—to grasp the fundamentals of the techniques you're applying, rather than just being someone who pushes buttons or connects boxes.

The following section, [*Hybrid LLM Inference*](https://arxiv.org/pdf/2404.14618), presents a probabilistic router with data transformation, while the subsequent section introduces the [*Matrix Factorization Router*](https://arxiv.org/pdf/2406.18665).


## Hybrid LLM Inference

The idea is straightforward: this approach involves training a router capable of directing easy and hard queries between two models of different sizes. Easier queries are sent to a smaller, less expensive, but less accurate model, while harder queries are routed to a larger, more expensive, and more accurate model.

When we mention "easy queries", we actually mean queries where the smaller model can provide answers without losing quality compared to the larger model.

We denote the larger model as $L : \mathcal{X} \to \mathcal{Z}$ and the smaller model as $S : \mathcal{X} \to \mathcal{Z}$, where $\mathcal{X}$ represents the input queries and $\mathcal{Z}$ the possible responses. The router is defined as $r : \mathcal{X} \rightarrow \{0, 1\}$, meaning for a given query $x \in \mathcal{X}$, the router directs it to the smaller model $S(x)$ if $r(x) = 0$, or to the larger model $L(x)$ if $r(x) = 1$.

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



## Matrix Factorization

In the article, several routing approaches are discussed: Similarity-weighted (SW) ranking, Matrix factorization, BERT classifier, and Causal LLM classifier. However, we will focus solely on matrix factorization, as it yielded the best results in the study.

The core idea remains the same: the router determines which model to use for each query, considering the complexity of the query and the capabilities of each model.

We’ll refer to the stronger model as $M_{strong}$ and the weaker model as $M_{weak}$. The model responsible for routing the queries will be denoted as $R_{\alpha}^{bin}$, where the decision to route a query to the stronger model is based on a probability of success for that model. The routing function is defined as:

<div>
$$
R_{\alpha}^{\text{bin}}(q) =
\begin{cases} 
    0 & \text{(send to } M_{\text{weak}} \text{)} \quad \text{if} \ P_{\theta}(\text{win}_{M_{\text{strong}}} \mid q) < \alpha \\
    1 & \text{(send to } M_{\text{strong}} \text{)} \quad \text{otherwise}
\end{cases}
$$
</div>

Where:

- $q ∈ Q$ is the query;
- $ P_{\theta}(\text{win}_{M_{\text{strong}}} \vert q) $ represents the probability that the stronger model $M_{strong}$ will provide a superior answer compared to the weaker model $M_{weak}$ for the query $q$;
- $\alpha$ is a threshold that controls the balance between cost and quality—essentially, the higher the value of $\alpha$, the stricter the requirement to use the stronger model, aiming to reduce costs.

The probability $P_{\theta}(\text{win}_{M_{\text{strong}}} \vert q)$ is learned from preference data, where different queries are evaluated by both models, and the choice is recorded based on which model provided the higher-quality answer. This learning process is formalized by the following maximization function:

<div>
$$
\max_{\theta} \sum_{(q, l_{i, j}) \in D_{\text{pref}}} \log P_{\theta}(l_{i,j} \vert q)
$$
</div>

Here, $D_{\text{pref}}$ denotes the preference dataset, where $l_{i,j}$ represents the outcome of the comparison between two models, $M_i$ and $M_j$, in terms of response quality for a given query $q$. The possible values for $l_{i,j}$ are $\mathcal{L} = \{{ win_{M_i}, \text{tie}, win_{M_j} \}}$.

To evaluate the efficiency of this approach, the authors propose using two metrics: a cost-efficiency metric $c(R_{\alpha}^{bin})$, which measures the percentage of queries routed to the stronger model, and another metric that evaluates response quality $r(R_{\alpha}^{bin})$ to assess the accuracy of the answers.


Based on this, the PGR (Performance Gap Recovered) metric is introduced, which quantifies the router’s performance in relation to the performance gap between the stronger and weaker models. Since PGR alone does not capture the trade-off between quality and cost, the APGR metric is proposed to measure the average performance of the router across different cost thresholds.

<div>
$$
PGR(R_{\alpha}^{\text{bin}}) = \frac{r(R_{\alpha}^{\text{bin}}) - r(M_{\text{weak}})}{r(M_{\text{strong}}) - r(M_{\text{weak}})}
$$
</div>

<div>
$$
APGR(R_{\text{bin}}) = \int_0^1 PGR(R_{\alpha}^{\text{bin}}) \, d(c(R_{\alpha}^{\text{bin}})) \approx \frac{1}{10} \sum_{i=1}^{10} PGR(R_{\alpha_i}^{\text{bin}})
$$
</div>

The training of the router uses preference data from the [*Chatbot Arena*](https://lmarena.ai/), where users compare the responses of two models for each query. The resulting dataset, $D_{arena}$, contains pairs of responses from two models, with a label indicating which model won or if the result was a tie. Due to the sparsity of direct comparisons, the models are grouped into three tiers based on their scores (to understand how these scores are determined, see the [leaderboard](https://lmarena.ai/?leaderboard)): strong, weak, and intermediate models. This grouping increases the variety of comparisons and generally improves the router’s performance.

To further address data sparsity, two data augmentation techniques are used. The first, called Golden-labeled datasets $D_{gold}$, uses automatically labeled data in the form $D_{gold} = \{ (q, a, l_g) \}$, where $q$ is the query and $l_g$ is the label automatically generated from the response $a$. The second, called LLM-judge-labeled datasets $D_{judge}$, generates comparisons between a strong and a weak model using a judge model. This judge model must be a strong model, one that shows high correlation with human preferences (see the [leaderboard](https://lmarena.ai/?leaderboard)).

Matrix factorization aims to capture the low-dimensional structure of interactions between queries and models. In this case, the scoring function $s(M_w, q)$ is used to represent the quality of the responses from model $M_w$ to query $q$. If model $M_w$ is better than $M_l$, we expect that $s(M_w, q) \gt s(M_l, q)$. This relationship is modeled using a sigmoid function $\sigma$, resulting in the probability of a win:

<div>
$$
P(\text{win}_{M_w} \mid q) = \sigma (s(M_w, q) - s(M_l, q))
$$
</div>

This scoring function $s$ is modeled using a bilinear function that depends on both the identity of the model and the query. For this, each model is mapped to a vector $v_m$ of dimension $d_m$, and each query is mapped to a vector $v_q$ of dimension $d_q$. The function that defines this score is given by:

<div>
$$
s(M, q) = \mathbf{w}_2^T \left( \mathbf{v}_m \odot \left( \mathbf{W}_1^T \mathbf{v}_q + \mathbf{b} \right) \right)
$$
</div>

Where:

- $v_m$ is the vector representing the model;
- $v_q$ is the vector representing the query;
- $W_1$ is the projection matrix that aligns the dimensions of $v_q$ with $v_m$;
- $w_2$ is the linear regression vector that produces the final scalar score;
- $\odot$ represents the Hadamard product.

In other words, there is a learned matrix factorization of scores across the set $Q \times M$, allowing the model to capture the relationships between queries and models. As demonstrated in the article, this approach yielded the best results based on the context of the experiments.

Additionally, it can be easily implemented in Python. Below is an example taken from the project's GitHub documentation ([RouteLLM](https://github.com/lm-sys/RouteLLM)).

### 1. Installation:

```bash
pip install "routellm[serve,eval]"
```

### 2. Usage

```python
import os
from routellm.controller import Controller

# Set your API keys for OpenAI and Anyscale
os.environ["OPENAI_API_KEY"] = "sk-XXXXXX"
# Replace with your preferred model provider, in this case, we are using Anyscale's Mixtral.
os.environ["ANYSCALE_API_KEY"] = "esecret_XXXXXX"

# Initialize the Controller with the matrix factorization (mf) router
client = Controller(
  routers=["mf"],
  strong_model="gpt-4-1106-preview",
  weak_model="anyscale/mistralai/Mixtral-8x7B-Instruct-v0.1",
)

# Use the chat completion method to generate a response using the MF router
response = client.chat.completions.create(
  # This specifies the MF router with a cost threshold of 0.11593
  model="router-mf-0.11593",
  messages=[
    {"role": "user", "content": "Hello!"}
  ]
)
```

## Conclusion

This post provided a more detailed explanation of only one approach from each reference article, but as mentioned earlier, these articles also present other methods that might be useful to add to your toolbox.

Personally, I see more advantages in the matrix factorization approach due to its model-agnostic nature. This allows you to swap between strong and weak models without sacrificing the balance between quality and cost in routing. Additionally, the authors have made the router available in a library, which is a great benefit. However, it's important to note that both approaches come with a cost to train the router, which needs to be considered and factored into the overall savings these methods can provide.


If you have any questions, comments, or corrections, feel free to reach out to me on LinkedIn.


## References

[Ding, D., Mallick, A., Wang, C., Sim, R., Mukherjee, S., Ruhle, V., ... & Awadallah, A. H. (2024). Hybrid LLM: Cost-efficient and quality-aware query routing. arXiv preprint arXiv:2404.14618.](https://arxiv.org/pdf/2404.14618)

[Ong, I., Almahairi, A., Wu, V., Chiang, W. L., Wu, T., Gonzalez, J. E., ... & Stoica, I. (2024). Routellm: Learning to route llms with preference data. arXiv preprint arXiv:2406.18665.](https://arxiv.org/pdf/2406.18665)