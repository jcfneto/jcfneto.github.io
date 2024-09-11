---
title: "MetaEvolv: Evolutionary Metaheuristic Optimization in Python"
date: 2024-08-17
tags: [genetic algorithm, evolutionary computing, metaheuristics, python]
# header:
#   overlay_image: "/images/metaevolv-banner.png"
excerpt: "Introducing MetaEvolv, a Python library for evolutionary metaheuristic optimization algorithms."
mathjax: true
---

## MetaEvolv

During my master’s program, I had the opportunity to take a course in Evolutionary Computing. Among the many challenges presented in the course, one of the most significant was the implementation of various evolutionary and metaheuristic algorithms. These files had been sitting in a repository on my GitHub for about three years. Recently, I decided to revisit this material, adjust a few details such as adding docstrings and updating sections that had become deprecated. As a result, I decided to release them as a Python library.

I’m pleased to introduce MetaEvolv, a Python library that includes several evolutionary metaheuristic optimization algorithms, including ABC (Artificial Bee Colony), Clonalg (Clonal Selection Algorithm), DE (Differential Evolution), GA (Genetic Algorithm), and PSO (Particle Swarm Optimization).

To install the package, simply run:

```bash
pip install metaevolv
```

And to use it, here’s a simple example:

```python
import numpy as np
from metaevolv import GeneticAlgorithm
from metaevolv.ga import GAConfig

# Define your objective function
def objective_function(x: np.ndarray) -> float:
    return np.sum(x**2)

# Configure the genetic algorithm
config = GAConfig(
    bits=10,
    dimensions=2,
    n_population=50,
    search_range=(-10.0, 10.0),
    k=3,
    cp=0.8,
    mp=0.01,
    max_iter=100,
    selection_type='tournament',
    crossover_type='one_point',
    mutation_type='bit_by_bit',
    pc_variation='constant',
    cp_final=0.9
)


# Instantiate the genetic algorithm with the configuration
ga = GeneticAlgorithm(config, objective_function)

# Run the algorithm
ga.fit()

# Display the results
print(f"Best solution found: {ga.best_ind}")
print(f"Objective function value at the best solution: {ga.best_eval}")
```