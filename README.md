# VW_Modified_Scenario2

Assesses performance of Contextual Bandit algorithms in noisy and non-stationary environments using Vorpal Wabbit. 

Some of the initial code used in this repository was sourced from: https://vowpalwabbit.org/tutorials/cb_simulation.html

### Performance Plot:

<img src="https://github.com/dhruv-sirohi/VW_Modified_Scenario2/blob/main/Algorithm_Performance_Plot.png" width="361" height="245" />

### Comments on Algorithm Performance:

The Explore-first algorithm intitially performs very well, with an initial mean click through rate >0.95. This is likely because the initial randomness allows for thorough exploration of the state space. However, performance declines consistently once the reward distribution is changed. This is to be expected, as the policy learned from the initial exploration is no longer optimal.

The Epsilon-Greedy algorithm consistently performs well, with a mean click through rate around ~0.9. After the reward distribution is changed, this algorithm suffers an initial drop in performance but soon improves. This is expected, because the epsilon-greedy exploration allows for changes in the reward distribution to be discovered relatively quickly.

The Softmax algorithm also performs very well initially. It reaches a mean click through rate >0.95 until the first change in the reward distribution, after which performance deteriorates. Performance continues to decline for some time after the change, before improving. This is to be expected, because the non-zero tau value leads to less random exploration. This means that changes in the reward distribution aren't discovered as quickly.

The Non-Learning algorithm consistently performs poorly, with a mean click through rate around ~0.15, which is significantly worse than all other algorithms. This value does not change as the reward distribution changes. This is to be expected because this algorithm only chooses actions random
