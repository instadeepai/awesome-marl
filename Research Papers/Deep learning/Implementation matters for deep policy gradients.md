# Implementation matters for deep policy gradients

[ [Paper](https://arxiv.org/pdf/2005.12729.pdf) ]

> We study the roots of algorithmic progress in deep policy gradient algorithms
through a case study on two popular algorithms: Proximal Policy Optimization
(PPO) and Trust Region Policy Optimization (TRPO). Specifically, we investigate
the consequences of “code-level optimizations:” algorithm augmentations found
only in implementations or described as auxiliary details to the core algorithm.
Seemingly of secondary importance, such optimizations turn out to have a major
impact on agent behavior. Our results show that they (a) are responsible for most
of PPO’s gain in cumulative reward over TRPO, and (b) fundamentally change
how RL methods function. These insights show the difficulty and importance of
attributing performance gains in deep reinforcement learning.
> 

# Main contributions:

<aside>
🖊️

We analyze the underpinnings of agent behavior—both through the traditional
metric of cumulative reward, and by measuring more fine-grained algorithmic properties. 
As a first step, we conduct a case study of two of the most popular deep policy-gradient methods: Trust Region Policy Optimization (TRPO) (Schulman et al., 2015a) and Proximal Policy Optimization(PPO) (Schulman et al., 2017). These two methods are closely related: PPO was originally developed as a refinement of TRPO.

We find that much of the observed improvement in reward brought by PPO may come from seemingly small modifications to the core algorithm which we call code-level optimizations. These optimizations are either found only in implementations of PPO, or are described as auxiliary details and are not present in the corresponding TRPO baselines1. We pinpoint these modifications, and perform an ablation study demonstrating that they are instrumental to the PPO’s performance.

</aside>

⇒ What did the authors do?

** It is important to note that code-level optimsations are separate from “implementation choices” like Tensorflow or Pytorch. Code-level optimsations intentionally change algorithm functionality.

### ATTRIBUTING SUCCESS IN PROXIMAL POLICY OPTIMIZATION

1. **Value function clipping**:**:** 
    - The original PPO paper suggests fitting the value network using a standard MSE loss  as
        
        $$
        L^V = (V_{\theta_t} -  V_targ)^2
        $$
        
    
    But, it is common to implement the value-network using a “PPO-like” objective: 
    
    $$
    L^V = max[(V_{\theta_t} - V_{targ})^2, (clip(V_{\theta_t}, V_{\theta_{t-1}} - \epsilon,V_{\theta_{t+1}} + \epsilon) - V_{targ})^2]
    $$
    
2. **Reward scaling:**
    - Normally a policy would receive a raw reward from the environment or a normalised one.
    - Instead rewards can be divided by a rolling standard distribution to maintain a constantly scaled reward
3. **Orthogonal initialisation and layer scaling:**
    - Normally would use a default weight initialisation scheme for  policy and value networks..
    - Instead use orthogonal initialisation scheme with scaling that varies per layer.
4. **Adam learning rate and annealing:**
    - Adam learning rate can be annealed or left constant based on setting.
5. **Reward clipping:**
    - Rewards can be clipped to preset range.
6. **Observation Normalisation:**
    - Normalise observations into mean-zero, variance-one vectors.
7. **Observation Clipping:**
    - Clip observations to limited range.
8. **Hyperbolic tan activations:**
    - Using tanh activation functions in the policy network.
9. **Global gradient clipping:**
    - After computing gradient w.r.t policy and value networks, clip gradients such as the global l2 norm to a fixed range.

To test the effectiveness of these implementation tricks, the authors denote TRPO (TRPO-M) minimal and PPO minimal (PPO-M) as version of the algorithms containing only the core implementations and, TRPO+ and PPO+ as versions containing the implementation tricks. They show that may of the performance improvements attributed to PPO are actually due to these implementation tricks.

## Ablation study on optimisations 1-4

![ablation.png](figures/Implementation%20matters%20for%20deep%20policy%20gradients/ablation.png)

Findings show that reward normlisation, Adam annealing and network initialisation are essential to obtain the highest rewards using PPO.

## CODE-LEVEL OPTIMIZATIONS HAVE ALGORITHMIC EFFECTS

→ The authors investigate how code-level optimisations effect the behavior of agents.

### Trust regions in TRPO and PPO.

- In the middle plot it is found that the PPO variants constantly violate the ratio of the””trust region”.
- Notably all 3 algorithms failed to maintain a ratio-based trust region, despite PPO and PPO-M being trained directly with a ratio-clipping objective.
- In the right plot both PPO variants constrain the KL divergence well despite what was found in the middle figure.
- It is notable that the implementation tricks alter the behavior of the “trust region” between PPO and PPO-M in the right image. This is despite the core algorithm being unchanged between experiments.
- The authors propose that perhaps the behavior of PPO agents is is heavily effected by auxiliary optimisations and not just the core methodology.

![Untitled](figures/Implementation%20matters%20for%20deep%20policy%20gradients/Untitled.png)

## IDENTIFYING ROOTS OF ALGORITHMIC PROGRESS

The authors aim to discover how much the main contribution of the PPO algorithm, the clipping function is actually the primary reason for perceived algorithmic performance. Previously the authors showed that the PPO clipping method is insufficient to maintain a trust region. They then propose that if code-level optimisation as responsible for PPO’s algorithmic performance, then maybe they are also a key factor in it’s perceived performance improvements over TRPO.

### Measuring algorithmic improvement

- The authors introduce 2 metrics; ***********average algorithmic improvement*********** (AAI) and  ************************average code-level improvement************************ (ACLI).
    
    ![AAI.png](figures/Implementation%20matters%20for%20deep%20policy%20gradients/AAI.png)
    
- AAI measures the improvement of PPO over TRPO when all optimisations are present on an equal level.
- ACLI measures the improvement in performance between the same algorithm with and without opti

### PPO without clipping

- The authors create a variant of PPO without the clipping function  PPO-NOCLIP to determine the importance of the clipping function.
- It is found that PPO-NOCLIP can out perform the minimal PPO implementation, PPO-M. With the correct hyper parameters it was deemed that the clipping function is nor responsible for PPO’s performance gains.

![Untitled](figures/Implementation%20matters%20for%20deep%20policy%20gradients/Untitled%201.png)

## Conclusion

- The authors find that many of the code-level optimsations that are commonly omitted from the final papers drastically impact performance.
- Despite how benign these optimisations seem, they fundamentally change the operation of the underlying algorithms that are being used in Deep RL. The authors find many of the reported improvements from PPO over TRPO are in fact purely due to optimisation and not algorithmic performance.
- Finally it is very important that authors design deep RL method using modular methods. Where we fully understand the effect of each component on the functionality of the overall system and, we must develop benchmarking tools that go beyond the benchmark-driven method currently utilised.