# RETHINKING THE IMPLEMENTATION TRICKS AND MONTONICITY CONSTRAINT IN COOPERATIVE MULTI-AGENT REINFORCEMENT LEARNING

[ [Paper](https://arxiv.org/pdf/2102.03479.pdf) ]

> Many complex multi-agent systems such as robot swarms control and autonomous
> 
> 
> vehicle coordination can be modeled as Multi-Agent Reinforcement Learning
> 
> (MARL) tasks. QMIX, a widely popular MARL algorithm, has been used as
> 
> a baseline for the benchmark environments, e.g., Starcraft Multi-Agent Chal-
> 
> lenge (SMAC), Difficulty-Enhanced Predator-Prey (DEPP). Recent variants of
> 
> QMIX target relaxing the monotonicity constraint of QMIX, allowing for per-
> 
> formance improvement in SMAC. In this paper, we investigate the code-level
> 
> optimizations of these variants and the monotonicity constraint. (1) We find that
> 
> such improvements of the variants are significantly affected by various code-level
> 
> optimizations. (2) The experiment results show that QMIX with normalized op-
> 
> timizations outperforms other works in SMAC; (3) beyond the common wisdom
> 
> from these works, the monotonicity constraint can improve sample efficiency in
> 
> SMAC and DEPP. We also discuss why monotonicity constraints work well in
> 
> purely cooperative tasks with a theoretical analysis. We open-source the code at
> 
> https://github.com/hijkzzz/pymarl2.
> 

# Implementation vs Algorithmic development:

<aside>
🖊️ MARL is currently a very active field particularly in the cooperative MARL setting. Between newly released papers there are a large amount of implementation level optimizations made that are detrimental to reproducibility. Many new value-factorisation algorithms have been produced in recent years that claim to improve upon Qmix and VDN  usually by claiming to relax the monotonic constraint. This paper shows that in fact in each of these claimed SOTA papers there are a wide array of optimization tricks used which inflate the results.

</aside>

⇒ What did the authors do?

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

![Untitled](figures/RETHINKING%20THE%20IMPLEMENTATION%20TRICKS%20AND%20MONOTONICITY%20CONSTRAINT%20IN%20COOPERATIVE%20MULTI-AGENT%20REINFORCEMENT%20LEARNING/Untitled.png)

### Use of eligibility traces

- The original Qmix uses a single step return to learn. Many newer implementations instead use Q(\lambda) learning.
- Q(\lambda) generates better reward signals if tuned correctly and greatly improves performance.

![Untitled](figures/RETHINKING%20THE%20IMPLEMENTATION%20TRICKS%20AND%20MONOTONICITY%20CONSTRAINT%20IN%20COOPERATIVE%20MULTI-AGENT%20REINFORCEMENT%20LEARNING/Untitled%201.png)

### Replay buffer size

- Large replay buffers create instability.

- The authors suggest this may be due to the non-stationary nature of MARL tasks rendering samples obsolete at a greater speed

![Untitled](figures/RETHINKING%20THE%20IMPLEMENTATION%20TRICKS%20AND%20MONOTONICITY%20CONSTRAINT%20IN%20COOPERATIVE%20MULTI-AGENT%20REINFORCEMENT%20LEARNING/Untitled%202.png)

### Optimal number of parallel actors

- Cases with smaller numbers of useful samples having a large number of parallel actors reduces learning speed. As most of the data is meaningless the replay buffer becomes filled with poor training data.

![Untitled](figures/RETHINKING%20THE%20IMPLEMENTATION%20TRICKS%20AND%20MONOTONICITY%20CONSTRAINT%20IN%20COOPERATIVE%20MULTI-AGENT%20REINFORCEMENT%20LEARNING/Untitled%203.png)

### Hidden layer size

- Larger hidden size for Qmix found to improve performance
- More specifically increasing the size of RNN layer is helpful to improve performance.

![Untitled](figures/RETHINKING%20THE%20IMPLEMENTATION%20TRICKS%20AND%20MONOTONICITY%20CONSTRAINT%20IN%20COOPERATIVE%20MULTI-AGENT%20REINFORCEMENT%20LEARNING/Untitled%204.png)

### Hidden layer size

- Overly slow anneal rate for epsilon in e-greedy exploration strategy can cause policy to collapse for Qmix.
- Note this is not consistent across environments and must be tuned.

 

![Untitled](figures/RETHINKING%20THE%20IMPLEMENTATION%20TRICKS%20AND%20MONOTONICITY%20CONSTRAINT%20IN%20COOPERATIVE%20MULTI-AGENT%20REINFORCEMENT%20LEARNING/Untitled%205.png)

# Findings:

### Fully optimised Qmix performance:

- The fully optimised Qmix of the authors out performs all other optimised SOTA algorithms across all tasks and, were able to achieve 100% winrate on all SMAC testing scenarios.

![Untitled](figures/RETHINKING%20THE%20IMPLEMENTATION%20TRICKS%20AND%20MONOTONICITY%20CONSTRAINT%20IN%20COOPERATIVE%20MULTI-AGENT%20REINFORCEMENT%20LEARNING/Untitled%206.png)

- Qmix was able to outperform all the newer SOTA algorithms across all tasks when properly optimised.
- The simpler VDN was also able to match and outperform most algorithms.

![Untitled](figures/RETHINKING%20THE%20IMPLEMENTATION%20TRICKS%20AND%20MONOTONICITY%20CONSTRAINT%20IN%20COOPERATIVE%20MULTI-AGENT%20REINFORCEMENT%20LEARNING/Untitled%207.png)

### RIIT algorithm:

- The authors present their own policy gradient based algorithm to test the value of the monotonic constraint in an end to end method. The use of monotonic functions is shown to greatly improve sample efficiency but they do stress that this is not the primary contribution of the paper.

![Untitled](figures/RETHINKING%20THE%20IMPLEMENTATION%20TRICKS%20AND%20MONOTONICITY%20CONSTRAINT%20IN%20COOPERATIVE%20MULTI-AGENT%20REINFORCEMENT%20LEARNING/Untitled%208.png)

# Conclusion

- Qmix when tuned is able to solve practically all SMAC environments almost perfectly and the MPE env is of limited usefulness as all algorithms aside from LICA have similar scores on it. Essentially with the current SMAC and MPE tests, the comparative performance between algorithms is inconclusive.
- This paper is a very useful look at how to maximize the performance of MARL algorithms on an implementation level and is good justification for more consistent testing conditions and benchmarking tools for MARL..