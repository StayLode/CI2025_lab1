# CI2025_LAB1 - Multiple 0/1 Knapsack Problem with Multidimensional Constraints
## Cooperating with Riccardo Vaccari (348856)

## Description
The goal is to maximize the total value of items allocated across a fixed number of knapsacks, while ensuring that each knapsack respects its multidimensional capacity limits. Each item can be placed in at most one knapsack.

The problem setup is controlled by the following parameters:
- NUM_KNAPSACKS – total number of available knapsacks.
- NUM_ITEMS – total number of items.
- NUM_DIMENSIONS – number of constraint dimensions (e.g., weight, volume).
- VALUES – value assigned to each item.
- WEIGHTS – multidimensional weight (or cost) of each item.
- CONSTRAINTS – maximum allowed capacity for every dimension in each knapsack.
- MAX_STEPS – total number of iterations performed by the optimization algorithm.
- NUM_SAMPLES – number of candidate solutions generated at each step in tabu search

## Solutions

After setting up the knapsack problem according to the specifications provided by the professor, one can choose among three possible initializations.

The tweak function simply flips the presence of a random item in a random knapsack. I also tried with a more sophisticated version (allowing multiple add/remove operations), but it actually produced worse results — likely because it introduced too much randomness.

Two solution approaches were then implemented.

### 1 - Base Hill Climbing

The first proposed solution follows the classic hill climbing algorithm, starting from a solution where all knapasacks are empty.

Before evaluating its fitness, each newly generated solution is checked for validity to ensure that all knapsack constraints are satisfied; if valid, it may then replace the current solution.

```
Best results:
- 1st problem   -> 1065 
- 2nd problem   -> 37838 
- 3rd problem   -> 1101136 
```


### 2 - Tabu Search Hill Climbing
The Hill Climbing solution was enhanced by integrating a Tabu Search strategy, which prevents revisiting previously explored solutions and allows the exploration of multiple neighbors at each iteration.

Only candidates that are valid and not in the tabu list are evaluated, with the best one selected for potential acceptance.

This solution appears to produce better results, especially as the problem size increases, although it requires slightly more computation time.

```
Best results:
- 1st problem   -> 1065
- 2nd problem   -> 41087 
- 3rd problem   -> 1644698 
```