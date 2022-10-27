# The Surprising Effectiveness of PPO in Cooperative Multi-Agent Games,

[ [Paper](https://arxiv.org/pdf/2102.03479.pdf) ]

Proximal Policy Optimization (PPO) is a ubiquitous on-policy reinforcement learning
algorithm but is significantly less utilized than off-policy learning algorithms
in multi-agent settings. This is often due to the belief that PPO is significantly
less sample efficient than off-policy methods in multi-agent systems. In this work,
we carefully study the performance of PPO in cooperative multi-agent settings.
We show that PPO-based multi-agent algorithms achieve surprisingly strong performance
in four popular multi-agent testbeds: the particle-world environments,
the StarCraft multi-agent challenge, the Hanabi challenge, and Google Research
Football, with minimal hyperparameter tuning and without any domain-specific
algorithmic modifications or architectures. Importantly, compared to strong offpolicy
methods, PPO often achieves competitive or superior results in both final
rewards and sample efficiency. Finally, through ablation studies, we analyze
implementation and hyperparameter factors that are critical to PPO’s empirical
performance, and give concrete practical suggestions regarding these factors. Our
results show that when using these practices, simple PPO-based methods are a
strong baseline in cooperative multi-agent reinforcement learning. Source code is
released at [https://github.com/marlbenchmark/on-policy](https://github.com/marlbenchmark/on-policy)

# Summary of contributions

- We demonstrate that PPO, without any domain-specific algorithmic changes or architectures
and with minimal tuning, achieves final performances competitive to off-policy methods on
four cooperative benchmarks
- We demonstrate that PPO obtains these strong results while using a comparable number of
samples to many off-policy methods.
- We identify and analyze five implementation and hyperparameter factors that govern the
practical performance of PPO in multi-agent settings, and offer concrete suggestions as to
best practices regarding these factors

# Empirical Findings

## Main results

### MPE Results

- MPE does not provide a true state space, instead they use a concatenation of the local observations as an alternative.
- Parameter sharing is not used in Comm
- MAPPO achieves top scores in all tasks and IPPO is only slightly behind in 2 tasks.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled.png)

### SMAC results

- 2 Extra variants of MAPPO are tested. MAPPO-AS and MAPPO-FP which test different custom input spaces for the central critic.
- IPPO and MAPPO in both configurations are competitive with Qmix with similar sample efficiency across all maps

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%201.png)

### Hanabi Results

- Full scale Hanabi game used with 2 to 5 players.
- MAPPO, IPPO and VDN trained without auxiliary tasks.
- As the number of cards increase, MAPPO produces noticabley improved performance. This shows the importance of the centralised critic in certain cases.
- MAPPO is competitive with both SAD and VDN in all cases and superior with larger numbers of agents.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%202.png)

### Google Football results

- MAPPO outperforms all offpolicy methods, even the purpose built CDS which uses intrinsit rewards and being pretrained on human data.
- MAPPO is able to outperform TiK on 4/5 settings.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%203.png)

## Implementation Factors

### Value Normalisation

- Impact of standardising the value of the output network to reduce instability.
- Was found to universally improve training.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%204.png)

### Input representation to value function

- 4 different observation specs created.
- Augmented spaces can be used on the critic as it it not in effect during execution time.
- The most effective overall was FP. Which is a feature pruned state with overlapping data removed.
- When available, include both local, agent-specific features and global features in the
value function input. Also check that these features do not unnecessarily increase the input dimension

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%205.png)

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%206.png)

### Training Data usage

- Minibatching for MARL universally seems to reduce performance
- PPO is sensitive to the Epoch parameter,

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%207.png)

### PPO Clipping

- Higher clipping values increase learning speed at the cost of stability.
- Sensitive for harder settings.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%208.png)

### PPO Batch Size

- Batch sizing must be above a certain threshold, but once it has been reached, larger batch sizes do not improve learning speed.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%209.png)

### Searching for implementation variance

1. **Hyper parameter variance:** 
    - A thorough hyper-parameter sweep is done for all major aspects of the claimed SOTA algorithms and the Qmix and VDN baselines.
2. **Implementation inconsistency between new algorithms:**
    - ****the authors comb though the SOTA implementations in order to determine all code level optimizations.

# Findings on QMIX:

→ The authors perform ablations to test popular alterations in MARL.

### Adam vs RMSProp

- Most Qmix implementations use RMSProp. Adam is found to be superior in the case of parallel training and should be used instead.
- The original Qmix implementation uses RMSProp, while mose newer algorithms use Adam.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%2010.png)

### Use of eligibility traces

- The original Qmix uses a single step return to learn. Many newer implementations instead use Q(\lambda) learning.
- Q(\lambda) generates better reward signals if tuned correctly and greatly improves performance.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%2011.png)

### Replay buffer size

- Large replay buffers create instability.

- The authors suggest this may be due to the non-stationary nature of MARL tasks rendering samples obsolete at a greater speed

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%2012.png)

### Optimal number of parallel actors

- Cases with smaller numbers of useful samples having a large number of parallel actors reduces learning speed. As most of the data is meaningless the replay buffer becomes filled with poor training data.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%2013.png)

### Hidden layer size

- Larger hidden size for Qmix found to improve performance
- More specifically increasing the size of RNN layer is helpful to improve performance.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%2014.png)

### Hidden layer size

- Overly slow anneal rate for epsilon in e-greedy exploration strategy can cause policy to collapse for Qmix.
- Note this is not consistent across environments and must be tuned.

 

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%2015.png)

# Findings:

### Fully optimised Qmix performance:

- The fully optimised Qmix of the authors out performs all other optimised SOTA algorithms across all tasks and, were able to achieve 100% winrate on all SMAC testing scenarios.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%2016.png)

- Qmix was able to outperform all the newer SOTA algorithms across all tasks when properly optimised.
- The simpler VDN was also able to match and outperform most algorithms.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%2017.png)

### RIIT algorithm:

- The authors present their own policy gradient based algorithm to test the value of the monotonic constraint in an end to end method. The use of monotonic functions is shown to greatly improve sample efficiency but they do stress that this is not the primary contribution of the paper.

![Untitled](figures/The%20Surprising%20Effectiveness%20of%20PPO%20in%20Cooperative%20Multi-Agent%20Games/Untitled%2018.png)

# Conclusion

- Qmix when tuned is able to solve practically all SMAC environments almost perfectly and the MPE env is of limited usefulness as all algorithms aside from LICA have similar scores on it. Essentially with the current SMAC and MPE tests, the comparative performance between algorithms is inconclusive.
- This paper is a very useful look at how to maximize the performance of MARL algorithms on an implementation level and is good justification for more consistent testing conditions and benchmarking tools for MARL..