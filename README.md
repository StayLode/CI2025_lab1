# Laboratory 1
## Cooperating with Riccardo Vaccari (348856)

After setting up the knapsack problem according to the specifications provided by the professor, one can choose among three possible initializations.

The tweak function simply flips the presence of a random item in a random knapsack. I also tried with a more sophisticated version (allowing multiple add/remove operations), but it actually produced worse results — likely because it introduced too much randomness.

Two solution approaches were then implemented: one following the classic hill climbing algorithm, and another incorporating tabu search. 

The latter appears to produce better results, especially as the problem size increases, although it requires slightly more computation time.

Best results:
- 1st problem   -> 1065 (with both)
- 2nd problem   -> 41087 (with Tabu Search HC)
- 3rd problem   -> 1644698 (with Tabu Search HC)