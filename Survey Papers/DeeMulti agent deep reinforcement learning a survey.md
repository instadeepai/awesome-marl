# Multi‑agent deep reinforcement learning: a survey

[ [Paper](https://link.springer.com/content/pdf/10.1007/s10462-021-09996-w.pdf) ]

> This paper is to provide a widened and more comprehensive overview of the current investigations conducted in the field of MADRL while recapitulating what has already been accomplished, the current challenges, and the existing solutions. It is dedicated to whoever wants an excursion into the realm of MADRL, insights about the historical roots of this field and its current developments, besides, an understanding of the open problems to be faced by future research.
> 

# Introduction:

- The contribution of this paper is to present a comprehensive survey of the recent research directions pursued in the field of MADRL.

![Untitled](https://www.researchgate.net/publication/350893932/figure/fig1/AS:1013084911042564@1618549673803/Schematic-structure-of-the-main-contents-in-this-survey-In-Sect3-we-review-schemes_W640.jpg)

# Analysis Training Schemes:

>📌 In this section, the authors describe training schemes that are used in practice for learning agent policies in the multi-agent setting.

![Untitled]([https://s3-us-west-2.amazonaws.com/secure.notion-static.com/41a50292-4c5e-4223-be7f-0cc950a7649c/Untitled.png](https://www.researchgate.net/publication/350893932/figure/fig2/AS:1013084911058954@1618549673889/Training-schemes-in-the-multi-agent-setting-Left-CTCE-holds-a-joint-policy-for-all_W640.jpg))

### **Distributed training decentralized execution (DTDE)**

- Each agent has an associated policy that maps local observations to a distribution over individual actions. No information is shared between agents such that each agent learns independently.
    
    → More recent works report that distributed training schemes scale poorly with the number of agents due to the extra sample complexity, which is added to the learning problem.
    
    → The search for an optimal policy influences the other agents’ decision-making, which may lead to **action shadowing** and impacts the balance between exploration and knowledge exploitation.
    

### **Centralized training centralized execution (CTCE)**

- The CTCE scheme describes a centralized executor modeling the joint policy that maps the collection of distributed observations to a set of distributions over individual actions.
    
    → The CTCE paradigm allows the straightforward employment of single-agent training methods such as actor-critics or policy gradient algorithms for multi-agent problems.
    
    → A phenomenon called “**lazy agents”** may occur in the CTCE setting when one agent learns a good policy but a second agent has less incentive to learn a good policy, as his actions may hinder the first agent, resulting in a lower reward.
    

### **Centralized training decentralized execution (CTDE)**

- Each agent holds an individual policy that maps local observations to a distribution over individual actions. During training, agents are endowed with additional information, which is then discarded at test time.
    
    →By sharing mutual information, the training process can be eased, and the learning speed can become superior when matched against independently trained agents.
    
    → Agents can bypass non-stationarity when extra information about the selected actions is available to all agents during training such that the consequences of actions can be attributed to the respective agents.
    

# Emergent patterns of agent behavior:

>🖊️ “Agents adjust their policies to maximize the task success and react to the behavioral changes of other agents. The dynamic interaction between multiple decision-makers, which simultaneously affects the state of the environment, can cause the emergence of specific behavioral patterns.”


### **Reward Structure**

- The primary factor that influences the emergence of agent behavior is the reward structure. In this section, the authors cite many cases of reward shaping based on the MARL settings (Cooperative…) from previous works.
1. **Cooperative settings:**
    - These are the suggested reward structures based on previous literature:
        - Making the reward of the team larger than the individual reward. (The higher it is the greater is the willingness to collaborate with other agents)
        - Punishing the whole team of agents for the failure of a single agent can cause cooperation.
2. **Competitive settings:** 
    - A competitive setting motivates agents to outperform their adversary counterparts.
    - In the Pong environment, one of the papers proves that the higher the reward for competition, the more likely an agent tries to outplay its opponents.
- The authors also talked about **the Sparse reward**: as the benefits from it is to motivate the agents to firstly explore unknown states, second to reduce uncertainty about the consequences of their own actions.

### **Language**

→ Many of the papers that are mentioned in this section report that utilizing a communication channel can increase task performance in terms of cumulative reward.

### **Social Context**

>🖊️ “Social dilemmas have long been studied as conflict scenarios in which agents gauge between individualistic and collective profits.”


- The social dilemmas can be divided in many ways such as:
1. **Human interaction:**
    
    →Classified along psychological variables
    
    - The gain of individual benefits
    - The fear of future consequences
    - The assessment of the impact of another agent’s behavior
    - The trust between agents
    - The impact of emotions on the decision-making
2. **Commons vs public good dilemmas:**
    - Commons dilemmas: describe the trade-off between individualistic short-term benefits and long-term common interests on a task that is shared by all agents.
    - Public good dilemmas: agents face a scenario where common-pool resources are constrained and oblige a sustainable use of resources.

# Challenges:

### Non-stationarity

>🖊️ “Due to the co-adaption, the environment dynamics appear non-stationary from the perspective of a single agent. Thus, agents face a moving target problem if they are not provided with additional knowledge about other agents.”


- **Proposed solutions:**
    1. Independent learners: this is a naive approach where we ignore the existence of the other agents and assume that their behavior will be static, it brings back the situation to the single-agent RL case.
        
        →The independent learning approach frequently results in poor performance.
        
    2. The CTDE paradigm: can be leveraged to share mutual information between learners to ease training. The availability of information during the training can loosen the non-stationarity of the environment since agents are augmented with information about others.
    3. Meta-Learning: it can be useful to learn how to adapt to the behavioral changes of others, and can also be utilized to construct agent models. By learning how to model other agents and make inferences from them, agents learn to predict the other agent’s future action sequences.

### Learning communication

>🖊️ “When an agent knows the actions taken by others, the learning problem becomes stationary again from a single agent’s perspective in a fully observable environment.”

- **Dec-POMDP:** is the most common framework to investigate communication since it is a fully cooperative setting where agents have partial observability, therefore to improve they need to communicate to know the full state of the environment in order to enhance their *equally-shared reward*.
- **Distributed systems:** in distributed systems, the agents must learn how to share information with one another by communication.
- **CTDE:** the agents can improve their decisions by sharing information during training, and one way to do that is communication, and this ability will be bandwidth-limited at test time.
- **Communication types:**
    1. Broadcasting: 
        - Messages addressed to all participants of the communication channel
        - The two common communication protocols are:
            - RL inter-agent learning (RIAL): deep recurrent Q-network combined with independent Q-learning and it applies *parameter sharing*.
            - Differentiable inter-agent learning (DIAL):
    2. Targeted communication: 
    3. Networked communication:
    4. Extensions:
